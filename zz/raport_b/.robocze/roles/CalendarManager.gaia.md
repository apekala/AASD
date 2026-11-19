# Karta roli GAIA: CalendarManager

**Role Schema:** `CalendarManager`

## Description

Zarządza kalendarzem użytkownika.

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| `CalendarChanged` | Poinformowanie o zmianie w kalendarzu. |
| `FreeTimeRequest` | Oczekiwanie na żądanie odczytu wolnego czasu z kalendarza. |
| `FreeTimeResponse` | Przekazanie żądanych danych. |
| `SavePlan` | Prośba o zapis planu treningowego w kalendarzu użytkownika. |

### Aktywności lokalne

| Nazwa | Opis |
| --- | --- |
| `CheckIfCalendarChanged` | Sprawdzenie, czy kalendarz uległ zmianie. |
| `ReadCalendar` | Odczyt kalendarza. |
| `CalculateFreeTime` | Kalkulacja czasu wolnego użytkownika. |
| `WritePlan` | Zapis planu treningu do kalendarza. |

## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads supplied userPlan` | Odczytuje przekazany plan treningów użytkownika. |
| `changes trainingPlan` | Zapisuje i odczytuje plan treningowy do/z kalendarza. |

## Responsibilities

### Liveness

```text
CalendarManager     = (CheckIfCalendarChanged | SupplyRequestedData | ChangeCalendar)^ω
HandleChangedData   = (ReadCalendar . [CalendarChanged])
SupplyRequestedData = (FreeTimeRequest . ReadCalendar . CalculateFreeTime . FreeKnowledgeResponse)
ChangeCalendar      = (SavePlan . WritePlan)
```

### Safety

- overlapsExist = true  =>  planSaveError
