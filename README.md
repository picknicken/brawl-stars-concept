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

## Modellen en skins
- Karakters zijn procedureel gebouwd (`buildChar`): outlines met constante dikte in schermruimte, rim-licht, knipperende ogen, boze wenkbrauwen bij schieten, wapperende sjaals, haar en capes
- Skins zijn recepten (`SKIN_RECIPES`): eigen kleurenpalet, verborgen basisonderdelen en extra onderdelen uit de `ACC`-bibliotheek (pompoenhoofd, vleugels, heksenhoed, schedel, bandages, wolfskop, slijm, spookstaart, ...)
- Een nieuwe skin toevoegen: een regel in `SKINS` (naam, zeldzaamheid, prijs) en een recept in `SKIN_RECIPES`

## 3D-modellen (GLB)

De knokkers en skins gebruiken echte geriggde 3D-modellen uit `assets/models/` (KayKit Adventurers & Skeletons door Kay Lousberg, **CC0**, zie `assets/LICENSE-KayKit.txt`). Skins zijn andere modellen, andere wapens en/of kleurtinten.

- GLB-bestanden kunnen niet via `file://` geladen worden: start een server, bv. `npx http-server -c-1 .`, en open `http://localhost:8080`.
- Lukt het laden niet, dan valt het spel terug op de procedurele modellen.
- Eigen (gratis) modellen toevoegen: zet een `.glb` met animaties in `assets/models/` en verwijs ernaar in `GLB_BASE` / `SKINS`. Goede CC0-bronnen: KayKit, Kenney, Quaternius, OpenGameArt; animaties via Mixamo.

## Maps

Vier thema-arena's, elk met eigen indeling per modus, verlichting, props, wandstijl en sfeerdeeltjes: Zonnepark (park), Rode Canyon (woestijn), Ijsvelden (sneeuw) en Spookkerkhof (nacht, fakkels). Na elke wedstrijd wisselt de map; de hub toont de volgende arena.
