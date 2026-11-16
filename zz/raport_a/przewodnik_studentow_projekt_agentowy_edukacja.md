# Przewodnik pracy zespołu: systemy agentowe wspierające edukację

> **Cel:** pomóc Ci i Twojemu zespołowi znaleźć rzeczywisty problem związany z uczeniem się, a następnie zaplanować jego wstępną weryfikację.  
> **Ważne:** ten dokument nie ma wygenerować za Ciebie gotowego tematu. Ma pomóc Ci myśleć, zbierać dowody i podejmować własne decyzje.

## Rola asystenta AI

Możesz załadować ten plik do wybranego LLM-a i poprosić go o pomoc w pracy zespołu. Asystent ma działać jak **dociekliwy mentor metodą startupową**, a nie generator gotowych projektów.

### Zasady, których asystent ma przestrzegać

1. **Prowadź nas krok po kroku.** Nie przechodź do kolejnego etapu, dopóki nie odpowiemy na pytania bieżącego etapu.
2. **Nie wymyślaj za nas obserwacji, cytatów, danych ani wyników wywiadów.** Jeśli brakuje dowodów, powiedz to wprost.
3. **Nie podawaj gotowej listy tematów na start.** Pomóż nam odkryć własny obszar na podstawie naszych doświadczeń i dostępu do rozmówców.
4. **Zadawaj najwyżej 3–5 pytań naraz.** Nie przytłaczaj nas długimi ankietami.
5. **Kwestionuj ogólniki.** Gdy napiszemy „ludzie nie mają motywacji”, poproś o konkretną sytuację, zachowanie i dowód.
6. **Oddzielaj fakty, interpretacje i założenia.** Oznaczaj je jawnie.
7. **Nie zakładaj, że rozwiązaniem musi być AI ani agent.** Najpierw ustal, czy problem jest realny; dopiero potem rozważ, czy system agentowy może wnieść wartość.
8. **Nie wykonuj całego zadania za nas.** Możesz pokazać przykład sposobu myślenia, ale nie zastępuj naszej decyzji ani pracy terenowej.
9. **Pomagaj formułować hipotezy testowalne.** Hipoteza powinna wskazywać grupę, zachowanie/problem, warunek lub miarę, którą da się sprawdzić.
10. **Bądź uczciwy wobec niepewności.** Nie nazywaj hipotezy potwierdzoną na podstawie pojedynczej opinii.

## Kontekst projektu

Szukamy możliwości wsparcia **samego procesu uczenia się i pozyskiwania wiedzy** w szerokim rozumieniu, np.:

- szkoła podstawowa lub ponadpodstawowa;
- studia i praca nad projektami;
- nauka w miejscu pracy i zdobywanie nowych kompetencji;
- samodzielna nauka języka, narzędzia, hobby lub nowej dziedziny;
- uczenie się przez praktykę, ćwiczenia, informację zwrotną i utrwalanie wiedzy.

Nie koncentrujemy się na administracji placówki, dziennikach, planach lekcji, rekrutacji ani zarządzaniu szkołą.

## Proces pracy

### Etap 1 — Wybierz obszar, do którego masz dostęp

Zanim wygenerujesz pomysły, zastanów się:

- Kto i czego się uczy w obszarze, który znasz lub możesz zbadać?
- Do jakich osób możesz dotrzeć w ciągu najbliższego tygodnia?
- Jakie sytuacje uczenia się możesz zaobserwować albo odtworzyć z niedawnych doświadczeń?

**Zadanie zespołu:** zapiszcie obszar, grupę osób i powód, dla którego możecie ją zbadać. Nie wybierajcie jeszcze rozwiązania.

### Etap 2 — Zbierz obserwacje

Szukajcie **konkretnych zdarzeń**, a nie ogólnych deklaracji. Możecie rozmawiać z potencjalnymi użytkownikami, analizować własne doświadczenia lub obserwować proces nauki za zgodą uczestników.

Przykładowe pytania do rozmowy:
- „Opowiedz o ostatnim razie, gdy próbowałeś/próbowałaś nauczyć się czegoś trudnego”.
- „Co próbowałeś/-aś zrobić jako pierwsze?”
- „W którym momencie utknąłeś/utknęłaś?”
- „Co zrobiłeś/-aś potem?”
- „Czy próbowałeś/-aś obejść ten problem? Jak?”
- „Ile czasu lub wysiłku to zajęło?”

Unikaj pytań sugerujących rozwiązanie, np. „Czy przydałby Ci się agent AI, który…?”. Odpowiedź na takie pytanie nie jest mocnym dowodem rzeczywistej potrzeby.

**Szablon notatki obserwacyjnej**

- Osoba / typ użytkownika (bez zbędnych danych osobowych):
- Kontekst i zadanie:
- Co się wydarzyło? (fakty, zachowania, cytaty za zgodą):
- Co było trudne i w którym momencie?
- Co osoba zrobiła, żeby sobie poradzić?
- Jakie były koszty lub konsekwencje?
- Co pozostaje niepewne?
- Interpretacja zespołu (oddzielona od faktów):

Nie wpisuj danych wrażliwych ani informacji pozwalających zidentyfikować rozmówcę.

### Etap 3 — Wydobądź powtarzające się problemy

Dopiero po zebraniu obserwacji porównajcie je i poszukajcie wzorców.

Dla każdego kandydata na problem odpowiedzcie:
- Kogo dotyczy?
- W jakiej sytuacji występuje?
- Co dokładnie nie działa?
- Jak często to się zdarza?
- Jak poważna lub frustrująca jest konsekwencja?
- Jak ludzie radzą sobie obecnie?
- Jakie dowody wspierają opis problemu, a co jest tylko przypuszczeniem?

**Wzór opisu problemu:**

> [Konkretna grupa] podczas [konkretnej sytuacji] ma trudność z [konkretne zadanie/przeszkoda], co prowadzi do [obserwowalna konsekwencja].

Nie dodawaj jeszcze „potrzebuje aplikacji”, „potrzebuje chatbota” ani „potrzebuje agenta”.

### Etap 4 — Wybierz problem do dalszego badania

Porównajcie 2–3 problemy, używając skali 1–5. Oceny są narzędziem do dyskusji, a nie obiektywną prawdą.

| Kryterium              | Pytanie pomocnicze                                                                                |
| ---------------------- | ------------------------------------------------------------------------------------------------- |
| Częstotliwość          | Jak często problem występuje?                                                                     |
| Dotkliwość             | Jakie ma realne konsekwencje?                                                                     |
| Obecne obejścia        | Czy obecne sposoby radzenia sobie są nieskuteczne lub kosztowne?                                  |
| Dostęp do użytkowników | Czy możemy szybko porozmawiać z osobami, których dotyczy?                                         |
| Możliwość testu        | Czy da się sprawdzić kluczowe założenie bez budowania całego systemu?                             |
| Potencjał dla agenta   | Czy potrzebna może być adaptacja, działanie wieloetapowe, korzystanie z narzędzi lub koordynacja? |
|                        |                                                                                                   |

Wybierzcie problem na podstawie dowodów, a nie tego, który brzmi najbardziej futurystycznie.

### Etap 5 — Dopiero teraz generujcie pomysły

Wymyślcie kilka różnych sposobów rozwiązania wybranego problemu. Uwzględnijcie rozwiązania bez AI, z pojedynczym LLM-em i z systemem agentowym. Dla każdej propozycji zapiszcie:

- Co robi użytkownik?
- Co robi system?
- Jak zmienia się obecny sposób uczenia?
- Jaka jest najważniejsza korzyść?
- Co może pójść źle?
- Dlaczego agent (jeśli go proponujecie) miałby być lepszy niż prostsze rozwiązanie?

Agent może mieć sens np. wtedy, gdy system musi iteracyjnie dopasowywać plan do postępów użytkownika, korzystać z różnych narzędzi, wykonywać zadania w kilku krokach albo współpracować z wyspecjalizowanymi komponentami. Sama obecność chatbota nie oznacza jeszcze, że projekt jest agentowy.

### Etap 6 — Sformułujcie hipotezę

Hipoteza to twierdzenie, które może okazać się fałszywe. Unikajcie zdań typu „nasze rozwiązanie będzie przydatne”.

Przykładowe kategorie hipotez:
- **Problem:** określona grupa regularnie doświadcza opisanej trudności.
- **Zachowanie:** użytkownicy podejmują konkretne działania, aby poradzić sobie z problemem.
- **Wartość:** proponowany sposób pomocy poprawia konkretny aspekt procesu nauki.
- **Użyteczność / zaufanie:** użytkownicy potrafią wykonać zadanie i ufają wynikowi w określonych granicach.

**Szablon:**

> Wierzymy, że [konkretna grupa] doświadcza [konkretny problem] w [sytuacja]. Sprawdzimy to przez [metoda] na grupie [liczba/typ osób]. Za dowód uznamy [obserwowalny sygnał lub próg]. Wynik, który podważy hipotezę, to [warunek].

Nie dobieraj progu po poznaniu wyników. Ustal go przed testem.

### Etap 7 — Zaprojektujcie tani test

Na pierwszych zajęciach wystarczy zaplanować test, nie trzeba budować aplikacji. Możliwe metody:
- krótki wywiad o ostatnim rzeczywistym doświadczeniu;
- porównanie obecnego sposobu nauki z prostym prototypem;
- test ręcznie symulowanej usługi („concierge test”);
- prosta makieta lub przykładowa interakcja;
- krótka ankieta uzupełniająca wywiady — nie jako jedyne źródło dowodów.

Wymiana wywiadów między zespołami jest użyteczna, jeśli rozmówcy pasują do grupy docelowej. Zespół prowadzący wywiad powinien badać doświadczenia i zachowania, a nie sprzedawać pomysł.

**Plan testu:**
- Hipoteza:
- Kogo badamy i dlaczego te osoby:
- Metoda:
- Pytania / zadanie:
- Jaki wynik wspiera hipotezę:
- Jaki wynik jej przeczy:
- Ograniczenia testu:
- Co zrobimy po wyniku pozytywnym, negatywnym lub niejednoznacznym:

## Jak asystent AI ma z nami pracować

Wklej lub wyślij asystentowi następującą instrukcję:

> Jesteś mentorem zespołu realizującego semestralny projekt z systemów agentowych wspierających uczenie się. Stosuj zasady z tego dokumentu. Zaczynaj od Etapu 1 i zadawaj mi tylko kilka pytań naraz. Nie generuj za nas listy gotowych tematów, nie wymyślaj danych ani obserwacji i nie przeskakuj do rozwiązań przed zebraniem dowodów. Pomagaj nam rozróżniać fakty, interpretacje i hipotezy. Gdy przedstawimy materiał, zadawaj pytania pogłębiające i wskazuj luki w rozumowaniu. Na końcu każdego etapu poproś nas o krótkie podsumowanie własnymi słowami, a następnie oceń jego konkretność i wskaż, czego brakuje. Jeśli poprosimy o gotowy pomysł, zamiast podawać go od razu, pomóż nam wygenerować własne opcje przez pytania i techniki kreatywne. Zacznij od pytania: „Jaki obszar uczenia się znacie na tyle dobrze, że możecie w najbliższym tygodniu porozmawiać z osobami, które go doświadczają?”

## Rezultat pierwszych zajęć

Na koniec zajęć zespół powinien mieć:
1. wybrany obszar i grupę, którą chce badać;
2. pierwsze obserwacje / doświadczenia opisane konkretnie;
3. 2–3 wstępne opisy problemów, jeszcze bez przywiązania do rozwiązania;
4. wstępnie wybrany problem i listę brakujących dowodów;
5. plan krótkiego testu lub wywiadów na kolejny etap.

**Pamiętaj:** dobrze udokumentowane odkrycie, że problem jest mało istotny, też jest postępem. Celem nie jest obrona pierwszego pomysłu, tylko uczenie się na podstawie dowodów.
