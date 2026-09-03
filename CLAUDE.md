# hildebrandtmanagement.com — HMDesign obowiązuje

Strona Hildebrandt Management (GitHub Pages, repo `LukaszHilde/lukaszhilde.github.io`).
Obowiązkowo używa systemu wizualnego **HMDesign**. Nie wprowadzamy własnej palety,
własnego kroju ani własnych komponentów.

**Kanon:** `C:\Users\Łukasz\Dropbox\HM_HOMAI_OS\08_ZASOBY\HMDesign\`
Specyfikacja: `SPEC.md` · Reguły obowiązkowe: `ZGODNOSC.md`

**Treść strony podlega `GLOS.md`** z tego samego kanonu: nazwy produktów
(TES+, obieg zdarzeń z odpowiedzialnością, widok zarządczy), zdania kanoniczne,
zasada dowodu i ton. Wygląd — HMDesign, treść — GLOS.md. Zmiana tekstu zaczyna
się w `GLOS.md`, nie w `index.html`.

## Jak system jest tu wpięty

Strona to **dwa samodzielne pliki** — `index.html` (PL) i `english/index.html` (EN)
— bez buildu i bez zewnętrznych zasobów. Dlatego tokeny HMDesign są **wklejone
inline** w `<style>`, a Lato jest osadzone jako `data:font/woff2`.

To jest świadomy wyjątek od „linkuj `hmdesign/styles.css`", a nie zaniedbanie —
jednoplikowość jest tu cechą, nie skrótem. Stan na 2026-09-02: wklejone tokeny są
**zgodne co do wartości** z `hmdesign/tokens/colors.css` w kanonie.

**Obowiązek:** przy zmianie systemu tokeny **przepisujemy z kanonu**, nie
poprawiamy ręcznie na miejscu. Wartość zmieniona lokalnie to błąd, nie wariant.
Zmiany trzymamy zsynchronizowane w obu językach.

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

## Publikacja — pułapka remote'ów

Push **wyłącznie** przez GitHub Desktop zalogowany kontem **LukaszHilde**.
Istnieje fork `hmaicentrum-lgtm/lukaszhilde.github.io` **bez GitHub Pages**;
gdy GitHub Desktop przepnie `origin` na fork, push „się uda", a strona się nie
zmieni. Poprawny stan remote'ów:

```
git remote set-url origin https://github.com/LukaszHilde/lukaszhilde.github.io.git
git remote remove upstream
```

W sesjach Claude Code `git push` nie zadziała (brak dostępu do tokenu GitHub Desktop)
— odczyt (`git fetch`, API) działa, bo repo jest publiczne.

## Odstępstwa

| Odstępstwo | Powód | Data |
|---|---|---|
| Tokeny i fonty wklejone inline zamiast linkowane z `hmdesign/styles.css` | Strona jest celowo jednoplikowa i w 100% offline-safe; brak buildu | 2026-09-02 |
