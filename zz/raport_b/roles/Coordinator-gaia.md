# Karta roli GAIA: Koordynator

**Role Schema:** `Coordinator`

## Description

Koordynuje działanie aplikacji: analizuje stan wiedzy o użytkowniku i sporcie, i na tej podstawie podejmuje dalsze działania.

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| UserKnowledgeChanged | UserKnowledgeCollector -> Coordinator: powiadomienie o zmianie stanu wiedzy o użytkowniku |
| CalendarChanged | CalendarManager -> Coordinator: powiadomienie o zmianie w kalendarzu |
| GetUserKnowledge | Coordinator -> UserKnowledgeCollector: zapytanie o stan wiedzy o użytkowniku |
| GetSportKnowledge | Coordinator -> SportKnowledgeCollector: zapytanie o wiedzę o sporcie |
| GeneratePlan | Coordinator -> Planner: prośba o wygenerowanie planu |
| GenerateQuestionnaire | Coordinator -> QuiestionnaireHandler -> prośba o wygenerowanie ankiety dla użytkownika |


### Aktywności

| Nazwa | Opis |
| --- | --- |
| <u>Analyze</u> | Analizuje potrzeby użytkownika na podstawie wiedzy o nim, wiedzy o treningach, wiedzy o sporcie, aktualnego planu, itd. |
| <u>InformUser</u> | Informuje użytkownika o jakimś wydarzeniu. |

## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads sportKnowledge, userKnowledge, userPlan` | Odczyt wiedzy o sporcie, wiedzy o użytkowniku oraz aktualnego planu. |

## Responsibilities

### Liveness

```text
Coordinator      = (AwaitChange . AnalyzeUserState . DecideWhatNext . [InformUser])^ω
AwaitChange      = (UserKnowledgeChanged | CalendarChanged)
AnalyzeUserState = (GetUserKnowledge . GetSportKnowledge . Analyze)
DecideWhatNext   = (GeneratePlan | GenerateQuestionnaire)
```

### Safety

- **true**
