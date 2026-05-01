# Tarjousvertailun laskentatyökalut

Selainpohjainen työkalu julkisten hankintojen tarjousvertailuun. Sisältää **painotuslaskurin** (auttaa määrittämään hinnan ja laadun painotuksen) ja **vertailulaskurin** (simuloi tarjousvertailun lopputuloksen eri painotuksilla ja laskentatavoilla).

Työkalu on yksittäinen `index.html`-tiedosto, joka käyttää Reactin ja Babelin CDN-versioita. Asennusta tai build-vaihetta ei tarvita — pelkkä julkaisu GitHub Pagesin kautta riittää.

## Julkaisu GitHub Pagesin kautta

### 1. Luo uusi GitHub-repositorio

1. Kirjaudu sisään osoitteessa [github.com](https://github.com).
2. Klikkaa oikeasta yläkulmasta **+** → **New repository**.
3. Anna repolle nimi, esim. `tarjousvertailu`.
4. Valitse **Public** (Pages on ilmainen julkisille repoille).
5. Klikkaa **Create repository**.

### 2. Lataa `index.html` repoon

Helpoin tapa selaimessa:

1. Avaa juuri luotu repo.
2. Klikkaa **Add file** → **Upload files**.
3. Raahaa `index.html` (ja halutessasi tämä `README.md`) sivulle.
4. Klikkaa **Commit changes**.

Vaihtoehtoisesti komentoriviltä:

```bash
git clone https://github.com/<käyttäjänimesi>/tarjousvertailu.git
cd tarjousvertailu
# kopioi index.html ja README.md tähän kansioon
git add .
git commit -m "Lisää tarjousvertailun työkalu"
git push
```

### 3. Ota GitHub Pages käyttöön

1. Avaa repon **Settings**-välilehti.
2. Vasemman palkin valikosta **Pages**.
3. Kohdassa **Source** valitse **Deploy from a branch**.
4. Kohdassa **Branch** valitse **main** ja kansioksi **/ (root)**.
5. Klikkaa **Save**.

GitHub kääntää sivun julkiseksi noin 1–2 minuutin kuluessa. Osoite näkyy samalla Pages-sivulla, ja se on muotoa:

```
https://<käyttäjänimesi>.github.io/tarjousvertailu/
```

### 4. Päivitykset

Aina kun lataat uuden version `index.html`:stä `main`-haaraan, GitHub Pages päivittää sivun automaattisesti muutaman minuutin kuluessa. Selaimessa voi joutua tyhjentämään välimuistin (Ctrl+F5 / Cmd+Shift+R) nähdäkseen muutokset heti.

## Oman domainin käyttö (valinnainen)

Jos haluat käyttää omaa domain-osoitetta (esim. `laskuri.example.fi`):

1. Lisää repon juureen `CNAME`-niminen tiedosto, jonka sisältönä on pelkkä domain (ilman `https://`-etuliitettä).
2. Lisää domain-rekisteröijällesi `CNAME`-tietue, joka osoittaa osoitteeseen `<käyttäjänimesi>.github.io`.
3. Tarkista repon **Settings → Pages** -kohdasta, että custom domain on tunnistettu.

## Tekninen huomio

Työkalu käyttää [Babel Standalonen](https://babeljs.io/docs/babel-standalone) selainpohjaista JSX-käännöstä. Tämä on tarkoituksellisesti yksinkertainen ratkaisu, joka toimii ilman Node.js:ää tai build-työkaluja. Latausaika on hieman pidempi kuin esikäännetyllä versiolla, mutta yksittäiselle työkalulle riittävä.

Jos haluat tuotantotason version (Vite + esikäännetty bundle), JSX-lähde löytyy tästä samasta kansiosta nimellä `Tarjousvertailun laskentatyökalut.jsx` ja sen voi siirtää suoraan Vite-projektin `App.jsx`:ksi.

## Lisenssi

© Ilkka Paukkunen
