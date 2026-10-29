# Uputstvo za tim -- Overleaf

## 1. Učitavanje projekta
1. Otvoriti Overleaf -> New Project -> Upload Project.
2. Učitati cijeli ZIP. Glavna datoteka je `main.tex`.
3. Compiler: `pdfLaTeX`.
4. U `konfiguracija.tex` su već upisana imena pet članova.
5. Kada izaberete algoritme, popuniti makronaredbe `\AlgJedan` do `\AlgPet`.

## 2. Podjela posla
- Zajednički dio: `poglavlja/01_1_*`, `01_3_*`, `01_4_*`, `02_1_*`, `02_3_*`.
- Svaki član piše **jednu** datoteku `literatura/rad_0X.tex` i **jednu** `modeli/model_0X.tex`.
- `poglavlja/01_2_*` i `02_2_*` automatski uključuju svih pet individualnih datoteka.
- Samo jedna osoba spaja konačne `.tex` datoteke; ne lijepi ih u `main.tex`.

| Član | Naučni rad | Model |
|---|---|---|
| Aldin Velić | `literatura/rad_01.tex` | `modeli/model_01.tex` |
| Bakir Činjarević | `literatura/rad_02.tex` | `modeli/model_02.tex` |
| Danijal Alibegović | `literatura/rad_03.tex` | `modeli/model_03.tex` |
| Haris Mačić | `literatura/rad_04.tex` | `modeli/model_04.tex` |
| Kerim Hajdar | `literatura/rad_05.tex` | `modeli/model_05.tex` |

## 3. Najjednostavnije pozivanje na kod
NEMA oznaka EDA-01/PREP-01 ni tabele za mapiranje ćelija. Napravite **jednu zajedničku Google Colab bilježnicu** čiji naslovi prate izvještaj:

- `1.1 Odabir i učitavanje skupa podataka`
- `1.3 Istraživačka analiza podataka`
- `1.4 Priprema podataka`
- `2.2.1 Model 1: [prvi algoritam]`
- `2.2.2 Model 2: [drugi algoritam]`
- `2.2.3 Model 3: [treći algoritam]`
- `2.2.4 Model 4: [četvrti algoritam]`
- `2.2.5 Model 5: [peti algoritam]`
- `2.3 Poređenje modela i ansambl`

Kada budete imali Colab link, **samo jednom** u `konfiguracija.tex` promijenite `\ColabBiljeznica` (primjer je u komentaru odmah iznad). Svaka referenca automatski upućuje na taj isti Colab, uz naziv odgovarajućeg odjeljka.

U tekstu možete dodati ili promijeniti referencu koristeći:

```tex
\referencaKod{1.3 Istraživačka analiza podataka}
```

Primjer u PDF-u: `Kod: Google Colab bilježnica, odjeljak „1.3 Istraživačka analiza podataka“.`

## 4. Sadržaj PDF-a
PDF sadrži samo stavke iz specifikacije: `1.1`, `1.2`, `1.3`, `1.4`, `2.1`, `2.2`, `2.3`, naslovnicu, sadržaj i nužnu literaturu. **Nema dodataka A/B, inventara na kraju, evidencije eksperimenata, posebnih oznaka ćelija ni dodatnih kontrolnih tabela.**

- Rezultate, grafikone, tabele i obrazloženja stavljati u PDF.
- Python kod ostaje u Google Colabu.
- Zamijenite sva označena mjesta `[Dopuniti: ...]` prije predaje.
- Tabela u 1.3 mora imati red za **svaki stvarno korišteni atribut**.
- Tabele rezultata treba popuniti stvarnim vrijednostima, ne izmišljati.
- U `literatura/izvori.bib` dodati bibliografske zapise za pet pronađenih radova.
- Grafikone iz Colaba kopirati u `slike/` i pozivati s `\slika{slike/naziv.png}{Opis}{fig:oznaka}`.
