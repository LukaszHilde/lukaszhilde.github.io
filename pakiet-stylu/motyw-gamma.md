# Motyw dla Gammy i narzędzi z własnym edytorem motywu

Gamma, Canva, Beautiful.ai i podobne nie czytają plików CSS — przyjmują wartości
w edytorze motywu. Poniżej dokładnie to, co należy tam wpisać. Wpisanie motywu to
czynność ręczna, jednorazowa; potem motyw zapisuje się i wybiera z listy.

## Nazwa motywu

`HMDesign`

## Kolory

| Pole w edytorze | Wartość |
|---|---|
| Accent / Primary | `#EB5C25` |
| Text / Heading | `#232120` |
| Body text | `#48494B` |
| Background (light) | `#FFFFFF` |
| Background (alt) | `#F6F7F7` |
| Background (dark) | `#232120` |
| Border / Divider | `#E4E5E5` |
| Link hover | `#C9481A` |

Nie dodawaj czwartego koloru. Nie używaj palet automatycznych ani „color harmony".

## Typografia

| Pole | Wartość |
|---|---|
| Heading font | Lato — waga 900 (Black) |
| Body font | Lato — waga 400 |
| Emphasis | Lato 700 |
| Heading case | wielkość zdaniowa (wyłącz automatyczne CAPS) |
| Heading letter spacing | najciaśniejsze dostępne (-2% do -3%) |

Jeśli narzędzie nie ma Lato: wgraj pliki z `fonts/` przez „upload font".
Nie zastępuj Lato krojem Inter, Roboto, Montserrat ani Arialem, dopóki nie ma zgody.

## Kształty i tło

- Rogi: **0**. Wyłącz zaokrąglenia kart, obrazów i przycisków.
- Cienie: **wyłączone**.
- Tła: płaskie kolory. Wyłącz gradienty, wzory, tekstury i tła generowane przez AI.
- Zdjęcia: tylko rzeczowe zdjęcia budowy lub dokumentów, z ciemnym przykryciem, jeśli
  na zdjęciu jest tekst. Zero grafik stockowych z ludźmi w kaskach na białym tle.
- Ikony: wyłącznie wypełnione, jednokolorowe (`#232120` lub `#EB5C25`). Bez emoji.

## Animacje

Wyłącz przejścia slajdów i animacje wejścia elementów. System jest print-first.

## Układ slajdu

- Etykieta sekcji: WERSALIKI, pomarańcz, tracking szeroki — nad nagłówkiem.
- Nagłówek: Lato 900, wielkość zdaniowa, maks. dwa wiersze.
- Treść: maks. trzy karty w rzędzie albo lista z punktorami `→`.
- Slajd otwierający i zamykający: tło czarne, akcent pomarańczowy.
- Stopka: `Łukasz Hildebrandt · tel. 889 447 117 · hildebrandtmanagement.com`

## Kontrola po wygenerowaniu

Narzędzia generatywne psują trzy rzeczy najczęściej. Sprawdź je za każdym razem:

1. Zaokrąglone rogi kart — wróciły automatycznie.
2. Gradient w tle slajdu tytułowego.
3. Emoji w punktorach.
