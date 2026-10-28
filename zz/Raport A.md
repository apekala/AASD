# Raport A: Identyfikacja problemu (0-5 pkt.)  
Powinien zawierać:

- **identyfikację i opis problemu, propozycję i sprecyzowanie rozwiązania oraz słowny opis koncepcji systemu** - ta część jest realizowana przez raport wygenerowany po zajęciach, 
- **proponowaną architekturę rozwiązania** - o to należy rozszerzyć opis
- **Proszę podać link do publicznego repozytorium kodu (np. git) w którym będziecie zamieszczać kod systemu.**

--- 

# Etap 1

Jesteśmy grupą 4 studentów drugiego stopnia informatyki, z różnym wcześniejszym wykształceniem - inżynieria internetu rzeczy i telekomunikacja. Wszyscy pracujemy jako programiści. Grupy do których możemy dotrzeć w ciągu tygodnia to głównie studenci z naszego kierunku, studenci architektury i medycyny, a także współpracownicy i rodzina. Z dyskusji wynikło, ze obszary w których najczęściej się uczymy to:
- praca, np. przy wdrażaniu się do nowego projektu,
- języki, głownie przez Duolingo,
- studia,
- nauka nowych sportów.
Zdecydowaliśmy dokładniej zbadać ostatni obszar.

# Etap 2
Przeprowadziliśmy 3 wywiady z różnymi osobami.

### Wywiad 1 - Samodzielna nauka biegania
#### Osoba
Osoba zaczynająca przygodę z bieganiem, która próbowała samodzielnie przygotować plan treningowy i pogodzić go z pracą oraz innymi obowiązkami.

#### Obserwacje
Pierwszy plan treningowy ułożyła przy użyciu czatu GPT oraz z pomocą koleżanki, która amatorsko zajmuje się bieganiem i przebiegła półmaraton. Największą trudnością okazało się dostosowanie planu do zmieniających się ograniczeń czasowych i połączenie regularnych treningów z pracą. Rozmówczyni musiała samodzielnie zdecydować, które treningi pominąć. Nie miała jednak wystarczającej wiedzy, aby ocenić, jak ograniczyć negatywny wpływ tej decyzji na efekty treningu. Nie konsultowała jej również z bardziej doświadczoną osobą. Innym problemem była trudność w zrozumieniu zależności pomiędzy poszczególnymi elementami treningu, takimi jak częstotliwość i intensywność ćwiczeń, odpoczynek, dieta oraz ryzyko kontuzji. W motywacji do treningu bardzo pomogło wsparcie koleżanki. 

### Wywiad 2 – Nauka jazdy na nartach

#### osoba
Instruktor narciarstwa uczący dzieci i dorosłych w różnym wieku. Większość jego uczniów stanowią dzieci do 12. roku życia.

#### obserwacje
Sposób nauki jazdy na nartach musi być dostosowany do wieku, umiejętności i motywacji ucznia. Małe dzieci najlepiej uczą się poprzez zabawę, natomiast dorośli potrzebują dokładnego i merytorycznego wyjaśnienia wykonywanych ćwiczeń. Dużym problemem są wcześniej utrwalone nawyki. Ich zmiana wymaga powrotu do podstaw i powolnego wprowadzania trudniejszych ćwiczeń. Uczniowie, szczególnie nastolatkowie, łatwo zniechęcają się, gdy przez dłuższy czas nie widzą postępów. Proces nauki utrudnia również źle dobrany sprzęt. Powoduje on dyskomfort, spowalnia rozwój i może całkowicie zniechęcić dziecko do dalszej jazdy.

### Wywiad 3 – Samodzielna nauka gry w padla

#### osoba
Początkujący gracz padla, który wcześniej grał w tenisa i squasha. Uczy się razem ze znajomymi, którzy również zaczynali od zera. Rozwija także własny projekt trackera do padla.

#### obserwacje
Na początku największą trudnością było dobranie odpowiedniej siły uderzenia oraz przewidywanie, w jaki sposób piłka odbije się od ściany. Regularna gra pozwoliła mu szybko przyzwyczaić się do zachowania piłki, jednak później przestał zauważać postępy. Przyczyną okazały się nawyki przeniesione z tenisa, szczególnie zbyt mocne i niepoprawne technicznie uderzenia. Rozmówca zaczął uczyć się z filmów na YouTubie i Instagramie. Materiały pokazywały prawidłową technikę, ale nie pozwalały ocenić, jakie błędy sam popełnia. Znajomi nie byli w stanie udzielić mu wiarygodnej informacji zwrotnej, ponieważ sami dopiero się uczyli. Rozmówca planuje skorzystać z pomocy instruktora.

# Etap 3
W wywiadach zidentyfikowaliśmy następujące powtarzające się problemy:
- Trudność w samodzielnej ocenie własnych umiejętności i postępów.
- Brak wiedzy potrzebnej do ustalenia kolejnych kroków treningu.
- Trudność w znalezieniu profesjonalnych źródeł wiedzy. Rozmówcy korzystali głównie z YouTube’a, Instagrama i czatu GPT.
- Problem z przewidywaniem, jak poszczególne elementy planu wpływają na efekty treningu. 
- Trudność w dobraniu odpowiedniego sprzętu.
- Problem ze znalezieniem odpowiedniego instruktora lub lekcji dopasowanych do poziomu i potrzeb ucznia.

# Etap 4
### Trudność w znalzienu profesjonalnych źródeł wiedzy

| Kryterium              | Pytanie pomocnicze                      |
| ---------------------- | --------------------------------------- |
| Częstotliwość          | 4                                       |
| Dotkliwość             | 3                                       |
| Obecne obejścia        | 3                                       |
| Dostęp do użytkowników | 5                                       |
| Możliwość testu        | 4 nie umiemy sami ocenić jakości źródeł |
| Potencjał dla agenta   | 3,5 - wyszukanie i walidacji informacji |
### Planowanie treningu, dostosowanie go do aktualnych możliwości

| Kryterium              | Pytanie pomocnicze                                                                        |
| ---------------------- | ----------------------------------------------------------------------------------------- |
| Częstotliwość          | 5                                                                                         |
| Dotkliwość             | 4                                                                                         |
| Obecne obejścia        | 4 - trzeba znaleźć kogoś kto się zna, możemy nie mieć dostępu do takiej osoby             |
| Dostęp do użytkowników | 5                                                                                         |
| Możliwość testu        | 2 - wymaga długiego badania                                                               |
| Potencjał dla agenta   | 4 - dpoasowauje diząłania na podstawie planu, twoich treningów, chrobry, dancyh z zegarka |

### Analiza zależnosci między różnymi elelmentami treningu

| Kryterium              | Pytanie pomocnicze                                         |
| ---------------------- | ---------------------------------------------------------- |
| Częstotliwość          | 3 - uzupełnienie problemu planu treningów                  |
| Dotkliwość             | 3                                                          |
| Obecne obejścia        | 5                                                          |
| Dostęp do użytkowników | 4                                                          |
| Możliwość testu        | 1 - wymaga długich testów, trudno mierzalne wyniki         |
| Potencjał dla agenta   | 3 - skomplikownay model, nie wiemy jakie dane są potrzebne |

Ze względu na duże zapotrzebowanie, dotkliwość problemu i dobry dostęp do użytkowników zdecydowaliśmy się rozwiązać problem planowania treningów. Największym ryzykiem przy tym temacie jest trudność w ocenie jakości planu treningowego przy testach narzędzia.

# Etap 5
### Bez AI
Program dobiera plan treningowy na podstawie formularza wypełnionego przez użytkownika. Plany są przygotowane wcześniej przez specjalistów i mogą być w pewnym stopniu parametryzowane.

System wymaga wcześniejszego opracowania planów treningowych i działa jedynie dla określonych dyscyplin oraz celów. Przygotowanie planów wymaga zaangażowania wykwalifikowanych specjalistów. Możliwości dostosowania planu do zmieniających się warunków i potrzeb użytkownika są ograniczone. Zaletą tego rozwiązania jest największa kontrola nad poprawnością informacji przekazywanych użytkownikowi.
### Nieagent
Rozwiązanie działa podobnie jak poprzednie, ale wykorzystuje czat z modelem językowym jako dodatkowy interfejs — na przykład rozmowę zamiast tradycyjnego formularza. Model może korzystać z przygotowanej wcześniej bazy sprawdzonych artykułów dotyczących treningu i odpowiadać na jej podstawie na pytania użytkownika. Ograniczenia pozostają zbliżone do rozwiązania bez AI. 

### Agent
System wieloagentowy rozpoznaje potrzeby użytkownika, wyszukuje informacje dotyczące efektywnego treningu w różnych dyscyplinach oraz reaguje na zmiany w jego sytuacji. System ma dostęp do różnych źródeł danych o aktywności użytkownika (kalendarz, dane o treningach, kontuzjach, biometria z zegarka). Z interfejsem webowym prostym.
##### Co robi użytkownik?
- Określa swój cel treningowy.
- Podaje dostępny czas oraz informacje o kondycji.
- Odpowiada na krótkie ankiety dotyczące wykonanych treningów.
- Podłącza źródło danych o treningach, na przykład aplikację do ich monitorowania.
- Udostępnia kalendarz.
##### Co robi system?
- Wyszukuje informacje dotyczące odpowiednich metod treningowych.
- Zbiera dane o użytkowniku z ankiet oraz podłączonych źródeł.
- Układa plan treningowy.
- Dostosowuje plan do zmian w aktywności i sytuacji użytkownika.
- Analizuje postępy treningowe.
- Analizuje obciążenie organizmu.

##### Jak zmienia się obecny sposób uczenia?
- Użytkownik nie musi samodzielnie zdobywać tak szerokiej wiedzy o procesie treningowym.
- Nie musi sam układać całego planu.
- Łatwiej jest mu realizować plan i dostosowywać go do zmieniającej się sytuacji.

##### Jaka jest najważniejsza korzyść?
- Zwiększenie efektywności treningu.
- Ograniczenie czasu poświęcanego na przygotowanie i modyfikowanie planu.

##### Co może pójść źle?
- Plan treningowy może okazać się nieskuteczny lub niebezpieczny.
- System może błędnie zinterpretować dane albo oprzeć zalecenia na niewiarygodnych źródłach.

##### Dlaczego agent może być lepszy niż prostsze rozwiązanie?
- Agent może na bieżąco reagować na zmiany w zachowaniu, kondycji, dostępności i możliwościach użytkownika oraz odpowiednio dostosowywać dalsze działania.

# Etap 6

> [!quote] 
> Wierzymy, że ludzie amatorsko uprawiający sport doświadczają trudności w układaniu planu treningowego, dostosowywaniu go do zmieniających się potrzeb i oceny jego skuteczności. Sprawdzimy to na grupie  sportowców amatorów, przez porównanie zmian w planie wprowadzonych przez badaną osobę ze zmianami zrobionymi przez agenta. Za dowód uznamy deklaracje większości badanych, że wolą nasze plany od swoich. Wynik, to sytuacja w której ludzie w większości wolą plany ułożone przez siebie.

# Etap 7

Coś trzeba wymyśleć...

 ### Plan testu:
- Hipoteza: Ludzie wolą ułożone przez nas testy od ułożonysch samodzielnie. 
- Kogo badamy i dlaczego te osoby: Osoby amatorsko uprawiające sport.
- Metoda: Przedstawienie grupie potencjalnych użytkowników makiety aplikacji z ustalonym na stałe planem. Użytkownik odpowiada na pytania dotyczące treningu i plan jest zmieniany przez LLM na podstawie odpowiedzi użytkownika.
- Pytania / zadanie:
	- Czy aplikacja pomogła Ci w ułożeniu planu?
	- Czy masz zaufanie do tak ułożonego planu?
	- Czy użycie aplikacji było łatwe?
	- Czy chciałbyś aby plan był automatycznie aktualizowany na podstawie twoich treinigów.
	- Co było trudne?
	- Jakie problemy widzisz?
	- Który plan wolisz?
- Jaki wynik wspiera hipotezę: WIększość badanych woli nasz plan.
- Jaki wynik jej przeczy: Większość badanych woli swój plan.
- Ograniczenia testu: Wynik zależy od jakości planu stworzonego przez nas na potrzeby testu.
- Co zrobimy po wyniku pozytywnym, negatywnym lub niejednoznacznym: 
	- pozytywnym: Przystąpimy do implementacji pełnego rozwiązania.
	- negatywnym/niejednoznacznym: Przeanalizujemy odpowiedzi użytkowników, zastanowimy się gdzie leży problem, powtórzymy test w innych warunkach, które określimy na podstawie odpowiedzi badanych (np. z ulepszoną metodą generowania planów lub dokładniejszymi pytaniami).
