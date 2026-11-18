# Karta roli GAIA: UserDataCollector

**Role Schema:** `UserDataCollector`

## Description

Dostarcza wiedzę o użytkowniku i informuje o zmianach jej stanu.

## Protocols and Activities

### Protokoły i fazy interakcji

  -----------------------------------------------------------------------
  Nazwa                               Opis
  ----------------------------------- -----------------------------------
  ReadData                            Odczyt danych użytkownika

  CheckIfDataChanged                  Sprawdzenie, czy dane użytkownika
                                      uległy zmianie

  InformAboutDataChange               Poinformowanie o zmianie danych
                                      użytkownika

  AwaitDataRequest                    Oczekiwanie na żądanie
                                      udostępnienia danych

  SendRequestedData                   Przekazanie żądanych danych
  -----------------------------------------------------------------------

### Aktywności

  ----------------------------------------------------------------------------------
  Nazwa                                          Opis
  ---------------------------------------------- -----------------------------------
  `<u>`{=html}HandleChangedData`</u>`{=html}     Monitorowanie zmian danych
                                                 użytkownika i informowanie o
                                                 wykrytych zmianach

  `<u>`{=html}SupplyRequestedData`</u>`{=html}   Oczekiwanie na żądanie, odczyt
                                                 odpowiednich danych i przekazanie
                                                 ich odbiorcy
  ----------------------------------------------------------------------------------

## Permissions

  -----------------------------------------------------------------------
  Pozwolenie                          Zakres
  ----------------------------------- -----------------------------------
  `reads workoutData, userData`       Odczytuje dane treningowe i dane
                                      użytkownika

  `reads supplied knowledgeType`      Odczytuje przekazany typ wymaganej
                                      wiedzy

  `generates dataChangeInfo`          Generuje informację o zmianie
                                      danych użytkownika
  -----------------------------------------------------------------------

## Responsibilities

### Liveness

``` text
UserDataCollector = (HandleChangedData | SupplyRequestedData)^ω
HandleChangedData    = (CheckIfDataChanged . InformAboutDataChange)^ω
SupplyRequestedData  = (AwaitDataRequest . ReadData . SendRequestedData)^ω
```

### Safety

-   dataChanged = false =\> informationAboutDataChange = NULL
