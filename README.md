# Arena Brawlers

Prototype van een Brawl Stars-achtige 3v3 arena-game in 3D (three.js, toon-shading + outlines; eigen namen en art).

Speel: open `index.html` in een browser (of `npx http-server`).

- **Modi:** Gem Grab (houd 10 gems vast) en Brawl Ball (scoor 2 goals, golden goal bij gelijkspel)
- **6 brawlers:** Cinder (shotgun), Falco (sniper), Granite (tank), Rime (vertraagt/bevriest), Lyric (heelt teamgenoten), Vanta (snelle dolken + dash)
- **Besturing:** pc: WASD, muis, klik, E = auto-aim, spatie = Super, M = geluid. Mobiel: tik op de aanvalsknop = auto-aim, sleep = zelf richten
- **Bots:** drie moeilijkheden, voorspellen je beweging, ontwijken kogels, verdelen gems/rollen, spelen Brawl Ball
- **Geluid:** procedureel (WebAudio), geen audiobestanden

## Voortgang (meta-game)
- **Valuta:** munten, energie (upgraden) en kristallen
- **Knokkers:** 3 ontgrendeld, de rest via kisten of het trofeeënpad. Levels 1-7 (+8% levens en schade per level)
- **Skins:** monster-skins als kleurvarianten (Pompoen, Zombie, Heks, Vampier, ...)
- **Kisten:** hout, zilver, goud. Je krijgt er na elk gevecht een, plus een gratis kist per dag
- **Opdrachten, seizoenspas en trofeeënpad**, plus een winkel
- Alles wordt in de browser bewaard (localStorage)
