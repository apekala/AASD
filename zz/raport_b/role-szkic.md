## Role

W ramach zaproponowanego systemu, zostały wyróżnione następujące role i ich aktywności:

* **Koordynator**: podejmowanie kolejnych działań na podstawie analizy, co się dzieje z użytkownikiem, np. po treningu wykonanym -> zlecenie utworzenia ankiety -> dalsza analiza danych; po treningu niewykonanym -> konsultacja agenta wiedzy -> decyzja o dalszym postępowaniu
* **Planer**: generowanie (lub re-generowanie) plan treningu na podstawie danych o użytkowniu, jego kalendarza, jego dodatkowych uwag, itd.
* **Ankieter**: wykonywanie ankiet dla użytkownika, m.in. po treningach
* **Pozyskiwacz wiedzy o sporcie**: pozyskuje wiedzę o sporcie uprawianym przez użytkownika
* **Pozyskiwacz wiedzy o użytkowniku**: zmiana stanu (danych o użytkowniku) -> raport do koordynatora
* **Zarządca integracji**: pozyskiwanie wiedzy o użytkowniku z integracji: aplikacji i/lub urządzeń podłączonych do telefonu użytkownika, m.in. aplikacja Strava lub Google Fit, dane z urządzeń typu Smartwatch, itd.
* **Zarządca kalendarza**: integracja z kalendarzem użytkownika, pozyskiwania danych o planie użytkownika (kiedy pracuje/uczy się, kiedy wykonuje dodatkowe aktywności, itd.), wypełnianie kalendarza planem użytkownika

Jest to architektura hierarchiczna, gdzie koordynator decyduje o kolejnych krokach: wykonanie nowego planu, zlecenie zrobienia ankiety, itd. Kolejne role (Planer, Pozyskiwacze wiedzy o sporcie/użytkowniu) wykonują swoje zadania (same z siebie lub po odpowiednim odpytaniu) i przekazują rezultaty koordynatorowi.

## Aktywności, Protokoły, Pozwolenia
* **Koordynator**:
  - aktywności: 
    - sprawdzanie i analiza stanu użytkownika (szczególnie po treningach)
    - analiza planu: "czy plan potrzebuje zmian?"
    - podejmowanie decyzji: 
  - protokoły:
    - UserKnowledgeChanged: powiadomienie o zmianie stanu wiedzy o użytkowniku
    - CalendarChanged: powiadomienie o zmianie stanu kalendarza
  - pozwolenia:
    - reads plan: odczyt aktualnego planu treningowego
    - reads user knowledge: odczyt aktualnego stanu użytkownika
    - reads sport knowledge: odczyt wiedzy o tym, co może oznaczać dany stan użytkownika
* **Planer**:
  - aktywności: brak
  - protokoły:
    - GeneratePlan: stworzenie lub dostosowanie planu (jeśli plan na wejściu to NULL)
  - pozwolenia:
    - changes plan: zmiana planu treningu użytkownika
    - reads sport knowledge
    - reads supplied user knowledge
* **Ankieter**:
  - aktywności:
    - sporadyczne ankiety samopoczucia użytkownika
  - protokoły:
    - GenerateQuestionnaire: wygeneruj ankietę o podanych parametrach
    - GetSummary: zwrócenie podsumowania rezultatów ankiet
  - pozwolenia:
    - changes user knowledge: zapis danych o użytkowniku pozyskanych z ankiet
* **Pozyskiwacz wiedzy o sporcie**:
  - aktywności:
    - aktualizowanie wiedzy o danym sporcie
  - protokoły:
    - GetSportKnowledge: sprawdzenie konkretnej wiedzy o sporcie
  - pozwolenia:
    - changes sport knowledge: aktualizuje wiedzę o sporcie
* **Pozyskiwacz wiedzy o użytkowniku**:
  - aktywności:
    - aktualizowanie wiedzy o użytkowniku
  - protokoły:
    - GetUserKnowledge: zwrócenie konkretej wiedzy o użytkowniku
    - IntegrationsChanged: powiadomienie o zmianie stanu integracji (dodanie nowej, usunięcie istniejącej)
  - pozwolenia:
    - changes user knowledge: aktualizacja wiedzy o użytkowniku w oparciu o dane z treningów, kalendarz, itd.
* **Zarządca integracji**:
  - aktywności:
    - dodawanie/aktualizacja/usuwanie integracji
    - pobranie i zapisywanie/aktualizacja danych z integracji
  - protokoły:
    - GetIntegrations: zwraca podpięte do aplikacji integracje
  - pozwolenia:
    - changes integrations: zarządzanie integracjami
    - changes training data: aktualizuje dane o treningach
* **Zarządca kalendarza**:
  - aktywności:
    - dodanie/usunięcie kalendarza
  - protokoły:
    - GetFreeTime: zwraca wolny czas w kalendarzu użytkownika
  - pozwolenia:
    - reads calendar: dostęp do kalendarza użytkownika

![](role-diagram.drawio.svg)