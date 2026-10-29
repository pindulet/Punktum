# Punktum

Skrivetræning for Frede: korte øvelser hvor talesprog bliver til klare, hele sætninger. Ingen grammatik, kun hands-on.

- **Ryd op** – gør talesprog til skriftsprog
- **Byg sammen** – saml små sætninger til én god
- **Del op** – klip lange "og så"-sætninger
- **Svar rigtigt** – svar på spørgsmål i hele sætninger
- **Tjek din egen tekst** – find talesprog i en skoletekst

Appen er `index.html` plus filerne i `vendor/`. Fremskridt gemmes i browseren (localStorage).

## Stavekontrol

Stavekontrollen kører i browseren uden internet efter første indlæsning: Hunspell som WebAssembly med Stavekontroldens danske ordbog (`vendor/da.aff`, `vendor/da.dic`). Sammensatte ord godkendes kun, når de kan deles i to rigtige ord, så fejl som "desvære" og "fodbolkamp" ikke slipper igennem. Forslag sorteres efter, hvor almindelige ordene er (`vendor/da-freq.txt`). Licenser står i `vendor/THIRD-PARTY.md`.

## Claude som skrivecoach

- **På claude.ai** (som artifact) bruger appen den indloggede Claude-konto.
- **På GitHub Pages** kalder appen Claude API'et direkte fra browseren med en API-nøgle, som en voksen sætter ind nederst på forsiden ("For voksne: slå Claude til på denne enhed"). Nøglen gemmes kun i den browsers localStorage og er aldrig en del af koden her.
  - Lav en nøgle kun til Punktum på https://console.anthropic.com/settings/keys og sæt en lille månedlig udgiftsgrænse.
  - Uden nøgle kører appen i øvetilstand: lamperne tjekker teksten, og man sammenligner med et godt bud.

`vendor/anthropic-sdk-0.134.0.js` er Anthropics officielle JavaScript-SDK (`@anthropic-ai/sdk`, MIT-licens, se `vendor/anthropic-sdk-LICENSE`) samlet til én browserfil.
