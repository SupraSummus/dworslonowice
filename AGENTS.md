# Wskazówki dla agentów

## Semantic Line Breaks (SemBr)

W plikach z prozą (Markdown itp.) stosujemy [semantyczne łamanie wierszy](https://sembr.org/):
nowa linia po każdym zdaniu lub istotnej frazie.
Na wyrenderowanej stronie nie robi to różnicy,
a diffy w gicie stają się czytelniejsze.

Przyjmujemy to leniwie:

- Nie przeformatowuj istniejącego tekstu tylko po to, żeby dodać łamania.
- Nowy tekst oraz zdania, które i tak edytujesz, zapisuj już w stylu SemBr.

## Dokumenty opisują teraźniejszość; przeszłość trzyma git

Dokument, który opowiada historię własnych zmian, staje się changelogiem —
a git prowadzi lepszy: kompletny, datowany i przypięty do faktycznych diffów.
Test dla każdego zdania o przeszłości:
**czy zmienia ono to, co powinien zrobić czytelnik pracujący z obecnym stanem?**
Jeśli tylko odnotowuje, że coś się wydarzyło albo kiedyś było inaczej — usuń je;
jeśli wyjaśnia, dlaczego teraźniejszość wygląda tak, a nie inaczej —
zostaw, ale sformułowane jako uzasadnienie w czasie teraźniejszym, nie jako wydarzenie.

Historia, która zasługuje na miejsce (zawsze jako uzasadnienie obecnego stanu):

- **Odrzucona alternatywa i powód odrzucenia** —
  oszczędza następnej osobie ponownego proponowania tego samego.
  Sekcja „Odrzucone warianty" w [woda.md](woda.md) to wzorcowy przykład:
  wybór padł, a odrzucone warianty stoją obok z powodami.
- **Świadoma zmiana decyzji lub nazwy** —
  żeby nikt nie „naprawił" jej z powrotem.
- **Data identyfikująca zewnętrzny artefakt** —
  uchwałę, dokument, stan prawny („stan prawny na 2026 r.") —
  to proweniencja i zostaje.

Historia, która jest balastem:

- **Znaczniki „zrobione".**
  Gdy pozycja z listy „do ustalenia" albo planu się domyka,
  usuń ją — bez ~~przekreśleń~~ na pamiątkę.
  Jeśli zostawia po sobie decyzję („odpadło celowo", „zostaje z rozmysłem"),
  przenieś decyzję do sekcji, która jest jej właścicielem;
  sama pozycja i tak znika.
- **Narracja statusu** — „aktualizacja (2026-07): …", „już zrobione".
  Wpisz bieżący stan wprost w zdanie, które jest właścicielem faktu.
- **Daty, których jedynym zadaniem jest uporządkowanie edycji samego dokumentu.**
  Taka data znaczy, że doklejono dopisek tam, gdzie należało przepisać sekcję.

Słowny sygnał ostrzegawczy:
przysłówki czasu — „jeszcze", „już", „nadal", „na razie", „wciąż", „obecnie" —
kotwiczą zdanie w chwili pisania
i po cichu zakładają przyszłą edycję
(„nadal czekamy" czyta się jako „czekamy, dopóki ktoś nie zaktualizuje tego zdania").
Pisz w zwykłym czasie teraźniejszym („czekamy na interpretację starostwa")
albo przypnij stwierdzenie do datowanego zewnętrznego artefaktu.
Podejrzany jest tylko sens czasowy —
użycia logiczne („woda wciąż krąży w obiegu") są w porządku —
więc traktuj trafienie jako sygnał do ponownego przeczytania zdania,
nie jako automatyczny błąd.

**Przepisuj w miejscu; nie doklejaj poprawek.**
Gdy decyzja się zmienia, zmienia się sekcja, która jest jej właścicielem —
tak, żeby dokument czytał się prawdziwie od góry do dołu.
Sekcja „powyższe zmienia się następująco"
zamienia dokument w serię łatek nakładanych w głowie czytelnika.
Jedyny uprawniony wyjątek: decyzja podjęta, ale niewykonana —
dokument naprawdę opisuje wtedy dwa stany (co jest i co będzie).
Wtedy docelowy wariant dostaje własną sekcję nazywającą to, co zastępuje,
każda zastępowana sekcja dostaje jednolinijkowy odnośnik w przód,
a instrukcja scalenia jest wpisana w samą sekcję
(„po wykonaniu wcielić do X") —
i wykonanie tego scalenia jest częścią zmiany, która decyzję realizuje.

Przyjmujemy to leniwie, jak SemBr:
usunięcie historii pozycji jest częścią zmiany, która ją domyka,
a edycja sekcji obejmuje wymiecenie zastanej, nieaktualnej narracji —
ale nie przeczesuj starych sekcji, których nic nie dotyka.

## Jeden właściciel każdego faktu; narrację powtarzaj swobodnie

Proza może się powtarzać; fakty nie.
Powtórzenie kontekstu, żeby dokument czytał się samodzielnie, to dobre pisarstwo —
notki o zakresie, streszczenia „sąsiedni dokument opisuje X" są mile widziane.
Ale każdy fakt, który może się zmienić —
decyzja, status, wymiar, granica, stan prawny —
ma dokładnie jedną sekcję-właściciela,
i to tam lądują edycje.
Powtórzenie gdzie indziej musi wskazać właściciela
(link albo nazwa sekcji)
i pozostać ogólniejsze od oryginału:
nie wyliczaj drugi raz zmiennych szczegółów
(liczb, powierzchni, stanów „ustalone/do ustalenia")
z pełną precyzją.
Jeśli powtórzenie jest równie precyzyjne jak właściciel,
czytelnik nie pozna, która kopia jest aktualna —
tak dwa dokumenty zaczynają sobie przeczyć.
Wzorcowy przykład w tym repo:
„Odrzucone warianty" w [woda.md](woda.md)
podaje powód odrzucenia stawu naturalnego ogólnie („woda gruntowa za głęboko")
i odsyła do sekcji o uszczelnieniu,
która jest właścicielem szczegółów.

Otwarte sprawy żyją w dokładnie jednej liście
(w tym repo: „Do ustalenia" w [woda.md](woda.md)).
Inne miejsce może nosić co najwyżej jednolinijkowy odnośnik do niej.

## Review zmian

Na prośbę o review przejrzyj zmiany z bieżącej sesji świeżym okiem,
odpowiedz na pytania poniżej,
a poprawki, które z odpowiedzi wynikają, od razu wprowadź —
małe refaktory realizuj, większe tylko odnotuj, zamiast rozgrzebywać.

- **Kierunek**: jaki konkretny problem znika dzięki tej zmianie?
  Zmiana, która tylko przesuwa tekst, nie ma kierunku.
- **Elegancja**: rozwiązanie proste i domknięte —
  bez sekcji-sierot, wiszących odwołań („te potrzeby" bez sąsiada)
  i połowicznych przenosin.
- **Spójność odwołań** (odpowiednik testów):
  grep za nazwami usuniętych i przemianowanych plików oraz sekcji;
  sprawdź linki w README i sąsiednich dokumentach
  oraz czy przykłady cytowane w tym pliku nadal istnieją.
  Sprawdzaj to, co zmiana mogła zepsuć —
  rytualne odhaczanie wszystkiego nie ma wartości.
- **Reguły tego pliku zastosowane do samej zmiany**:
  czas teraźniejszy, jeden właściciel faktu, brak znaczników „zrobione",
  jedna lista spraw otwartych, SemBr w nowym tekście.
- **Uczciwość**: czy dokument czyta się prawdziwie od góry do dołu
  i nie zmyli kolejnej osoby?
  Jeśli zmiana celowo oddaje jakąś informację historii gita,
  nazwij ją w opisie zmiany, zamiast udawać, że nic nie zniknęło.
- **Szum**: meta-komentarze, nawiasy i odnośniki tylko tam,
  gdzie niosą treść.
- **Werdykt**: pchać dalej, domknąć czy wycofać — z uzasadnieniem.
  Kolejne zmiany bez problemu, który je napędza, to mieszanie w tekście.
