# Karta roli GAIA: Planer

**Role Schema:** `Planner`

## Description

Generuje plan treningów użytkownika

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| `GetFreeTime` | Planner -> CalendarManager: zapytanie o czas wolny użytkownika |
| `GetSportKnowledge` | Planner -> SportKnowledgeCollector: zapytanie o wiedzę o sporcie |
| `GeneratePlanRequest` | Coordinator -> Planner: prośba o plan |
| `GeneratePlanResponse` | Planner -> Coordinator: zwrócenie planu |

### Aktywności

| Nazwa | Opis |
| --- | --- |
| `CheckPlanChanged` | Sprawdza, czy aktualny plan wymaga zmiany w świetle wiedzy o użytkowniku. Gdy plan na wejściu to NULL, zmiana jest zawsze wymagana. |
| `GeneratePlan` | Wygenerowanie planu. |


## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads supplied userKnowledge` | Na wejściu otrzymuje wiedzę o użytkowniku w postaci skondensowanej |
| `reads sportKnowledge` | Odczytuje wiedzę o sporcie |
| `generates userPlan, planRationale, sourceReferences` | Generuje plan treningu użytkownika wraz z uzasadnieniem i odwołaniami do źródeł |
| `generates isPlanSafe, isPlanPossible` | Wyniki kontroli planu, na których opierają się warunki safety |

## Responsibilities

### Liveness

```text
Planner         = (GeneratePlanRequest . MakePlan . GeneratePlanResponse)^ω
MakePlan        = (CheckPlanChanged . [GetFreeTime . GetSportKnowledge . GeneratePlan])
```

### Safety

* isPlanSafe = false      =>  plan = NULL
* isPlanPossible = false  =>  plan = NULL
