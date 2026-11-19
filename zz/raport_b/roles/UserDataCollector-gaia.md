# Karta roli GAIA: UserDataCollector

**Role Schema:** `UserDataCollector`

## Description

Dostarcza wiedzę o użytkowniku i informuje o zmianach jej stanu.

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| `UserDataChanged` | Poinformowanie o zmianie danych użytkownika. |
| `AwaitDataRequest` | Oczekiwanie na żądanie udostępnienia danych. |
| `SendRequestedData` | Przekazanie żądanych danych. |

### Aktywności lokalne

| Nazwa | Opis |
| --- | --- |
| <u>CheckIfDataChanged</u> | Sprawdzenie, czy dane użytkownika uległy zmianie. |
| <u>ReadUserData</u> | Odczyt danych użytkownika. |

## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads workoutData, userData` | Odczytuje dane treningowe i dane użytkownika. |
| `reads supplied knowledgeType` | Odczytuje przekazany typ wymaganej wiedzy. |
| `generates dataChangeInfo` | Generuje informację o zmianie danych użytkownika. |

## Responsibilities

### Liveness

```text
UserDataCollector = (HandleChangedData | SupplyRequestedData)^ω
HandleChangedData = (CheckIfDataChanged . [InformAboutDataChange])
SupplyRequestedData = (AwaitDataRequest . ReadData . SendRequestedData)
```

### Safety

- **true**
