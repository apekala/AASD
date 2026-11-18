# Karta roli GAIA: Planer

**Role Schema:** `Planner`

## Description

Generuje plan treningów użytkownika

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| GetFreeTime | Planner -> CalendarManager: zapytanie o czas wolny użytkownika |
| GetSportKnowledge | Planner -> SportKnowledgeCollector: zapytanie o wiedzę o sporcie |
| GetPlan | Coordinator -> Planner: prośba o plan |
| ReturnPlan | Planner -> Coordinator: zwrócenie planu |

### Aktywności

| Nazwa | Opis |
| --- | --- |
| <u>GeneratrPlan</u> | Generacja planu treningów na podstawie wiedzy o użytkowniku, jego kalendarza i wiedzy sporcie |

## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads supplied userKnowledge` | Na wejściu otrzymuje wiedzę o użytkowniku w postaci skondensowanej |
| `reads sportKnowledge` | Odczytuje wiedzę o sporcie |
| `generates userPlan` | Generuje plan treningu użytkownika |

## Responsibilities

### Liveness

```text
Planner         = (GetPlan . MakePlan . ReturnPlan)^ω
MakePlan        = (CheckPlanChanged . [GenerateNewPlan] . ReturnPlan)
GenerateNewPlan = (GetFreeTime . GetSportKnowledge . GeneratePlan)
```

### Safety

* isPlanSafe = false      =>  plan = NULL
* isPlanPossible = false  =>  plan = NULL
