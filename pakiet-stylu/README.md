# HMDesign — pakiet stylu dla narzędzi AI

Zestaw do przekazania narzędziu, które ma budować strony, dokumenty albo
prezentacje Hildebrandt Management. Komu co dać:

| Narzędzie | Co przekazać |
|---|---|
| Claude Code, Claude Cowork (dostęp do plików) | cały ten katalog + `CLAUDE.md` w korzeniu repo |
| ChatGPT, Claude w przeglądarce (bez plików) | `prompt-styl.txt` (lub `prompt-style.en.txt`) wklejony na starcie rozmowy |
| Gamma App i inne z własnym motywem | `motyw-gamma.md` — wartości do wpisania w edytorze motywu |
| Człowiek (podwykonawca, agencja) | `STYLE.md` + `referencja/` otwarta w przeglądarce |

## Zawartość

```
STYLE.md              reguły twarde, tokeny, bloki, głos — wersja polska
STYLE.en.md           to samo po angielsku
CLAUDE.md             instrukcja repozytorium (do korzenia repo strony)
prompt-styl.txt       jeden blok do wklejenia w czat (PL)
prompt-style.en.txt   jeden blok do wklejenia w czat (EN)
motyw-gamma.md        wartości motywu dla Gammy i podobnych narzędzi
tokens/
  colors.css          paleta i aliasy semantyczne (--hm-*)
  typography.css      rodzina, grubości, tracking, interlinia, skale
  spacing.css         geometria A4, marginesy, detale, skala odstępów
  fonts.css           @font-face Lato wskazujący na ../fonts/
  fonts-base64.css    @font-face Lato osadzony jako data:font/woff2
  tokens.json         te same wartości maszynowo
fonts/                Lato .woff2 — 12 plików (300/400/400i/700/700i/900 × latin, latin-ext)
referencja/
  hmdesign-web.css    warstwa webowa: klasy sekcji, kart, przycisków, stopki
  index.html          strona główna — wszystkie bloki w jednym miejscu
  uslugi-tes.html     podstrona usługi — ten sam układ, mniej bloków
```

## Który plik fontów

- `tokens/fonts.css` + katalog `fonts/` — gdy strona ma pliki obok siebie. Lżejszy HTML.
- `tokens/fonts-base64.css` — gdy strona ma być **jednym plikiem**, offline-safe, bez
  żadnego zapytania sieciowego. Tak działa dzisiejsza strona hildebrandtmanagement.com.

Nigdy Google Fonts ani inny CDN. To wymóg prywatności, nie preferencja.

## Czego w pakiecie nie ma

Plików logo. Znak jest typograficzny: pomarańczowy kwadrat + logotyp Lato 900,
odtwarzany w HTML (`.wordmark`). Nie rysujemy i nie rekonstruujemy znaku z pamięci.

## Kontakt

Łukasz Hildebrandt · office@hildebrandtmanagement.com · tel. 889 447 117 · hildebrandtmanagement.com · Gdańsk / Trójmiasto
