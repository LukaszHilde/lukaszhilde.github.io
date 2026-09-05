# HMDesign — reguły obowiązujące

System wizualny Hildebrandt Management. Obowiązuje dla stron, dokumentów A4,
prezentacji 16:9 i materiałów PDF. Wygląd nie jest kwestią gustu wykonawcy —
wartości są ustalone i przenoszone z tokenów.

---

## 1. Zasady twarde

1. Kolory **wyłącznie** przez `var(--hm-…)`. Żadnego nowego hexa poza blokiem tokenów.
2. Krój wyłącznie **Lato**, osadzony lokalnie. **Zero zapytań sieciowych** — bez Google
   Fonts, bez CDN, bez zewnętrznych skryptów i analityki. Wymóg prywatności.
3. `border-radius: 0`. Ostre rogi bez wyjątku.
4. Karty: ramka `1px var(--hm-hairline)`, **bez cienia**. Cień istnieje tylko pod kartką
   A4 i slajdem w widoku ekranowym.
5. **Bez emoji.** Dozwolone glify: `→` `✕` `✉`. Punktory list to `→`, negacja `✕`.
6. Nagłówki Lato 900, wielkość zdaniowa. WERSALIKI tylko w eyebrow i etykietach
   (tracking .16–.18em, w kolorze akcentu).
7. Zieleń `--hm-green*` tylko dla wątku „sustainability". Maksymalnie ~3 kolory na kompozycję.
8. Bez gradientów, tekstur i zdjęć dekoracyjnych. Bez animacji poza `:hover` linku.
9. Logo **nie rysujemy z pamięci** — znak jest typograficzny: pomarańczowy kwadrat + Lato 900.
10. Wartość spoza tokenów wymaga decyzji człowieka. Narzędzie **pyta**, nie dobiera samodzielnie.

---

## 2. Paleta

| Token | Hex | Użycie |
|---|---|---|
| `--hm-orange` | `#eb5c25` | akcent podstawowy |
| `--hm-orange-deep` | `#c9481a` | hover / press |
| `--hm-black` | `#232120` | atrament, logotyp, sekcje mocne |
| `--hm-white` | `#ffffff` | powierzchnia podstawowa |
| `--hm-grey-700` | `#48494b` | tekst prowadzący, listy |
| `--hm-grey-600` | `#6a6b6d` | opisy kart |
| `--hm-grey-500` | `#919295` | stopki, podpisy |
| `--hm-grey-400` | `#b4b5b7` | numery, separatory |
| `--hm-grey-300` | `#d1d3d3` | linia mastheadu, jasny tekst na czerni |
| `--hm-grey-200` | `#e4e5e5` | włoskowate linie, ramki kart |
| `--hm-grey-100` | `#f6f7f7` | tło sekcji szarych, nagłówki tabel |
| `--hm-peach` | `#fdefe9` | **wyłącznie** tło jasnego callouta |
| `--hm-green-deep` | `#034745` | wyłącznie „sustainability" |
| `--hm-green` | `#12a537` | wyłącznie „sustainability" |

Akcent dokumentu podmieniany jedną linią: `:root{ --hm-accent: … }`.
Dozwolone: pomarańcz, czerń, zieleń-deep. Nic innego.

Bez ciepłych beżów. Bez chłodnych, niebieskawych szarości.

---

## 3. Typografia

Rodzina: `--hm-font: 'Lato', Arial, Helvetica, sans-serif`.
Grubości: 300 sporadycznie · 400 body · 700 wyróżnienia · 800 etykiety i karty · 900 nagłówki.

Skala webowa (z działającej strony):

| Element | Wartość |
|---|---|
| H1 hero | `clamp(38px, 6vw, 76px)`, waga 900, tracking `-.025em`, interlinia 1.04 |
| H2 sekcji | `36px`, tracking `-.01em`, interlinia 1.08 |
| Lead | `19px`, interlinia 1.5, `--hm-grey-700`, `max-width: 64ch` |
| Podtytuł hero | `20px`, interlinia 1.5, `--hm-grey-300`, `max-width: 60ch` |
| Body | `16px`, interlinia 1.55, `--hm-grey-700`, `max-width: 66ch` |
| Eyebrow | `13px`, waga 800, tracking `.18em`, UPPERCASE, akcent |
| Tytuł karty | `18px`, waga 800 |
| Tekst karty | `14.5px`, interlinia 1.5, `--hm-grey-600` |

Body nigdy poniżej 16 px. `text-wrap: balance` na nagłówkach, `pretty` na akapitach.
Skale A4 (pt) i deck 16:9 (px) — w `tokens/typography.css`.

---

## 4. Layout — strona

- Kolumna: `.wrap{max-width:1120px;margin:0 auto;padding:0 40px}`, na telefonie `0 24px`.
- Sekcja: `.section{padding:88px 0}`, na telefonie `64px 0`.
- Warianty tła sekcji: biel (domyślnie), `--hm-grey-100`, `--hm-black`. Nic więcej.
- Rytm strony: hero na czerni → pasek intro → sekcje naprzemiennie biel / szarość →
  sekcja ciemna → kontakt na czerni → stopka na czerni.
- Siatki: 3 karty na desktopie, 1 kolumna poniżej 900 px. Siatka „tabelowa" robiona
  `gap:1px` na tle `--hm-hairline` — linie zamiast odstępów.
- Pasek akcentu 6 px u góry strony (`.topbar`). W dokumencie A4: 2,5 mm. W decku: 10 px.
- Ukośnik 62° w prawym górnym rogu hero — dwie kreski: akcent 12 px i biała 18% 5 px.

## 5. Layout — dokument i prezentacja

- A4 `210×297 mm`, marginesy kolumny 10 / 13 / 11 mm, siatka kart z gapem 2,6 mm.
- Deck `1920×1080 px`, pasek 10 px, tekst nigdy poniżej 24 px.
- Stopka przyklejona do dołu strony, z włoskowatą linią i pełnym kontaktem.

---

## 6. Bloki

Nazwy klas z działającej strony — trzymamy je, nie wymyślamy nowych.

| Klasa | Co to |
|---|---|
| `.topbar` | pasek akcentu 6 px |
| `.siteheader`, `.nav` | sticky nagłówek, wysokość 64 px, dolna linia hairline |
| `.wordmark` | znak: kwadrat 15 px + „Hildebrandt Management" Lato 900, 20 px |
| `.eyebrow` | kreska 36×3 px + WERSALIKI w akcencie |
| `.hero` | sekcja na czerni z ukośnikiem, H1 z `.accent` na jednym fragmencie |
| `.intro` | pasek pod hero, jedno zdanie 22 px, dolna linia |
| `.section`, `.section--grey`, `.section--dark` | sekcje |
| `.shead`, `.snum` | nagłówek sekcji: numer + eyebrow + H2 + lead |
| `.grid`, `.card`, `.card--bar` | siatka kart z liniami 1 px |
| `.offer`, `.ocard` | krótkie karty ofertowe (3 elementy) z paskiem 3 px u góry |
| `.svc`, `.scard` | **karta usługi** — 2 kolumny; numer, tytuł 22 px/900, pytanie 17 px, akapity 15 px z odstępem 12 px, „Do rozpoczęcia" 14 px `--hm-grey-500`, link CTA 15 px/800 w akcencie |
| `.proof__num` | liczba dowodu: 34 px, waga 900, akcent, nad tytułem karty `.card--bar`. Używać tylko z liczbami potwierdzonymi i nieidentyfikującymi klienta; obecna strona ich nie pokazuje |
| `.nav__check`, `.nav__toggle` | menu mobilne: checkbox + etykieta „Menu", lista rozwijana poniżej 900 px; działa bez JS, opcjonalny skrypt inline zamyka menu po kliknięciu odnośnika |
| `.princ`, `.pcell` | siatka zasad |
| `.callout` | tło peach, lewa krawędź 6 px w akcencie, waga 700 |
| `.about`, `.about__mark`, `.tag` | sekcja „o mnie" + tagi w ramce akcentu |
| `.contact`, `.cbox`, `.crow` | kontakt na czerni: etykieta 96 px + wartość |
| `.btn--primary`, `.btn--ghost`, `.btn--ghost-dark` | przyciski, zawsze z `→` w środku |
| `.footer` | stopka na czerni, dane kontaktowe + copyright |

Kompletny arkusz: `referencja/hmdesign-web.css`. Nowa strona to nowy zestaw treści
w istniejących blokach, **nie** nowy arkusz styli.

---

## 7. Stany i ruch

- Link `:hover` → `--hm-accent`, przejście `color .15s ease`. Nic poza tym się nie rusza.
- Stan aktywny / press → `--hm-orange-deep`.
- `:focus-visible` → widoczna ramka w kolorze akcentu. Obsługa klawiatury jest wymagana.
- Zaznaczenie tekstu: tło pomarańcz, tekst biały.
- Bez animacji wejścia, parallaksy, liczników, karuzel.

---

## 8. Głos i treść

Język polski, zdania krótkie i orzekające. Do klienta forma **Ty** — tak mówi
żywa strona i zatwierdzone teksty usług („Zbierasz oferty…", „Otrzymujesz…").
O sobie w pierwszej osobie („Opracowuję", „Sprawdzam"). Narzędzia AI są tłem,
nie bohaterem — nie opisujemy „systemu", opisujemy usługę i jej wynik.

- Nie obiecujemy — opisujemy, co system robi i **czego nie robi**.
- Uczciwość co do granic jest częścią głosu.
- Konkret zamiast okrągłości: liczba, termin, zakres.
- Nagłówki w wielkości zdaniowej. Nigdy CAPS w nagłówku.
- Separator inline: środkowa kropka `·`.
- Klient jest partnerem, nie „leadem".

**Treść strony podlega zatwierdzonemu stanowi HM w Notion** („HM — SYSTEM").
Nazwy usług, ich opisy i liczby w sekcji Dowód zmienia wyłącznie Łukasz.
Dawne nazwy produktów („TES+", „obieg zdarzeń", „widok zarządczy") nie obowiązują.

---

## 9. Dostępność

Pułapka: jasna karta wewnątrz `.section--dark` dziedziczy `color:#fff` po sekcji.
Każda biała powierzchnia w sekcji ciemnej musi jawnie wracać do `var(--hm-black)`.

- Kontrast tekstu do tła co najmniej 4,5:1 (3:1 dopuszczalne wyłącznie dla nagłówków).
- Pełny atrament na tłach akcentu — nie przygaszamy tekstu przez `opacity`.
- Każda sekcja ma `aria-labelledby` wskazujący na własny nagłówek.
- Nawigacja klawiaturą z widocznym focusem. Menu mobilne działa bez JS albo degraduje czysto.
- `lang` ustawiony poprawnie; nazwy własne w `<span translate="no" class="notranslate">`.

---

## 10. Kryteria odbioru

- [ ] Wszystkie rogi ostre, żaden element nie ma cienia.
- [ ] Zero zapytań sieciowych — sprawdzone w zakładce Network.
- [ ] Każdy kolor pochodzi z `var(--hm-…)`.
- [ ] Nagłówki w wielkości zdaniowej, eyebrow w wersalikach z trackingiem.
- [ ] Punktory to `→`, brak emoji.
- [ ] Kontrast tekstu ≥ 4,5:1.
- [ ] Strona czytelna na 360 px i przy wydruku do PDF.
- [ ] Stopka i Kontakt z pełnym kontaktem: office@hildebrandtmanagement.com, tel. 889 447 117, Gdańsk / Trójmiasto. E-mail jako przycisk podstawowy.
- [ ] Menu mobilne działa bez JS (checkbox), fokus widoczny.
- [ ] Wersje PL i EN zsynchronizowane co do struktury.
