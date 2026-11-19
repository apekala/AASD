# Karta roli GAIA: IntegrationsHandler

**Role Schema:** `IntegrationsHandler`

## Description

Zarządza integracjami - połączeniami z innymi aplikacjami i urządzeniami, np. aplikacjami do wykonywania sportu (Strava, Google Fit) lub urządzeniami typu Smartwatch.

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| `IntegrationChanged` | IntegrationsHandler -> UserDataCollector: poinformowanie o zmianie w integracjach (dodanie lub usunięcie integracji). |
| `IntegrationsRequest` | Oczekiwanie na żądanie odczytu wolnego czasu z kalendarza. |
| `IntegrationsResponse` | Przekazanie żądanych danych. |

### Aktywności lokalne

| Nazwa | Opis |
| --- | --- |
| `CheckIntegrations` | Sprawdzenie, stanu integracji - dodania lub usunięcia oraz nowych danych. |
| `SaveIntegrationData` | Zapis nowych danych o/z integracji do bazy. |
| `ReadIntegrations` | Odczyt informacji o integracjach. |

## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads supplied integrationType` | Odczytuje przekazany typ integracji. |
| `changes trainingData, integrations` | Zapisuje i odczytuje dane o treningach pozyskane z integracji oraz stan samych integracji. |

## Responsibilities

### Liveness

```text
IntegrationsHandler = ((CheckIntegrations . [SaveIntegrationData] . [IntegrationChanged]) | SupplyRequestedData)^ω
SupplyRequestedData = (IntegrationsRequest . ReadIntegrations . IntegrationsResponse)
```

### Safety

- integrationDataValid = false  =>  integrationDataToSave = NULL
