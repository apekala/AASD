# Karta roli GAIA: Pozyskiwacz wiedzy o sporcie

**Role Schema:** `SportKnowledgeCollector`

## Description

Pozyskuje, ocenia i przechowuje wiedzę treningową dotyczącą dyscypliny i celu użytkownika. Udostępnia Koordynatorowi i Planerowi informacje ze źródłami oraz ograniczeniami. Realizuje RF-04 i wspiera RF-05 oraz RF-06 opisane w [wymaganiach funkcjonalnych](../wymagania_funkcjonalne.md).

## Protocols and Activities

### Protokoły i fazy interakcji

| Nazwa | Opis |
| --- | --- |
| `GetSportKnowledge` | Koordynator lub Planer → Pozyskiwacz wiedzy o sporcie: pytanie z dyscypliną i celem treningowym. |
| `ReturnSportKnowledge` | Pozyskiwacz wiedzy o sporcie → inicjator zapytania: odpowiedź ze źródłami i ograniczeniami albo informacja o braku wystarczającej wiedzy lub błędzie. Zamyka interakcję GetSportKnowledge. |

### Aktywności lokalne

| Nazwa | Opis |
| --- | --- |
| <u>ReadKnowledge</u> | Sprawdza parametry i wyszukuje w bazie wiedzę pasującą do pytania; ocenia jej kompletność i aktualność. |
| <u>CheckRefreshDue</u> | Sprawdza termin okresowej aktualizacji; jeden termin uruchamia jedno odświeżenie. |
| <u>RefreshKnowledge</u> | Złożona aktywność: wyszukanie materiałów, ich ocena i ewentualna aktualizacja bazy; kończy się wynikiem odświeżenia. |
| <u>SearchSources</u> | Wyszukuje publikacje naukowe i materiały specjalistów. Internet jest zasobem środowiska. |
| <u>EvaluateSources</u> | Ocenia autorstwo, datę i przydatność materiałów; wyodrębnia informacje wraz ze źródłami, rozbieżnościami i ograniczeniami. |
| <u>UpdateKnowledge</u> | Zapisuje zaakceptowaną wiedzę ze źródłami, oceną materiałów, zakresem zastosowania i datą sprawdzenia. |
| <u>BuildKnowledgeResponse</u> | Przygotowuje odpowiedź i wskazuje ograniczenia, brak wiedzy lub przyczynę błędu. |

## Permissions

| Pozwolenie | Zakres |
| --- | --- |
| `reads supplied sport, trainingGoal, question` | Dyscyplina, cel treningowy i pytanie inicjatora. |
| `reads sourceMaterials, knowledgeSettings` | Materiały źródłowe oraz ustawienia zakresu, aktualności, harmonogramu i limitu czasu wyszukiwania. |
| `changes sportKnowledge` | Odczyt i aktualizacja bazy wiedzy treningowej wraz ze źródłami i ograniczeniami. |
| `generates knowledgeResponse, sourceReferences, refreshResult` | Odpowiedź, odwołania do materiałów i wynik próby odświeżenia. |

## Responsibilities

### Liveness

```text
SportKnowledgeCollector = (KnowledgeTask | RefreshTask)^ω
KnowledgeTask = GetSportKnowledge . ReadKnowledge . (BuildKnowledgeResponse | (RefreshKnowledge . BuildKnowledgeResponse)) . ReturnSportKnowledge
RefreshTask = CheckRefreshDue . RefreshKnowledge
RefreshKnowledge = SearchSources . EvaluateSources . [UpdateKnowledge]
```

- `KnowledgeTask` oznacza obsługę jednego zapytania, a `RefreshTask` — jednego okresowego odświeżenia. Zakres okresowej aktualizacji wynika z ustawień.
- Gdy baza wystarcza, po `ReadKnowledge` wykonywane jest `BuildKnowledgeResponse`. Przy poprawnym zapytaniu i niepełnej lub nieaktualnej wiedzy obowiązkowo poprzedza je `RefreshKnowledge`. Niepoprawne parametry prowadzą bezpośrednio do przygotowania odpowiedzi z błędem.
- `UpdateKnowledge` jest obowiązkowe, gdy uzyskano zaakceptowane informacje, i pomijane w pozostałych przypadkach. Brak materiałów lub błąd kończy próbę bez dopisywania zastępczych treści. Każde zapytanie otrzymuje odpowiedź, również przy niewystarczającej wiedzy.

### Safety

- Zapis do sportKnowledge ⇒ ocenione źródła wskazane w sourceReferences, zakres zastosowania i data sprawdzenia.
- knowledgeResponse odpowiada sport, trainingGoal i question; brak podstaw, sprzeczności oraz nieaktualność materiałów są jawne.
- Błąd wyszukiwania lub zapisu ⇒ zachowanie poprzedniej zawartości sportKnowledge i jej dat sprawdzenia.
