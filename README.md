# Dechový event SPIRITUS — Pihel

Statická jednostránková pozvánka na první skupinový dechový event Honzy Spilky.
Neděle 12. 7. 2026, Residence Morris (jurta Luna) v Pihelu.

## Struktura projektu

```
.
├── index.html          # hlavní stránka
├── css/
│   └── styles.css      # veškeré styly
├── js/
│   └── main.js         # scroll reveal, nav, mobilní menu, FAQ akordeon
├── img/                # 6 fotek (jurta, portrét, Prostor Tata)
├── .nojekyll           # zabraňuje GitHub Pages zapnout Jekyll build
├── .gitignore
└── README.md
```

Žádný build krok, žádné závislosti. Otevři `index.html` v prohlížeči
a funguje. Fonty (Poppins + Fraunces) se stahují z Google Fonts.

## Nasazení na GitHub Pages — nejčastější past

**Chyba, kvůli které se stránka načte bez CSS a obrázků:**
nahraješ na GitHub buď samotný ZIP soubor, nebo rozbalenou složku
jako celek. GitHub potom hledá `index.html` v kořeni repozitáře,
ale najde jen `dechovy-event-github/index.html` — a prohlížeč nemá
jak najít `css/styles.css` a `img/`.

**Správný postup: musíš nahrát OBSAH složky, ne samotnou složku.**

### Postup A — přes web (bez příkazové řádky)

1. **Rozbal ZIP** na svém počítači.
2. **Otevři** rozbalenou složku a **označ všechny soubory uvnitř**
   (`index.html`, `css/`, `js/`, `img/`, `README.md`, `.nojekyll`,
   `.gitignore`) — ne tu složku samotnou, ale její obsah.
3. Na GitHubu vytvoř nový repozitář (třeba `dechovka`).
4. Klikni na **Add file → Upload files** a **přetáhni ty označené
   soubory** do okna. Musí se objevit v seznamu `index.html`,
   `css/styles.css`, `img/jurta_hero.jpg` atd. — bez žádného
   nadadresáře.
5. Commit changes.
6. **Settings → Pages → Source: Deploy from a branch → main / (root) → Save**.
7. Za 1–2 minuty adresa `https://TVOJE-JMENO.github.io/dechovka/` běží.

### Postup B — přes Git

```bash
# v rozbalené složce projektu
git init
git add .
git commit -m "první verze webu"
git branch -M main
git remote add origin https://github.com/TVOJE-JMENO/dechovka.git
git push -u origin main
```

Pak stejně: **Settings → Pages → main / (root) → Save**.

### Kontrola, že je vše na správném místě

Po nahrání na GitHubu musíš v hlavním pohledu repozitáře **vidět
rovnou `index.html`, `css/`, `js/`, `img/`** — ne složku, ve které
jsou tyhle věci schované. Pokud tam vidíš složku `dechovy-event-github/`
nebo podobnou, nahrání proběhlo špatně a stránka nebude mít styly.

### Vlastní doména (volitelně)

**Settings → Pages → Custom domain** → napiš doménu, ulož,
u registrátora nastav CNAME záznam na `TVOJE-JMENO.github.io`.

## Testování lokálně

Kliknutí na `index.html` v souborech obvykle funguje, ale spolehlivější
je spustit malý lokální server:

```bash
# v rozbalené složce projektu
python3 -m http.server 8000
```

Pak otevři [http://localhost:8000](http://localhost:8000) v prohlížeči.
Když to funguje lokálně, na GitHub Pages to musí fungovat taky
(pokud jsi soubory nahrál správně dle postupu výše).

## Editace obsahu

- **Texty a struktura sekcí:** `index.html`
- **Barvy, typografie, layout:** `css/styles.css` — celá paleta je
  definovaná nahoře v `:root { --sky, --wood, --sand, --cream, ... }`.
  Změň jednu proměnnou a projeví se všude.
- **Interakce (menu, akordeon, scroll reveal):** `js/main.js`
- **Fotky:** vyměň soubory v `img/` — stejné jméno = žádné další
  úpravy potřeba

## Odkaz na Google Formulář

Vstupní formulář se otevírá v tlačítku "Vyplnit formulář" v sekci
"Formulář". Hledej v `index.html` řetězec `forms.gle`.
