# hildebrandtmanagement.com — HMDesign obowiązuje

Strona Hildebrandt Management (GitHub Pages, repo `LukaszHilde/lukaszhilde.github.io`).
Obowiązkowo używa systemu wizualnego **HMDesign**. Nie wprowadzamy własnej palety,
własnego kroju ani własnych komponentów.

**Kanon stylu:** `pakiet-stylu/` w tym repozytorium — `STYLE.md` (reguły),
`tokens/` (wartości), `fonts/` (Lato), `referencja/` (działający wzorzec strony
i podstrony). Kopia robocza: `C:\HM\PROJEKTY\strona-www\WYNIKI\pakiet-stylu\`.

**Treść strony podlega zatwierdzonemu stanowi HM** w Notion, strona „HM — SYSTEM"
(przestrzeń HM SYSTEM): https://app.notion.com/p/3d2b1115d89480ffa89dcfc5c776feb1
Obowiązujące usługi (05.09.2026): **TES — wspólna podstawa do porównania ofert**
oraz **Audyt dokumentacji i paczki podwykonawcze**. Ich zatwierdzone teksty są
w `index.html` (sekcja `#uslugi`). Dawne nazwy „TES+", „obieg zdarzeń
z odpowiedzialnością", „widok zarządczy" **nie obowiązują** — nie wracają do treści.
Wygląd — HMDesign; treść — decyzja Łukasza zapisana w Notion. Zmiana tekstu
usług wymaga jego wyraźnego polecenia.

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

E-mail jest głównym kanałem kontaktu (przycisk podstawowy w sekcji Kontakt),
LinkedIn drugim. E-mail i telefon występują w `index.html` i `english/index.html`
w trzech miejscach: przycisk w Kontakcie, lista kontaktowa (`.crow`) i stopka
(`.fmeta`). Zawsze jako `mailto:office@hildebrandtmanagement.com` oraz
`tel:+48889447117` z tekstem `+48 889 447 117`. Zmiana = sześć miejsc, dwa pliki.

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
