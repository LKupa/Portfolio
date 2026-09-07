# Jak si nastavit vlastní portfolio na GitHub Pages

Tento návod vám ukáže, jak si z tohoto repozitáře (šablony) vytvořit **vlastní** portfolio, které bude fungovat jako webová stránka.

## 1. Vytvořte si vlastní kopii repozitáře

1. Na hlavní stránce repozitáře klikněte na tlačítko **„Use this template"** → **„Create a new repository"**.
   - Tím vznikne úplně nový repozitář jen váš, oddělený od šablony (na rozdíl od Fork nebude propojený historií commitů se šablonou).
2. Zvolte si název repozitáře – nejlépe krátký a bez diakritiky, např. `moje-portfolio`.
3. Ujistěte se, že je repozitář **Public** – GitHub Pages ve zdarma verzi fungují jen u veřejných repozitářů (pokud nemáte placený účet).

## 2. Zapněte GitHub Pages

1. V novém repozitáři jděte do **Settings** → **Pages** (v levém menu).
2. V sekci **Build and deployment** → **Source** vyberte **Deploy from a branch**.
3. Jako **Branch** vyberte `main` a složku `/ (root)`.
4. Klikněte **Save**.
5. Po chvíli (obvykle do 1–2 minut) se nahoře objeví odkaz na váš web ve tvaru:
   `https://<vase-uzivatelske-jmeno>.github.io/<nazev-repozitare>/`

## 3. Upravte základní údaje

Než začnete psát vlastní bloky, ověřte si a upravte soubor `_config.yaml`:

```yaml
title: Tvoje jméno
logo: /logo.png
description: Krátký popis tvého portfolia
remote_theme: pages-themes/minimal@v0.2.0
plugins:
  - jekyll-remote-theme
```

- `title` a `description` – přepište na svoje údaje (v šabloně je zatím jméno autora šablony).
- `logo` – buď necháte výchozí obrázek, nebo nahradíte vlastním `logo.png` ve stejném formátu a názvu.
- `about.md` – přepište vlastním krátkým představením.

Po uložení změny stačí počkat cca minutu, GitHub Pages se přebuildí automaticky při každém commitu do `main`.

## 4. Přidávejte obsah

Nové bloky přidáváte jako další `.md` soubory do `portfolio/blocks/` (praktická část) a `portfolio/teorie/` (teorie) a přidáte na ně odkaz do `README.md`, stejně jako u bloků 1–7.

### Odstranění ukázkových bloků

Šablona obsahuje 7 už vyplněných ukázkových bloků (Python, webová stránka, 3D grafika, Arduino, vektorová grafika, 3D tisk, střih videa). Ty slouží jako vzor a do vašeho portfolia nepatří – je potřeba je smazat a nahradit vlastními:

1. Ve svém repozitáři na GitHubu otevřete složku `portfolio/blocks/`.
2. U každého souboru, který nechcete použít (např. `blok-01.md` až `blok-07.md`), klikněte na tři tečky u souboru (nebo ho otevřete a v editaci zvolte možnost smazat) a potvrďte commit.
3. Stejně postupujte ve složce `portfolio/teorie/` u odpovídajících souborů `teorie-01.md` až `teorie-07.md`.
4. Pokud pracujete s repozitářem lokálně (přes Git), stačí smazat soubory ve složkách a změny commitnout a pushnout stejně jako u jakékoli jiné úpravy.

### Aktualizace README

`README.md` není jen popis repozitáře – je to zároveň **úvodní stránka (landing page)** vašeho webu, protože se zobrazuje na hlavní adrese portfolia. Po smazání ukázkových bloků a přidání vlastních je proto nutné README aktualizovat, jinak budou odkazy na hlavní stránce vést na soubory, které už neexistují:

- Odstraňte odkazy na smazané ukázkové bloky.
- Přidejte odkazy na vaše nové bloky (praktická část i teoretické pozadí) ve stejném formátu, v jakém jsou uvedeny stávající bloky.
- Zkontrolujte i odkaz na `about.md` a na návod k Markdown syntaxi, ať zůstanou funkční.

Pokud zatím nechcete řešit mazání souborů, postačí z `README.md` odstranit části odkazující na tyto soubory a fyzicky mohou zůstat a z webové stránky se na ně nedostanete.

---

# Přehled témat (themes), která jdou nastavit bez velké práce

GitHub Pages má sadu **oficiálně podporovaných** Jekyll témat. Stačí v `_config.yaml` změnit řádek `remote_theme:` (šablona už má `jekyll-remote-theme` plugin zapnutý, takže nic dalšího nastavovat nemusíte) a během minuty se web přebuildí s novým vzhledem.

| Téma | Styl | Nastavení v `_config.yaml` |
|---|---|---|
| **Minimal** *(aktuálně použité)* | Čisté, jednoduché, boční panel s odkazy | `remote_theme: pages-themes/minimal@v0.2.0` |
| **Cayman** | Moderní, velký barevný nadpis nahoře | `remote_theme: pages-themes/cayman@v0.2.0` |
| **Architect** | Tmavý postranní panel, technický vzhled | `remote_theme: pages-themes/architect@v0.2.0` |
| **Slate** | Tmavý, „vývojářský" styl | `remote_theme: pages-themes/slate@v0.2.0` |
| **Midnight** | Tmavé pozadí, hodí se pro noční/hackerský vzhled | `remote_theme: pages-themes/midnight@v0.2.0` |
| **Dinky** | Kompaktní, malý postranní panel | `remote_theme: pages-themes/dinky@v0.2.0` |
| **Hacker** | Terminálový/monospace vzhled | `remote_theme: pages-themes/hacker@v0.2.0` |
| **Merlot** | Elegantní, seriózní | `remote_theme: pages-themes/merlot@v0.2.0` |
| **Leap Day** | Výrazné barvy, oblejší tvary | `remote_theme: pages-themes/leap-day@v0.2.0` |
| **Modernist** | Strohý, novinový styl | `remote_theme: pages-themes/modernist@v0.2.0` |
| **Tactile** | Jemné textury na pozadí | `remote_theme: pages-themes/tactile@v0.2.0` |
| **Time Machine** | Retro, „historizující" vzhled | `remote_theme: pages-themes/time-machine@v0.2.0` |
| **Primer** | Vzhled podobný samotnému GitHubu | `remote_theme: pages-themes/primer@v0.6.0` |

**Tip:** než se rozhodnete, můžete si všechna témata prohlédnout naživo na náhledových stránkách jednotlivých témat (např. `https://pages-themes.github.io/minimal/`, `https://pages-themes.github.io/cayman/` atd. – stačí nahradit název tématu v odkaze).

> Pozn.: Verze za `@` (např. `v0.2.0`) odpovídá poslední stabilní verzi tématu v době psaní tohoto návodu. Pokud chcete mít vždy nejnovější verzi, dá se `@verze` vynechat úplně a napsat jen `remote_theme: pages-themes/minimal` – riskujete tím ale, že se vzhled časem sám změní bez vašeho vědomí.
