# hildebrandtmanagement.com — HMDesign obowiązuje

Strona Hildebrandt Management (GitHub Pages, repo `LukaszHilde/lukaszhilde.github.io`).
Obowiązkowo używa systemu wizualnego **HMDesign**. Nie wprowadzamy własnej palety,
własnego kroju ani własnych komponentów.

**Kanon stylu:** `pakiet-stylu/` w tym repozytorium — `STYLE.md` (reguły),
`tokens/` (wartości), `fonts/` (Lato), `referencja/` (działający wzorzec strony
i podstrony). Kopia robocza: `C:\HM\PROJEKTY\strona-www\WYNIKI\pakiet-stylu\`.

## Rola i treść — decyzja 05.09.2026

ChatGPT Work prowadzi strategię, marketing, metodologię i rozwój oferty. Claude Code wykonuje uzgodnione zmiany techniczne. Łukasz podejmuje decyzje. Cowork jest wycofany z bieżącego obiegu HM.
Przed pracą przeczytaj wspólny `C:\HM\START_HM.md`, `C:\HM\CLAUDE.md` i stan zadania strony. Jeżeli tych plików nie ma w środowisku, wskaż brak i skorzystaj z jawnie przekazanego zakresu.

HM obejmuje strategię i rozwój, ofertę, przygotowanie, realizację i wynik kontraktu. Metodologia łączenia ludzi, informacji, decyzji i odpowiedzialności jest szersza niż pierwsze dwie usługi. Wolno opisywać system pracy; nie wolno utożsamiać HM wyłącznie z TES, audytem dokumentacji albo narzędziami AI.
HMDesign i pliki stylu określają wygląd. Stare GLOS.md, wzorce i pamięć modelu nie narzucają obecnego pozycjonowania.

Pierwsze zatwierdzone usługi: **TES — wspólna podstawa do porównania ofert** i **Audyt dokumentacji i paczki podwykonawcze**. Zachowaj przekazane opisy. Zmiana sensu, zakresu, liczb lub narracji wymaga jednoznacznego polecenia Łukasza. Wdrożenie uzgodnionej zmiany nie wymaga ponownego pytania.
Przy zmianie EN tłumacz aktualną zatwierdzoną PL w całości, zachowując zakres i znaczenie. Nie łącz nowej oferty z dawnymi sekcjami EN. Uogólnienia liczb muszą być prawdziwe i spójne językowo; przygotowanie oferty nie oznacza prowadzenia realizacji.
[HM — SYSTEM](https://app.notion.com/p/3d2b1115d89480ffa89dcfc5c776feb1) przechowuje zatwierdzone ustalenia. Najnowsze jednoznaczne polecenie Łukasza ma pierwszeństwo przed starszym zapisem.

## Jak system jest tu wpięty

Strona to **dwa samodzielne pliki** — `index.html` (PL) i `english/index.html` (EN)
— bez buildu i bez zewnętrznych zasobów. Dlatego tokeny HMDesign są **wklejone
inline** w `<style>`, a Lato jest osadzone jako `data:font/woff2`.

To jest świadomy wyjątek od „linkuj `hmdesign/styles.css`", a nie zaniedbanie —
jednoplikowość jest tu cechą, nie skrótem.

**Obowiązek:** przy zmianie systemu tokeny **przepisujemy z kanonu**, nie
poprawiamy ręcznie na miejscu. Wartość zmieniona lokalnie to błąd, nie wariant.
Zmiany trzymamy zsynchronizowane w obu językach.

Źródło fontów do wklejenia: `pakiet-stylu/tokens/fonts-base64.css` (gotowe
`@font-face` z `data:font/woff2`). Wariant z plikami obok: `tokens/fonts.css` + `fonts/`.

## Zasady twarde

1. Kolory **wyłącznie** przez `var(--hm-…)`. Żadnego nowego hexa poza blokiem tokenów.
2. Krój wyłącznie **Lato**. **Zero zapytań sieciowych** — bez Google Fonts, bez CDN,
   bez zewnętrznych skryptów i analityki. To wymóg prywatności, nie preferencja.
3. `border-radius: 0`. Ostre rogi bez wyjątku.
4. Karty: ramka `1px var(--hm-hairline)`, **bez cienia**.
5. **Bez emoji.** Dozwolone glify: `→` `✕` `✉`. Punktory list to `→`.
6. Nagłówki Lato 900, wielkość zdaniowa. WERSALIKI tylko w eyebrow/etykietach
   (tracking `.16–.18em`, w akcencie).
7. Zieleń `--hm-green*` tylko dla wątku „sustainability". Max ~3 kolory na kompozycję.
8. Bez gradientów, tekstur i zdjęć dekoracyjnych. Bez animacji poza `:hover` linku.
9. Logo **nie rysujemy z pamięci** — znak jest typograficzny: pomarańczowy kwadrat
   + logotyp Lato 900.
10. Wartość spoza tokenów wymaga decyzji człowieka. **Pytaj, nie dobieraj.**

## Nowa podstrona — jak

Podstrony usług (`uslugi/tes.html`, `uslugi/audyt.html`) trzymają ten sam układ:
pasek akcentu → sticky nagłówek → hero na czerni → pasek intro → sekcje naprzemiennie
biel / szarość → sekcja ciemna → kontakt → stopka.

Wzorzec do skopiowania: `pakiet-stylu/referencja/uslugi-tes.html`.
Nie dokładamy nowych klas CSS. Nowa strona to nowa treść w istniejących blokach.
Bloki dodane 05.09.2026 i obowiązujące: karta usługi (`.svc`, `.scard`), liczby
dowodu (`.proof__num`), menu mobilne bez JS (`.nav__check`, `.nav__toggle`).

Każda podstrona: własny `<title>`, `description`, `og:*`, `canonical`,
`hreflang` do odpowiednika EN. Nawigacja w nagłówku wraca na `/`.

## Kontakt — jedno źródło prawdy

```
Łukasz Hildebrandt · office@hildebrandtmanagement.com · tel. 889 447 117
Gdańsk / Trójmiasto, Polska · LinkedIn: linkedin.com/in/lukasz-hildebrandt
```

E-mail jest głównym kanałem kontaktu, LinkedIn drugim. Sprawdzaj wszystkie rzeczywiste wystąpienia kontaktu w PL i EN; nie zakładaj sztywnej liczby miejsc.
Adres: `mailto:office@hildebrandtmanagement.com`. Telefon: `tel:+48889447117`, tekst `+48 889 447 117`.

## Publikacja — pułapka remote'ów

Publikacja wymaga jednoznacznego polecenia Łukasza oraz sprawdzonego wyniku. Dotychczasowy uzgodniony kanał to GitHub Desktop na koncie **LukaszHilde**.
Właściwe repo: `LukaszHilde/lukaszhilde.github.io`. Przed ewentualną publikacją sprawdź `git remote -v` i docelową gałąź. Istnieje też historyczny fork `hmaicentrum-lgtm/lukaszhilde.github.io`; nie zakładaj, że push tam zmieni właściwą stronę.
Nie zmieniaj remote, nie usuwaj upstream, nie wykonuj force-push, resetu ani czyszczenia cudzych zmian w ramach porządkowania instrukcji. Nie zakładaj braku lub obecności uprawnień na podstawie starej sesji.
Sprawdź wygląd na komputerze i telefonie, linki, kontakt i spójność PL/EN. Przegląd samego kodu nie jest kontrolą wizualną. Przed publikacją przekaż gotowy wynik do niezależnego przeglądu w ChatGPT Work.

## Odstępstwa

| Odstępstwo | Powód | Data |
|---|---|---|
| Tokeny i fonty wklejone inline zamiast linkowane z `hmdesign/styles.css` | Strona jest celowo jednoplikowa i w 100% offline-safe; brak buildu | 2026-09-02 |

