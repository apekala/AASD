# Karta roli GAIA: Koordynator

**Role Schema:** `Coordinator`

## Description

Koordynuje działanie aplikacji: analizuje stan wiedzy o użytkowniku i sporcie, i na tej podstawie podejmuje dalsze działania.

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| `UserKnowledgeChanged` | UserKnowledgeCollector -> Coordinator: powiadomienie o zmianie stanu wiedzy o użytkowniku |
| `CalendarChanged` | CalendarManager -> Coordinator: powiadomienie o zmianie w kalendarzu |
| `GetUserKnowledge` | Coordinator -> UserKnowledgeCollector: zapytanie o stan wiedzy o użytkowniku |
| `GetSportKnowledge` | Coordinator -> SportKnowledgeCollector: zapytanie o wiedzę o sporcie |
| `GeneratePlan` | Coordinator -> Planner: prośba o wygenerowanie planu |
| `GenerateQuestionnaire` | Coordinator -> QuiestionnaireHandler: prośba o wygenerowanie ankiety dla użytkownika |
| `ReturnQuestionnaireResult` | QuestionnaireHandler -> Coordinator: wynik ankiety (odpowiedzi, braki lub przyczyna niepowodzenia); zamyka zlecenie `GenerateQuestionnaire` |
| `GetSummary` | Coordinator -> QuestionnaireHandler: żądanie podsumowania ankiet użytkownika z danego okresu i tematu |
| `ReturnSummary` | QuestionnaireHandler -> Coordinator: podsumowanie ankiet albo informacja o braku danych lub błędzie; zamyka interakcję `GetSummary` |
| `AcceptPlan` | Coordinator <-> użytkownik przez interfejs: przedstawienie planu wraz z uzasadnieniem i źródłami oraz odebranie decyzji użytkownika (plan zaakceptowany lub odrzucony). |
| `SavePlan` | Coordinator -> CalendarManager: prośba o zapis planu treningowego w kalendarzu użytkownika |


### Aktywności

| Nazwa | Opis |
| --- | --- |
| `Analyze` | Analizuje potrzeby użytkownika na podstawie wiedzy o nim, wiedzy o treningach, wiedzy o sporcie, aktualnego planu, itd. |
| `InformUser` | Informuje użytkownika o jakimś wydarzeniu. |

## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads sportKnowledge, userKnowledge, userPlan` | Odczyt wiedzy o sporcie, wiedzy o użytkowniku oraz aktualnego planu. |
| `reads supplied planDecision` | Decyzja użytkownika o planie odebrana w `AcceptPlan`: zaakceptowany (`accepted`) lub odrzucony (`rejected`). |

## Responsibilities

### Liveness

```text
Coordinator      = (AwaitChange . AnalyzeUserState . DecideWhatNext . [InformUser])^ω
AwaitChange      = (UserKnowledgeChanged | CalendarChanged)
AnalyzeUserState = (GetUserKnowledge . GetSportKnowledge . [GetSummary . ReturnSummary] . Analyze)
DecideWhatNext   = [PlanFlow | QuestionnaireFlow]
PlanFlow         = (GeneratePlan . [AcceptPlan . (SavePlan | QuestionnaireFlow)])
QuestionnaireFlow = (GenerateQuestionnaire . ReturnQuestionnaireResult)
```

- `DecideWhatNext` jest opcjonalne: gdy `Analyze` stwierdzi, że plan nie wymaga zmian i nie jest potrzebna ankieta, Koordynator nie wykonuje żadnego działania i wraca do `AwaitChange`.
- `GetSummary . ReturnSummary` jest wykonywane, gdy analiza wymaga historii ankiet użytkownika.
- `AcceptPlan` jest wykonywane tylko wtedy, gdy Planer zwrócił plan (`userPlan ≠ NULL`). Zaakceptowany plan jest zapisywany przez `SavePlan`. Po odrzuceniu Koordynator zleca ankietę o powód odrzucenia (`QuestionnaireFlow` z kontekstem odrzuconego planu, RF-10).

### Safety

- planDecision ≠ accepted  =>  `SavePlan` nie jest wykonywane (plan trafia do kalendarza użytkownika wyłącznie po jego akceptacji).
