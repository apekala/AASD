# Raport A — Identyfikacja problemu i koncepcja systemu agentowego wspierającego planowanie treningów

**Przedmiot:** AASD

**Skład zespołu:**

- Antoni Pękała
- Julian Uziembło
- Natalia Prokopiuk
- Franciszek Zarębski

**Repozytorium projektu:** https://github.com/apekala/AASD  

## 1. Cel i zakres projektu

Celem projektu jest opracowanie systemu agentowego wspierającego osoby amatorsko uprawiające sport w tworzeniu planów treningowych, dostosowywaniu ich do zmieniających się możliwości oraz ocenie realizacji założonych celów. System ma uwzględniać informacje przekazywane przez użytkownika, historię aktywności oraz dane z udostępnionych źródeł, takich jak kalendarz czy aplikacja monitorująca treningi.

Projekt dotyczy również procesu uczenia się: poznawania zasad treningu, rozumienia zależności między jego elementami oraz podejmowania świadomych decyzji dotyczących dalszego rozwoju. Proponowane rozwiązanie ma nie tylko przedstawiać plan, lecz także wyjaśniać przyczyny jego zmian i wskazywać informacje, na których oparto rekomendacje.

Niniejszy raport przedstawia wybór obszaru badania, wyniki trzech wywiadów, analizę problemów, porównanie możliwych rozwiązań oraz koncepcję systemu wieloagentowego. Architektura i plan walidacji opisane w dalszej części są propozycjami do realizacji. Skuteczność rozwiązania nie została jeszcze zweryfikowana.

## 2. Wybór obszaru badania

Zespół tworzy czterech studentów informatyki drugiego stopnia, posiadających wcześniejsze wykształcenie z zakresu inżynierii internetu rzeczy i telekomunikacji. Wszyscy członkowie zespołu pracują jako programiści.

Podczas wstępnej dyskusji wskazaliśmy sytuacje, w których sami zdobywamy wiedzę i rozwijamy umiejętności:

- wdrażanie się do nowych projektów w pracy;
- naukę języków obcych, między innymi z wykorzystaniem Duolingo;
- naukę w ramach studiów;
- poznawanie nowych dyscyplin sportowych i rozwijanie umiejętności ruchowych.

Zdecydowaliśmy się dokładniej zbadać ostatni z wymienionych obszarów. Mamy dostęp do osób uprawiających sport amatorsko oraz do instruktora, co umożliwia zebranie informacji zarówno z perspektywy osoby uczącej się, jak i osoby prowadzącej naukę. Do potencjalnych rozmówców należą również studenci, współpracownicy i członkowie rodzin zespołu.

## 3. Badanie potrzeb i zebrane obserwacje

Przeprowadziliśmy trzy wywiady dotyczące nauki i rozwijania umiejętności sportowych: samodzielnego rozpoczęcia biegania, nauki jazdy na nartach oraz nauki gry w padla. Rozmowy miały charakter rozpoznawczy. Ich celem było poznanie konkretnych trudności, sposobów radzenia sobie z nimi i konsekwencji dla procesu nauki.

Poniższe opisy stanowią syntezę relacji rozmówców. Nie są wynikami pomiarów sprawności ani niezależnej oceny jakości ich treningu.

### 3.1. Wywiad 1 — Samodzielna nauka biegania

**Profil rozmówczyni i kontekst.** Osoba rozpoczynająca bieganie, która próbowała samodzielnie przygotować plan treningowy i połączyć jego realizację z pracą oraz innymi obowiązkami.

**Przebieg i trudności.** Pierwszy plan powstał z pomocą ChatGPT oraz koleżanki, która amatorsko biega i ukończyła półmaraton. Największa trudność pojawiła się wtedy, gdy dostępny czas przestał wystarczać na realizację wszystkich zaplanowanych treningów. Rozmówczyni musiała samodzielnie zdecydować, które jednostki pominąć. Kierowała się własnym wyczuciem i nie konsultowała tych zmian z bardziej doświadczoną osobą.

Nie miała wystarczającej wiedzy, aby ocenić wpływ takiej modyfikacji na realizację celu. W rozmowie pojawiły się również trudności ze zrozumieniem zależności między częstotliwością i intensywnością treningów, odpoczynkiem, dietą oraz ryzykiem kontuzji. Ważnym źródłem motywacji było wsparcie koleżanki.

**Interpretacja zespołu.** Wywiad wskazuje na trudność w aktualizowaniu planu po zmianie dostępności czasowej oraz na niepewność dotyczącą konsekwencji podejmowanych decyzji. Stanowi bezpośrednią przesłankę do zbadania potrzeby wsparcia w dostosowywaniu treningów.

### 3.2. Wywiad 2 — Nauka jazdy na nartach

**Profil rozmówcy i kontekst.** Instruktor narciarstwa uczący dzieci i dorosłych w różnym wieku. Większość jego uczniów stanowią dzieci do 12. roku życia.

**Przebieg i trudności.** Rozmówca wskazał, że sposób prowadzenia nauki wymaga dostosowania do wieku, umiejętności i motywacji ucznia. W jego doświadczeniu małe dzieci dobrze reagują na naukę przez zabawę, natomiast dorośli potrzebują dokładniejszego wyjaśnienia celu ćwiczeń.

Istotną przeszkodą są wcześniej utrwalone nawyki. Ich zmiana może wymagać powrotu do podstaw i stopniowego zwiększania trudności zadań. Instruktor opisywał także zniechęcenie uczniów, zwłaszcza nastolatków, gdy przez dłuższy czas nie zauważają postępów. Kolejną trudnością jest niewłaściwie dobrany sprzęt, który powoduje dyskomfort i utrudnia naukę.

**Interpretacja zespołu.** Wywiad wskazuje na znaczenie indywidualizacji procesu nauki, stopniowania trudności i informacji zwrotnej. Nie stanowi bezpośredniego dowodu na problem samodzielnego układania planów, ale pokazuje czynniki, które mogą wpływać na ich dopasowanie do użytkownika.

### 3.3. Wywiad 3 — Samodzielna nauka gry w padla

**Profil rozmówcy i kontekst.** Początkujący gracz padla, mający wcześniejsze doświadczenie w tenisie i squashu. Uczy się ze znajomymi, którzy również rozpoczynali naukę od podstaw. Rozwija także własny projekt trackera do padla.

**Przebieg i trudności.** Początkowo największą trudność sprawiały dobór siły uderzenia i przewidywanie odbicia piłki od ściany. Regularna gra pomogła rozmówcy oswoić się z zachowaniem piłki, jednak później przestał zauważać postępy. Łączył to z nawykami przeniesionymi z tenisa, zwłaszcza ze zbyt mocnymi i nieodpowiednimi dla padla uderzeniami.

Rozmówca korzystał z materiałów na YouTubie i Instagramie. Filmy prezentowały wzorzec techniki, lecz nie pozwalały mu ocenić, na ile jego własne ruchy odpowiadają temu wzorcowi. Znajomi również dopiero się uczyli, dlatego nie stanowili wiarygodnego źródła informacji zwrotnej. Rozmówca deklarował zamiar skorzystania z pomocy instruktora.

**Interpretacja zespołu.** Wywiad wskazuje na trudność w samodzielnej ocenie umiejętności i ustalaniu kolejnych kroków nauki. Opisany brak postępów jest subiektywną oceną rozmówcy; nie został potwierdzony pomiarem ani oceną instruktora.

### 3.4. Synteza wyników i ograniczenia badania

Zebrany materiał pozwolił wyróżnić następujące trudności:

| Problem | Podstawa w wywiadach | Zakres wniosku |
|---|---|---|
| Dostosowanie treningów do zmieniających się możliwości | Samodzielne pomijanie treningów przez rozmówczynię rozpoczynającą bieganie | Bezpośrednio opisany przypadek; częstotliwość w szerszej grupie wymaga zbadania |
| Ocena własnych umiejętności i postępów | Relacja gracza padla oraz doświadczenia instruktora narciarstwa | Przesłanka dotycząca znaczenia informacji zwrotnej |
| Ustalenie kolejnych kroków rozwoju | Niepewność przy zmianie planu biegania i przy dalszej nauce padla | Wstępne ustalenie problemu |
| Rozumienie zależności między elementami treningu | Rozmowa dotycząca biegania | Problem rozpoznany w jednym wywiadzie |
| Ocena przydatności i wiarygodności materiałów | Korzystanie z ChatGPT i materiałów wideo; brak indywidualnej informacji zwrotnej | Wymaga dalszego badania; samo korzystanie z tych źródeł nie świadczy o ich niskiej jakości |
| Dobór sprzętu | Doświadczenia instruktora narciarstwa | Problem istotny w opisanym kontekście, bez potwierdzenia we wszystkich dyscyplinach |

W notatkach pojawił się również temat szukania instruktora lub lekcji dopasowanych do potrzeb. Traktujemy go jako kierunek dalszych pytań, ponieważ zebrany materiał nie pozwala jeszcze określić skali tej trudności.

Badanie obejmuje niewielką i zróżnicowaną grupę. Perspektywa instruktora różni się od perspektywy osoby trenującej samodzielnie, a poszczególne dyscypliny mają odmienne wymagania. Wywiady pozwalają sformułować hipotezy, lecz nie potwierdzają jeszcze powszechności problemu ani skuteczności proponowanego rozwiązania.

## 4. Porównanie problemów i wybór kierunku projektu

Do dalszej analizy wybraliśmy trzy kierunki: wyszukiwanie wiarygodnej wiedzy, planowanie i dostosowywanie treningów oraz analizę zależności między elementami treningu.

Porównaliśmy je według sześciu kryteriów. Oceny w skali od 1 do 5 są ocenami zespołu, służącymi uporządkowaniu dyskusji. Nie są wynikami badania ilościowego. Wyższa wartość oznacza kolejno: większą częstotliwość lub dotkliwość problemu, bardziej kosztowne albo niewystarczające obejścia, lepszy dostęp do badanych, łatwiejszą walidację lub większy potencjał zastosowania agenta.

| Kryterium | Wyszukiwanie wiarygodnych źródeł wiedzy | Planowanie i dostosowywanie treningów | Analiza zależności między elementami treningu |
|---|---:|---:|---:|
| Częstotliwość | 4 | 5 | 3 |
| Dotkliwość | 3 | 4 | 3 |
| Niewystarczalność obecnych obejść | 3 | 4 | 5 |
| Dostęp do użytkowników | 5 | 5 | 4 |
| Możliwość przeprowadzenia testu | 4 | 2 | 1 |
| Potencjał zastosowania agenta | 3,5 | 4 | 3 |
| **SUMA** | 22,5 | 24 | 19 |

**Wyszukiwanie wiarygodnych źródeł wiedzy.** Można stosunkowo szybko przygotować test wyszukiwania i prezentowania informacji. Trudnością pozostaje jednak ocena jakości znalezionych treści, do której zespół może potrzebować wsparcia specjalisty.

**Planowanie i dostosowywanie treningów.** Ten kierunek łączy tworzenie planu z reagowaniem na zmiany w dostępności, realizacji treningów i sytuacji użytkownika. Obecne obejścia wymagają samodzielnej wiedzy albo dostępu do bardziej doświadczonej osoby. Główną trudnością jest ocena jakości planów i ich długoterminowych efektów.

**Analiza zależności między elementami treningu.** Kierunek jest powiązany z planowaniem, ale wymaga ustalenia, jakie dane są niezbędne i jak mierzyć wpływ poszczególnych czynników. W ramach krótkiego badania trudno oddzielić te zależności od innych przyczyn zmian wyników.

Na podstawie dyskusji, jako problem do rozwiązania wybraliśmy **planowanie treningów i dostosowywanie ich do aktualnych możliwości użytkownika**. Uznaliśmy go za warty rozwiązania ze względu na opisany przypadek trudności, dostęp do potencjalnych użytkowników i możliwość zastosowania procesu iteracyjnego. Wybór ma charakter wstępny i wymaga dalszej walidacji.

### 4.1. Opis wybranego problemu

Osoby amatorsko uprawiające sport, które samodzielnie organizują treningi, mogą mieć trudność z opracowaniem planu odpowiadającego ich celom oraz z aktualizowaniem go po zmianie dostępności czasowej, wykonaniu treningów w inny sposób niż zaplanowano lub zmianie samopoczucia. Brak wiedzy o zależnościach między elementami treningu utrudnia im ocenę konsekwencji takich decyzji.

Bezpośrednią przesłanką jest wywiad dotyczący biegania. Pozostałe rozmowy uzupełniają obraz o znaczenie indywidualizacji, informacji zwrotnej i rozpoznawania kolejnych kroków rozwoju. Zakładamy, że potrzeba wsparcia może występować także w innych dyscyplinach, ale zakres tego uogólnienia wymaga sprawdzenia.

## 5. Porównanie możliwych rozwiązań

### 5.1. Rozwiązanie bez AI

Użytkownik wypełnia formularz dotyczący celu, poziomu zaawansowania i dostępnego czasu. Program dobiera plan z wcześniej przygotowanego zbioru, ewentualnie dostosowując jego parametry według zdefiniowanych reguł.

Zaletą jest możliwość dokładnej kontroli treści planów i reguł ich doboru. Rozwiązanie wymaga jednak wcześniejszego przygotowania materiałów przez specjalistów. Zakres obsługiwanych dyscyplin i sytuacji zależy od opracowanej bazy, a reagowanie na nietypowe zmiany wymaga rozbudowanych reguł.

### 5.2. Rozwiązanie z pojedynczym modelem językowym

Model prowadzi rozmowę z użytkownikiem, zbiera informacje i proponuje plan lub jego modyfikację. Może także odpowiadać na pytania na podstawie przygotowanej bazy materiałów dotyczących treningu.

Takie rozwiązanie zapewnia elastyczny interfejs i może reagować na opisane zmiany. Samo wykorzystanie pojedynczego modelu nie wyklucza personalizacji. W najprostszym wariancie utrzymanie historii, pobieranie danych z wielu źródeł oraz kontrola zgodności kolejnych zmian wymagają jednak dodatkowych mechanizmów.

### 5.3. Rozwiązanie wieloagentowe

System koordynuje zbieranie informacji o użytkowniku, pozyskiwanie wiedzy, tworzenie planu, sprawdzanie proponowanych zmian i analizowanie jego realizacji. Korzysta z ankiet oraz udostępnionych źródeł danych, takich jak kalendarz, historia aktywności i dane z urządzenia sportowego.

Potencjalną zaletą jest jawny podział odpowiedzialności oraz możliwość wielokrotnego wykonywania kolejnych kroków po pojawieniu się nowych informacji. Rozwiązanie jest bardziej złożone, a sam podział na agentów nie gwarantuje wyższej jakości. Jego zasadność powinna zostać oceniona w porównaniu z prostszym wariantem.

## 6. Koncepcja proponowanego systemu

### 6.1. Działania użytkownika

Użytkownik korzysta z prostego interfejsu webowego, w którym:

- określa cel treningowy, dyscyplinę i poziom zaawansowania;
- podaje dostępny czas oraz informacje o aktualnych możliwościach;
- przegląda proponowany plan i uzasadnienie najważniejszych decyzji;
- odpowiada na krótkie ankiety dotyczące realizacji treningów i samopoczucia;
- zgłasza zmiany ograniczające realizację planu;
- może udostępnić kalendarz i podłączyć źródło danych o aktywności, np. aplikację treningową lub urządzenie sportowe.

### 6.2. Działania systemu

System zbiera informacje o użytkowniku, wyszukuje odpowiednie materiały dotyczące metod treningowych i przygotowuje propozycję planu. Następnie porównuje założenia z historią realizacji oraz reaguje na nowe informacje.

W przypadku zmiany dostępności, pominięcia treningu lub zgłoszenia trudności system proponuje aktualizację planu. Wyjaśnia, co zostało zmienione i dlaczego. Jeśli dane są niewystarczające lub sprzeczne, zadaje pytania uzupełniające zamiast zakładać brakujące informacje.

Koncepcja obejmuje również analizę postępów i obciążenia na podstawie dostępnych danych. Zakres i wiarygodność tych analiz zależą od jakości źródeł oraz przyjętych metod, dlatego wymagają osobnej weryfikacji.

### 6.3. Wpływ na proces uczenia się

System ma ułatwiać przejście od ogólnych materiałów o treningu do decyzji odnoszących się do konkretnej sytuacji użytkownika. Uzasadnienia zmian powinny pomagać zrozumieć rolę regularności, intensywności, odpoczynku i stopniowania trudności.

Oczekiwaną korzyścią jest ograniczenie czasu potrzebnego na przygotowanie i aktualizowanie planu oraz zwiększenie zrozumienia decyzji treningowych. Poprawa efektywności treningu pozostaje zakładanym efektem długoterminowym, którego nie można potwierdzić samym testem makiety.

### 6.4. Uzasadnienie zastosowania agentów

Agentowy charakter rozwiązania wynika z realizacji procesu wieloetapowego: zebrania kontekstu, rozpoznania brakujących danych, wykorzystania narzędzi, opracowania zmiany, sprawdzenia jej zgodności z ograniczeniami oraz ponowienia procesu po otrzymaniu informacji zwrotnej.

Przykładowo, po opuszczeniu treningu system powinien sprawdzić aktualny plan i dostępność użytkownika, ustalić znaczenie brakującej aktywności, przygotować wariant modyfikacji i przedstawić jego uzasadnienie. Podział odpowiedzialności pomiędzy agentów ma umożliwiać niezależną ocenę tych etapów i ułatwiać diagnozowanie błędów.

## 7. Proponowana architektura rozwiązania

Poniższa architektura stanowi propozycję realizacji koncepcji. Nie opisuje już zaimplementowanych komponentów.

### 7.1. Komponenty i odpowiedzialności

| Komponent | Odpowiedzialność |
|---|---|
| Interfejs webowy | Zbieranie informacji, prezentacja planu i jego zmian, ankiety po treningu oraz wyświetlanie uzasadnień |
| Warstwa aplikacyjna i integracje | Obsługa żądań, pobieranie danych z udostępnionych źródeł i przekazywanie ich do procesu agentowego |
| Agent koordynujący | Rozpoznawanie rodzaju zadania, ustalanie kolejności działań, zlecanie pracy innym agentom i obsługa brakujących informacji |
| Agent wiedzy treningowej | Wyszukiwanie materiałów odpowiednich do dyscypliny i celu, porządkowanie informacji oraz zachowywanie odwołań do źródeł |
| Agent planowania | Tworzenie i modyfikowanie planu na podstawie celu, ograniczeń, historii oraz informacji przygotowanych przez agenta wiedzy |
| Agent oceny i monitorowania | Porównywanie planu z realizacją, identyfikowanie rozbieżności oraz sprawdzanie propozycji pod kątem zdefiniowanych ograniczeń |
| Baza danych | Przechowywanie profilu, planów i ich wersji, historii aktywności, odpowiedzi na ankiety oraz uzasadnień zmian |

Sprawdzanie przez agenta oceny powinno zostać uzupełnione regułami programistycznymi tam, gdzie ograniczenia dają się jednoznacznie zapisać, np. przy kontroli dostępnych dni i czasu. Ocena wykonana przez kolejny model językowy nie jest niezależnym potwierdzeniem poprawności treningowej. Ponadto, kluczowa pod kątem zdrowia fizycznego i psychicznego użytkownika praca agentów, jak np. ustalanie ilości treningów, powinna być szczególnie dogłębnie sprawdzana na różne dostępne sposoby, aby nie powodować negatywnych konsekwencji.

### 7.2. Przepływ działania

1. Użytkownik określa cel, możliwości i dostępność, a system zapisuje jego profil.
2. Agent koordynujący sprawdza kompletność informacji i w razie potrzeby zadaje pytania.
3. Agent wiedzy przygotowuje informacje i źródła potrzebne do opracowania planu.
4. Agent planowania tworzy propozycję, którą sprawdzają agent oceny oraz reguły systemowe.
5. Użytkownik otrzymuje plan wraz z uzasadnieniem. Zaakceptowana wersja jest zapisywana.
6. Ankiety i podłączone źródła dostarczają informacji o realizacji treningów i zmianach sytuacji.
7. System ocenia potrzebę aktualizacji. Propozycja zmiany przechodzi ponownie przez etap planowania i sprawdzania, a następnie jest przedstawiana użytkownikowi.

Wersjonowanie pozwoli porównać kolejne plany i odtworzyć przyczyny ich modyfikacji. Integracje mają dostarczać danych za zgodą użytkownika; propozycja architektury nie zakłada automatycznego uzyskania dostępu do wszystkich wymienionych źródeł.

### 7.3. Ryzyka i ograniczenia

Najważniejszym ryzykiem jest wygenerowanie planu nieskutecznego albo niedopasowanego do możliwości użytkownika. Źródłem błędów mogą być niewiarygodne materiały, niepełne dane, błędna interpretacja historii lub nieprawidłowa rekomendacja modelu.

System powinien wskazywać niepewność i ograniczenia posiadanych informacji. Zgłoszenie kontuzji lub choroby nie może być traktowane jako wystarczająca podstawa do automatycznego określania bezpiecznego powrotu do treningu. W takich przypadkach potrzebne są jasno określone granice działania systemu i konsultacja specjalisty.

Dodatkowym wyzwaniem jest zróżnicowanie dyscyplin sportowych. Weryfikacja rozwiązania powinna rozdzielać zgodność planu z ograniczeniami użytkownika, jego zrozumiałość i preferencje badanych od oceny poprawności merytorycznej oraz rzeczywistych efektów treningu.

## 8. Hipotezy do weryfikacji

**Hipoteza problemowa.** Osoby amatorsko uprawiające sport, które samodzielnie organizują treningi, doświadczają trudności w tworzeniu planu, aktualizowaniu go po zmianie warunków i ocenie konsekwencji takich zmian. Będziemy ją dalej badać poprzez pytania o ostatnie rzeczywiste sytuacje, podjęte decyzje i obecne sposoby radzenia sobie z trudnością.

**Hipoteza wartości rozwiązania.** W zadaniu wymagającym dostosowania planu do zmienionych warunków większość badanych będzie preferowała propozycję przygotowaną z pomocą systemu względem modyfikacji opracowanej samodzielnie. Preferencję uzupełnimy oceną uzasadnienia wyboru, czasu wykonania zadania i zgodności zmiany z podanymi ograniczeniami.

Preferencja użytkowników będzie sygnałem dotyczącym postrzeganej wartości rozwiązania. Nie będzie dowodem jego przewagi treningowej ani bezpieczeństwa planów.

## 9. Proponowany plan testu

Test nie został jeszcze przeprowadzony. Poniższe liczebności, zadania i progi są propozycją do ustalenia przed rekrutacją i zebraniem wyników.

### 9.1. Uczestnicy

Proponujemy udział ośmiu osób amatorsko uprawiających sport, które samodzielnie organizują przynajmniej część swoich treningów. Podczas rekrutacji ustalimy ich dyscypliny, doświadczenie i obecny sposób planowania. Różnice te uwzględnimy przy interpretacji wyników; tak mała próba nie pozwoli na osobne wnioski dla każdej dyscypliny.

### 9.2. Metoda i zadanie

Wykorzystamy prostą makietę aplikacji lub prototyp z przygotowanym planem wyjściowym odpowiednim do danego scenariusza. Zmiana planu może być generowana przez model językowy, bez wcześniejszego budowania pełnej architektury i wszystkich integracji. Taki test pozwala sprawdzić koncepcję interakcji, ale nie dowodzi jeszcze przewagi systemu wieloagentowego.

Przebieg testu:

1. Uczestnik opisuje ostatnią sytuację, w której musiał zmienić treningi, oraz sposób podjęcia decyzji.
2. Otrzymuje plan wyjściowy i konkretną zmianę warunków, np. utratę jednego dostępnego dnia. Samodzielnie proponuje modyfikację i wyjaśnia decyzję.
3. Wprowadza te same informacje do prototypu, odpowiada na pytania uzupełniające i przegląda propozycję systemu wraz z uzasadnieniem.
4. Porównuje oba warianty. Może wskazać plan własny, propozycję systemu albo brak preferencji, a następnie wyjaśnia wybór.
5. Odpowiada na pytania dotyczące zrozumiałości, zaufania i trudności napotkanych w zadaniu.

Scenariusz nie będzie wymagał wykonywania zaproponowanych treningów. Dane z kalendarza, urządzeń czy aplikacji śledzących kondycję fizyczną użytkownika oraz przebieg treningu, mogą być symulowane na potrzeby zadania.

### 9.3. Pytania po zadaniu

- Co wpłynęło na wybór danego planu lub brak preferencji?
- Które zmiany były zrozumiałe, a które wymagały dodatkowego wyjaśnienia?
- Jakich informacji zabrakło przed podjęciem decyzji?
- Na ile ufasz propozycji i co mogłoby zwiększyć albo zmniejszyć to zaufanie?
- Co sprawiło trudność podczas korzystania z prototypu?
- W jakiej rzeczywistej sytuacji skorzystałbyś lub skorzystałabyś z takiej pomocy?
- Jakie zmiany system mógłby proponować samodzielnie, a które powinny wymagać Twojej akceptacji?

### 9.4. Metryki i kryteria interpretacji

Głównym metryką zasadności proponowanego rozwiązania będzie wybór uczestnika wraz z uzasadnieniem. Dodatkowo, zapiszemy czas samodzielnej modyfikacji i pracy z prototypem, zgodność wariantów z ograniczeniami scenariusza oraz ocenę zrozumiałości i zaufania w skali 1–5. Kolejność etapów może wpływać na czas, dlatego pomiar ten będzie miał charakter pomocniczy.

Proponujemy następujące kryteria ustalone przed badaniem:

- **Wynik wspierający hipotezę wartości:** co najmniej pięć z ośmiu osób preferuje propozycję systemu.
- **Wynik podważający hipotezę wartości:** co najmniej pięć z ośmiu osób preferuje własną modyfikację.
- **Wynik niejednoznaczny:** żaden z powyższych warunków nie jest spełniony, w tym w sytuacji licznych odpowiedzi bez preferencji.

Naruszenie jawnych ograniczeń scenariusza będzie rejestrowane jako błąd niezależnie od preferencji uczestnika. Ocena jakości treningowej wymaga dodatkowej konsultacji z osobą posiadającą odpowiednie kompetencje.

### 9.5. Ograniczenia testu

Wynik będzie zależał od jakości przygotowanego planu, scenariusza, modelu i interfejsu. Mała, dogodnościowa próba ogranicza możliwość uogólnienia. Uczestnicy mogą kierować się sposobem prezentacji lub szczegółowością uzasadnienia, a nie jakością samego planu. Porównanie po samodzielnym wykonaniu zadania może także wpływać na ich późniejsze zachowanie.

Test pozwoli ocenić postrzeganą przydatność i użyteczność koncepcji w określonym zadaniu. Nie pozwoli potwierdzić poprawy wyników sportowych, długoterminowej regularności ani bezpieczeństwa planów.

### 9.6. Dalsze działania

**Po wyniku pozytywnym** przejdziemy do implementacji i kolejnych testów prototypu, uwzględniając błędy oraz uwagi uczestników. Oddzielnie zaplanujemy ocenę jakości planów i porównanie architektury wieloagentowej z prostszym rozwiązaniem.

**Po wyniku negatywnym** przeanalizujemy, czy przyczyną była mała istotność problemu, jakość propozycji, brak zaufania czy sposób interakcji. Wyniku nie będziemy traktować wyłącznie jako argumentu za zmianą rozwiązywanego problemu.

**Po wyniku niejednoznacznym** doprecyzujemy niepewne założenia i zaplanujemy kolejny test. Jeśli zmienimy scenariusz, sposób generowania planu lub kryteria oceny, potraktujemy to jako nowe badanie i ustalimy jego zasady przed zebraniem kolejnych wyników.

## 10. Stan prac i kolejne kroki

Dotychczas wybraliśmy obszar badania, przeprowadziliśmy trzy wywiady, uporządkowaliśmy problemy i porównaliśmy możliwe kierunki projektu. Wybraliśmy planowanie oraz dostosowywanie treningów i opisaliśmy koncepcję rozwiązania. W niniejszym raporcie przedstawiamy również propozycję architektury oraz plan pierwszej walidacji.

Kolejne kroki obejmują ustalenie scenariuszy i kryteriów testu, przygotowanie prototypu, rekrutację uczestników oraz zebranie wyników. Najważniejszym zadaniem pozostaje sprawdzenie, czy proponowane wsparcie odpowiada na rzeczywistą trudność użytkowników i czy uzasadnia dalszą implementację systemu.
