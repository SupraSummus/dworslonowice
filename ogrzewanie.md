# Ogrzewanie dworu — układ wodny dla dwóch źródeł ciepła

Ten dokument jest o **układzie wodnym**: jak połączyć dwa źródła ciepła tak,
żeby jedno niosło podstawę, a drugie dopełniało do zadanego poziomu,
i żeby z tego samego układu szło centralne ogrzewanie (c.o.) i ciepła woda użytkowa (c.w.u.).
Czym palić i jakim kotłem — celowo poza zakresem;
tu liczy się hydraulika, sterowanie i bezpieczeństwo wody.

Potrzeby, które ta koncepcja realizuje:
źródło podstawowe (paliwo stałe) niesie tanie ciepło, gdy dwór żyje;
źródło szczytowe (istniejący kocioł gazowy) dopełnia automatycznie i pilnuje domu, gdy stoi pusty;
c.o. i c.w.u. z jednego układu;
brak ręcznych przełączeń między źródłami;
zero ryzyka dla źródła na paliwo stałe, które nie umie samo zgasnąć.

Wynik: **oba źródła pracują na wspólny zbiornik buforowy.
Źródło podstawowe ładuje bufor pełną mocą, a odbiory (c.o. i c.w.u.) ciągną z bufora.
Źródło szczytowe wpina się równolegle, z priorytetem bufora: dogrzewa odbiory tylko
wtedy, gdy zmagazynowanego ciepła zabraknie, i bierze przy tym powrót z najchłodniejszej
wody, żeby nie stracić sprawności kondensacji.**
Bufor jest elementem łączącym — całe wyzwanie „jak spiąć dwa źródła" sprowadza się do tego,
jak go obudować, żeby pogodzić **przeciwne** wymagania obu źródeł i higienę ciepłej wody.

## Kontekst

Dwór grzano drewnem przez większość istnienia,
więc źródło na paliwo stałe wraca do tego, jak budynek był ogrzewany —
kominy z epoki istnieją (ich przydatność potwierdza kominiarz, sekcja „Miejsce w dworze i komin").
Nowe jest tylko połączenie dwóch źródeł, i to ono jest właściwym problemem do rozwiązania.

## Wyzwanie: połączyć źródło, które się nie wyłącza, ze źródłem, które się wyłącza

Dwa źródła różnią się tak, że nie da się ich po prostu spiąć w te same rury bez namysłu.
Źródło szczytowe (kocioł gazowy) moduluje i gaśnie na sygnał —
grzeje dokładnie tyle, ile trzeba, i tylko wtedy, gdy trzeba.
Źródło podstawowe na paliwo stałe zachowuje się odwrotnie i stawia układowi wodnemu
trzy twarde wymagania:

- **Nie da się go płynnie regulować** — gdy oddaje moc, oddaje ją całą,
  a nie tyle, ile w danej chwili potrzebuje dom.
  Układ wodny musi mieć więc gdzie tę moc **odłożyć**.
- **Musi mieć gdzie oddać ciepło zawsze** — jeśli odbiór stanie
  (zamknięte termostaty, wygrzana c.w.u., brak prądu),
  woda w źródle podstawowym się zagotuje.
  Układ musi gwarantować odbiornik ciepła w każdej chwili.
- **Chce pracować gorąco** — powrót poniżej ~60°C wykrapla na nim substancje,
  które je niszczą. Układ musi trzymać jego powrót ciepły.

I tu zaczyna się właściwa trudność: **reszta układu stawia wymagania ciągnące w przeciwną stronę.**

- **Kocioł gazowy kondensacyjny chce powrotu zimnego.** Swoją wysoką sprawność oddaje
  tylko wtedy, gdy powrót jest poniżej punktu rosy spalin (~54°C dla gazu ziemnego) —
  wtedy para wodna ze spalin skrapla się i oddaje dodatkowe ciepło.
  Powrót podgrzany (np. wodą z bufora) tę sprawność zabiera: strata rzędu 10–12%,
  i to dokładnie odwrotny wymóg niż ma źródło podstawowe.
- **Ciepła woda użytkowa chce magazynu gorącego.** Legionella namnaża się w stojącej,
  letniej wodzie (20–45°C), groźna po aerozolizacji pod prysznicem — więc c.w.u. albo
  magazynuje się gorąco (≥60°C, z okresowym przegrzewem), albo nie magazynuje wcale
  (stacja świeżej wody, sekcja o odbiorach).

Wspólny **zbiornik buforowy** godzi te sprzeczności, bo pozwala zaspokoić każde wymaganie
w jego własnym miejscu, a nie jedną wspólną temperaturą:

- źródło podstawowe oddaje pełną moc do wody i **magazynuje** ją, zamiast dławić spalanie,
  a jego powrót trzyma ciepły osobny zawór (sekcja o bezpieczeństwie);
- bufor jest odbiornikiem ciepła, który przyjmie tę moc zawsze;
- kocioł gazowy wpina się **równolegle** i bierze powrót z najchłodniejszej wody (sekcja niżej),
  więc kondensuje mimo gorącego bufora obok;
- woda w buforze jest **technologiczna, w obiegu zamkniętym** — nie pije się jej,
  więc legionella jej nie dotyczy i jej temperatura może swobodnie spadać;
  higiena obowiązuje tylko wodę użytkową i jest rozwiązana osobno.

## Schemat układu: dwa źródła, jeden magazyn, dwa odbiory

```
   ŹRÓDŁA                          MAGAZYN                      ODBIORY

   źródło podstawowe            ┌────────────────┐
   (paliwo stałe)               │   ZASOBNIK      │──▶ c.w.u. (stacja świeżej wody
      │ zasilanie ─────────────▶│   BUFOROWY      │           albo zasobnik ≥60°C)
      ▲ powrót CIEPŁY (≥60°C)   │  góra: gorąca   │
      │ ← zawór ochrony powrotu │  ~1500–2500 l   │──▶ c.o. ─▶ mieszacz+krzywa ─▶ grzejniki
      │                         │  dół: chłodna   │                              │
   zawór schładzający           └────────────────┘                              │
   (awaryjny zrzut ciepła)          powrót z odbiorów (ZIMNY) ◀──────────────────┘
                                        │
   źródło szczytowe                     ├──────────▶ dół bufora
   (kocioł gazowy                       │
    KONDENSACYJNY)                      └──────────▶ powrót kotła gazowego (ZIMNY)
      │ zasilanie ─▶ obieg c.o. i dogrzew c.w.u. (równolegle z buforem)
      ▲ powrót ZIMNY (≤54°C → kondensuje)
      └ priorytet bufora: gaz rusza, gdy góra bufora spada poniżej progu
```

Zasada pracy — podstawa niesie, szczyt dopełnia:

1. **Źródło podstawowe ładuje bufor.** Oddaje pełną moc do zbiornika,
   aż wygrzeje go od góry do dołu. Jeden cykl pracy = jeden zapas ciepła.
2. **Odbiory ciągną z góry bufora** — najgorętszej warstwy: obieg c.o. i c.w.u.
3. **Źródło szczytowe dopełnia braki — równolegle, na zimnym powrocie.**
   Kocioł gazowy nie stoi w szeregu za buforem (podgrzewałby sobie powrót i przestał kondensować),
   tylko wpina się równolegle: gdy góra bufora spadnie poniżej progu, przejmuje obieg c.o.
   i grzeje go wprost, biorąc powrót z najchłodniejszej wody układu —
   dzięki temu kondensuje mimo stojącego obok gorącego bufora.
   Póki bufor jest ciepły, gaz nie pali w ogóle.

To daje żądaną hierarchię bez żadnego ręcznego przełączania:
**podstawa niesie tak długo, jak starcza zmagazynowanego ciepła,
a szczyt dokłada tylko różnicę** — decyduje automatyczny regulator wg progu na buforze.

## Jak dokładnie spinają się dwa źródła

To jest sedno całej koncepcji — reszta z niego wynika.

- **Źródło podstawowe łączy się tylko z buforem**, nie z odbiorami wprost:
  ładuje go swoim obiegiem (z ochroną powrotu), i na tym jego rola się kończy.
  Nie „grzeje kaloryferów" — grzeje wodę w zbiorniku.
- **Źródło szczytowe łączy się równolegle i bierze zimny powrót.**
  Gdy bufor stygnie poniżej progu, kocioł gazowy przejmuje obieg c.o. i grzeje go wprost;
  jego powrót to najchłodniejsza woda układu (powrót z grzejników / dół bufora),
  nigdy woda podgrzana buforem — dlatego kocioł kondensuje i nie traci sprawności.
- **Rozdziela je regulator z czujnikiem w górze bufora**, który przełącza obieg
  na kocioł gazowy dopiero poniżej progu (zawór przełączający albo osobna pompa).
  To jedyny element „decyzyjny" układu — działa automatycznie, bez ręcznych przełączeń.

Odrzucona alternatywa — **kocioł gazowy szeregowo za buforem**, tak żeby woda do odbiorów
płynęła przez kocioł: prostsze i pasywne (wystarczyłby sam termostat, bez zaworu przełączającego),
ale bufor podgrzewałby wtedy powrót kotła, a kocioł kondensacyjny na ciepłym powrocie
traci sprawność kondensacji (sekcja „Wyzwanie") — i to na cieple, które robi droższe źródło.
Odrobina sterowania w wariancie równoległym zwraca się tą właśnie sprawnością.

## Odbiory: centralne ogrzewanie i ciepła woda

- **Centralne ogrzewanie (grzejniki).** Instalacja grzejnikowa pracuje na wyższym
  zasileniu (typ. 55–70°C), więc bufor trzeba ładować gorąco (góra ~80°C)
  i niesie on podstawę krócej, niż niosłaby ją instalacja płaszczyznowa —
  jeden zapas to godziny, nie doba. Obieg c.o. bierze z góry bufora
  przez mieszacz z krzywą grzewczą. **Krzywa grzewcza pracuje tu podwójnie:**
  obniżając temperaturę zasilania przy łagodnej pogodzie wydłuża czas, w którym
  podstawa wystarcza, i **obniża powrót** — a im niższy powrót, tym więcej
  kocioł gazowy kondensuje w chwilach, gdy dopełnia. Powrót z grzejników poniżej ~54°C
  jest warunkiem kondensacji; przez większość sezonu krzywa go tam sprowadza,
  a jeśli grzejniki są za małe, by pracować chłodno — to argument, żeby je powiększyć.
- **Ciepła woda użytkowa — z ochroną przed legionellą.** Woda w buforze jest
  technologiczna, więc higiena dotyczy dopiero wody pitnej. Dwa czyste warianty:
  - **Zasobnik gorący (≥60°C) z przegrzewem.** Istniejący zasobnik zostaje;
    bufor grzeje jego wężownicę, gdy jest w nim ciepło z podstawy, a kocioł gazowy
    dogrzewa i **gwarantuje okresowy przegrzew antylegionellowy** (≥60°C),
    niezależnie od tego, czy ktoś palił drewnem. Trzymanie zasobnika gorąco
    kosztuje trochę kondensacji przy dogrzewie c.w.u. — cena higieny.
  - **Stacja świeżej wody** (płytowy wymiennik na górze bufora) — to właśnie
    „podgrzewanie na wyjściu": zimna woda wodociągowa przepływa przez wymiennik
    dopiero przy poborze i wychodzi gorąca. Sedno w tym, że strona użytkowa to
    **świeża woda w przepływie, a nie magazyn** (kilka litrów w wymienniku, nie zbiornik),
    więc legionella nie ma stojącej, letniej wody do namnożenia, a bufor po drugiej
    stronie zostaje technologiczny. Bufor musi mieć w górze ~60–65°C, żeby dać
    ~50–55°C w kranie — a skoro c.w.u. bierze się wtedy wyłącznie z bufora,
    kocioł gazowy musi umieć **doładować górę bufora**, gdy podstawa nie pali
    (całe lato!); to dodatkowe wpięcie po stronie gazu, którego wariant
    z zasobnikiem nie potrzebuje.
    Sensowna zwłaszcza, gdyby istniejący zasobnik i tak trzeba było wymienić.

  Odrzucona pokrewna myśl — **bufor napełniony wodą pitną, sterylizowaną wymiennikiem
  na wyjściu**: kierunek trafny, ale nie ta wersja. Cały bufor (1500–2500 l) stałby się
  wtedy siedliskiem legionelli, bo woda stoi w nim długo i bywa letnia (20–45°C),
  a podgrzanie samej wychodzącej strugi tego nie naprawia — do tego jednorazowy przepływ
  przez 60°C nie sterylizuje (w 60°C legionella ginie w minutach, pewny natychmiastowy
  efekt daje dopiero ~70°C). Woda pitna w stalowym buforze wnosiłaby też tlen,
  przyspieszając korozję bufora i źródła na paliwo stałe. Dlatego strona użytkowa albo
  nie magazynuje wody wcale (stacja świeżej wody), albo trzyma ją gorąco — a bufor
  zostaje w obiegu zamkniętym.

  Wybór wariantu — po przeglądzie istniejącego zasobnika („Do ustalenia").

## Bezpieczeństwo wody — pasywne, bo źródło podstawowe nie zgaśnie

Wymagania **źródła podstawowego** z sekcji „Wyzwanie" (ciepły powrót, zawsze dostępny
odbiornik ciepła) domyka mechaniczna armatura, działająca **bez prądu** —
to warunek, bo zagrożenie pojawia się właśnie przy zaniku zasilania:

- **Ochrona powrotu: zawór termostatyczny** (próg 60–72°C) miesza gorące zasilanie
  z zimnym powrotem, aż źródło podstawowe się rozgrzeje — powrót nie schodzi
  poniżej punktu rosy, więc nie ma korozji ani osadów.
- **Awaryjny zrzut ciepła: zawór schładzający** na wężownicy schładzającej źródła —
  gdy woda przekroczy ~95°C (np. przy zaniku prądu i stojącej pompie),
  przepuszcza przez wężownicę zimną wodę wodociągową i odbiera nadmiar ciepła.
  Wariant dla źródeł bez takiej wężownicy: układ otwarty z naczyniem wzbiorczym.
- **Naczynie przeponowe i zawór bezpieczeństwa** jak w każdym układzie zamkniętym.
- **Odbiornik ciepła zawsze dostępny**: sam bufor. Pojedynczy, dopalający się bez odbioru
  cykl źródła podstawowego ma dokąd oddać moc, nawet gdy dom nie pobiera ciepła.

## Praca bez opieki — kiedy nie ma kto obsłużyć podstawy

Ten sam wymóg co przy wodzie (dwór bywa bez stałej opieki):
układ ma przetrwać mróz **bez udziału człowieka**.
Podział ról między źródłami załatwia to sam z siebie:

- **Źródło szczytowe (gaz) jest bezobsługowe.** Gdy bufor wystygnie, bo nikt nie obsłużył
  podstawy, kocioł gazowy automatycznie utrzymuje c.o. na temperaturze chroniącej przed
  zamarznięciem, grzeje c.w.u. i **realizuje przegrzew antylegionellowy** —
  higiena c.w.u. nie zależy więc od tego, czy ktoś palił drewnem.
- **Źródło podstawowe daje tanie ciepło, gdy ktoś jest.**
  Obsłużone w czasie pobytu ładuje bufor, a gaz milczy, dopóki starcza zapasu.
- Armatura bezpieczeństwa działa pasywnie, więc nieobecność nie stwarza ryzyka.

Podział jest naturalny: **podstawa obniża rachunek, gdy dwór żyje;
szczyt pilnuje go, gdy stoi pusty.**

## Wielkość bufora

Bufor jest tym większy, im dłużej ma nieść podstawę między obsługami źródła
i im większą moc źródła musi przyjąć naraz.
Reguła kciuka: **~50–100 l na kW mocy źródła podstawowego** —
przy typowej mocy 20–30 kW to **~1500–2500 l**.
Dokładna wartość wynika z obliczenia straty ciepła dworu i z projektowej
temperatury zasilania grzejników (obie pozycje w „Do ustalenia").
Bufor izolowany trzyma zapas ze stratą kilku %/dobę.

## Miejsce w dworze i komin

Układ stoi w piwnicy dworu (piwnica schodzi ~1,5 m w grunt, [sekcja o wodzie](woda.md)):
blisko odbiorów, krótkie rury, straty ciepła zostają w bryle budynku.
Ponieważ jedno źródło jest na paliwo stałe, piwnica potrzebuje:

- **nawiewu powietrza** do spalania (czerpnia od zaplecza albo pod ziemią —
  plan zakazuje ingerencji w elewacje frontowe, [woda.md](woda.md)),
- **miejsca na bufor** (zbiornik 1500–2500 l zajmuje realną przestrzeń i nośność stropu/posadzki),
- **przewodu kominowego dla paliwa stałego** — odpornego na wysoką temperaturę i pożar sadzy,
  z własnym ciągiem, osobnego od spalin gazowych; stan kominów z epoki potwierdza kominiarz.

## Etapowanie

1. **Teraz**: obliczenie straty ciepła dworu i przegląd piwnicy, kominów
   oraz istniejącego zasobnika c.w.u. („Do ustalenia") —
   bez tego nie dobiera się mocy źródła ani wielkości bufora.
2. **Etap 1**: bufor z pełną armaturą bezpieczeństwa (ochrona powrotu, zawór schładzający,
   naczynie), wpięcie źródła podstawowego na bufor, wpięcie kotła gazowego **równolegle**
   z priorytetem bufora (regulator progowy + zawór przełączający / pompa, powrót gazu z zimnej
   strony), mieszacz z krzywą grzewczą na c.o.
   Po tym etapie podstawa niesie, a szczyt dopełnia automatycznie i wciąż kondensuje.
3. **Etap 2 (opcjonalnie)**: zasobnik dwuwężownicowy albo stacja świeżej wody,
   jeśli przegląd wskaże wymianę istniejącego zasobnika.
4. **Kiedyś**: kolejne źródło (np. kominek z płaszczem wodnym) dopięte do bufora —
   układ jest na to gotowy z założenia, każde nowe źródło ładuje ten sam magazyn.

Rzędy wielkości kosztów (szacunek na ceny 2026, prace zlecone —
do planowania, nie zamiast ofert wykonawców):

- Bufor 1500–2500 l z izolacją i osprzętem: **~5–12 tys. zł**.
- Armatura bezpieczeństwa, pompy, mieszacz, regulator, montaż i orurowanie: **~10–25 tys. zł**.
- Ewentualny wkład kominowy: **~5–15 tys. zł**, zależnie od stanu komina.

(Koszt samego źródła podstawowego zależy od jego wyboru — poza zakresem tego dokumentu.)

## Do ustalenia

- Obliczenie straty ciepła dworu (moc źródeł i c.o.) —
  bez niego reszta doboru wisi w powietrzu.
- Projektowa temperatura zasilania **i powrotu** grzejników — wyznacza, jak gorąco
  ładować bufor, jak długo podstawa niesie oraz czy powrót schodzi poniżej ~54°C,
  żeby kocioł gazowy kondensował (jeśli nie, rozważyć powiększenie grzejników).
- Wielkość i umiejscowienie bufora w piwnicy: przestrzeń, nośność, trasa nawiewu
  i **droga wniesienia** — zbiornik 1500–2500 l często nie przechodzi przez drzwi piwnicy;
  wtedy wariantem są dwa mniejsze zbiorniki spięte w jeden magazyn.
- Stan i klasa kominów (przegląd kominiarski): czy jest przewód dla paliwa stałego.
- C.w.u. wobec legionelli: zasobnik gorący (≥60°C) z przegrzewem czy stacja świeżej wody;
  przegląd istniejącego zasobnika (liczba wężownic, decyzja o wpięciu kontra wymianie).
- Czy obecny kocioł gazowy jest kondensacyjny i jak wpiąć jego sterowanie w priorytet bufora;
  moc kotła oraz układ istniejącej instalacji c.o.
