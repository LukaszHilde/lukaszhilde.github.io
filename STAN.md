# STAN — karta przekazania projektu strony

Aktualizacja: 2026-09-09. Gałąź robocza: `claude/new-repository-creation-a0y3pd`.

Plik jest kartą przekazania między sesjami (desktop i telefon). Czytaj go na starcie,
aktualizuj przed commitem. Zapisujemy tu wyłącznie fakty potwierdzone w repozytorium.

## Cel

Strona `hildebrandtmanagement.com` — wizytówka Hildebrandt Management prezentująca
system pracy oraz pierwsze zatwierdzone usługi: TES i audyt dokumentacji.
Wygląd określa HMDesign (`pakiet-stylu/`). Zasady pracy: `CLAUDE.md`.

## Stan wykonany

- `index.html` (PL) i `english/index.html` (EN) — dwa samodzielne pliki, bez buildu.
- Zero zapytań sieciowych: Lato osadzone jako `data:font/woff2`, favicon jako `data:` SVG.
  Jedyne odnośniki zewnętrzne to nawigacja: LinkedIn (profil i firma) oraz `canonical`/`hreflang`.
- Sekcje PL: `#uslugi`, `#dowod`, `#obszary`, `#o-mnie`, `#kontakt`; kotwica powrotu `#top`.
- Menu mobilne bez JS (checkbox `.nav__check` / `.nav__toggle`), z drobnym skryptem
  zamykającym po kliknięciu odnośnika. Sprawdzone: otwiera się i zamyka poprawnie.
- Kontakt obecny w `index.html`: `mailto:office@hildebrandtmanagement.com`, `tel:+48889447117`.
- `CNAME` wskazuje `hildebrandtmanagement.com`.
- Ostatni commit na `main`: `f1f1f26` — publikacja ocenionej wersji EN v1 z dwiema korektami PL.

## Istotne pliki

| Ścieżka | Rola |
|---|---|
| `index.html` | strona PL, 593 linie, jeden plik |
| `english/index.html` | strona EN, odpowiednik PL |
| `CLAUDE.md` | zasady pracy, twarde reguły stylu, kontakt, publikacja |
| `pakiet-stylu/STYLE.md` | kanon HMDesign (PL); `STYLE.en.md` — EN |
| `pakiet-stylu/tokens/` | wartości tokenów, `fonts-base64.css` do wklejania |
| `pakiet-stylu/referencja/uslugi-tes.html` | wzorzec podstrony usługi do skopiowania |
| `CNAME` | domena produkcyjna |

## Blokady

- **Brak dostępu do dysku `C:\HM`.** Sesje w chmurze nie widzą `C:\HM\START_HM.md`
  ani `C:\HM\CLAUDE.md`. Kontekst trzeba brać z repozytorium albo z jawnego polecenia.
- **Podstrony usług nie istnieją.** `CLAUDE.md` opisuje `uslugi/tes.html` i `uslugi/audyt.html`,
  ale katalog `uslugi/` nie został utworzony. Wzorzec czeka w `pakiet-stylu/referencja/`.
- **Podgląd mobilny — mechanizm sprawdzony, publikacja niewykonana.** Wierna kopia
  `index.html` renderuje się piksel w piksel identycznie po dodaniu jednej linii
  `<style>body{font-size:medium}</style>` na początku (strona nie deklaruje `font-size`
  na `body`, więc dziedziczyłaby wartość z resetu hosta). Samo opublikowanie podglądu
  zostało odrzucone przez klasyfikator uprawnień sesji — wymaga zgody Łukasza.

## Następny krok

Zbudować `uslugi/tes.html` na wzorcu `pakiet-stylu/referencja/uslugi-tes.html`,
bez dokładania nowych klas CSS. Warunek startu: zatwierdzona przez Łukasza treść TES.
