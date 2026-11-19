# Karta roli GAIA: Ankieter

**Role Schema:** `QuestionnaireHandler`

## Description

Zbiera informacje o realizacji treningów, samopoczuciu i powodach odrzucenia planu. Przygotowuje ankiety, zapisuje odpowiedzi i przekazuje wyniki Koordynatorowi. Odpowiada za zbieranie danych w RF-03 i RF-10; wspiera RF-08 i RF-09 opisane w [wymaganiach funkcjonalnych](wymagania_funkcjonalne.md).

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| `GenerateQuestionnaire` | Koordynator → Ankieter: zlecenie ankiety z identyfikatorem użytkownika, celem i kontekstem treningu lub odrzuconego planu. |
| `QuestionnaireInteraction` | Ankieter ↔ użytkownik przez interfejs: przedstawienie pytań i odebranie odpowiedzi lub odmowy. Brak odpowiedzi do wyznaczonego terminu kończy oczekiwanie. |
| `ReturnQuestionnaireResult` | Ankieter → Koordynator: wynik ankiety z zapisanymi odpowiedziami, brakami lub przyczyną niepowodzenia. Zamyka zlecenie albo informuje o wyniku ankiety okresowej. |
| `GetSummary` | Koordynator → Ankieter: żądanie podsumowania ankiet danego użytkownika, okresu i tematu. |
| `ReturnSummary` | Ankieter → Koordynator: podsumowanie lub informacja o braku danych albo błędzie. Zamyka interakcję GetSummary. |

### Aktywności lokalne

| Nazwa | Opis |
| --- | --- |
| `CheckQuestionnaireDue` | Sprawdza, czy nadszedł termin ankiety okresowej; jeden termin uruchamia jedną ankietę. |
| `PrepareQuestionnaire` | Sprawdza parametry i przygotowuje pytania wraz z identyfikatorem ankiety i terminem odpowiedzi. |
| `ValidateAnswers` | Sprawdza poprawność odpowiedzi i ich przypisanie do użytkownika oraz ankiety; oznacza braki, odmowę i błędy. |
| `SaveAnswers` | Zapisuje poprawne odpowiedzi z czasem, identyfikatorem ankiety i pochodzeniem ankietowym. |
| `RecordQuestionnaireError` | Przy błędzie parametrów lub przygotowania ankiety ustala wynik z przyczyną niepowodzenia. |
| `BuildSummary` | Podsumowuje historię ankiet w żądanym zakresie, zachowując informację o brakujących danych. |

## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads supplied questionnaireRequest, questionnaireContext, summaryScope` | Cel i kontekst ankiety, odebrane odpowiedzi oraz zakres podsumowania. |
| `reads questionnaireSettings, questionnaireHistory` | Harmonogram i cel ankiet okresowych, termin oczekiwania oraz historia ankiet użytkownika stanowiąca część userData. |
| `generates questionnaire, questionnaireResult, questionnaireSummary` | Pytania, wynik obsługi ankiety i podsumowanie. |
| `changes userData` | Wyłącznie część ankietowa: odpowiedzi, metadane i statusy ankiet, dostępne następnie w questionnaireHistory. |

## Responsibilities

### Liveness

```text
QuestionnaireHandler = (QuestionnaireTask | SummaryTask)^ω
QuestionnaireTask    = (GenerateQuestionnaire | CheckQuestionnaireDue) .
    PrepareQuestionnaire .
    (QuestionnaireInteraction . ValidateAnswers . ([SaveAnswers]
     | RecordQuestionnaireError)) .
    ReturnQuestionnaireResult
SummaryTask = GetSummary . BuildSummary . ReturnSummary
```

- `QuestionnaireTask` oznacza obsługę jednej ankiety, a `SummaryTask` — jednego podsumowania. Ankietę uruchamia zlecenie Koordynatora albo termin z harmonogramu.
- Po poprawnym przygotowaniu ankiety wykonywane są `QuestionnaireInteraction` i `ValidateAnswers`. Przy błędzie parametrów lub przygotowania wykonywane jest `RecordQuestionnaireError`. `SaveAnswers` jest obowiązkowe, gdy istnieją poprawne odpowiedzi, i pomijane w pozostałych przypadkach; niepełny zapis zachowuje oznaczenie braków.
- Każde zadanie kończy się przekazaniem wyniku, także przy braku odpowiedzi, odmowie lub błędzie. Pusta historia daje podsumowanie z informacją o braku danych. O zmianie planu decyduje Koordynator.

### Safety

- Zapis odpowiedzi ⇒ poprawne dane, zgodny userId i identyfikator ankiety; dane zachowują pochodzenie ankietowe i nie nadpisują danych z integracji w userData.
- Brak odpowiedzi lub odmowa ⇒ zapis wyłącznie statusu i metadanych, bez domyślnych deklaracji o treningu czy samopoczuciu.
- questionnaireSummary wynika wyłącznie z questionnaireHistory w zakresie summaryScope i wskazuje brakujące dane.
