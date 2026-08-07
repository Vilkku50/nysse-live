# Nysse Live

Tampereen Nyssen bussien reaaliaikainen sijaintikartta puhelimessa. Toteutettu asennettavana web-sovelluksena (PWA), joka näyttää bussit kartalla ITS Factoryn GTFS-RT-rajapinnasta.

## Käyttöönotto Android-puhelimessa

1. Odota, että `main`-haaraan tehty push on ajanut "Deploy to GitHub Pages" -workflown loppuun (Actions-välilehti), tai ota GitHub Pages käyttöön kohdasta *Settings → Pages → Source: GitHub Actions*.
2. Avaa julkaistu osoite (`https://<käyttäjätunnus>.github.io/nysse-live/`) Chromella puhelimessa.
3. Avaa selaimen valikko (⋮) ja valitse **Lisää aloitusnäytölle** / **Asenna sovellus**.
4. Sovellus toimii tämän jälkeen omana kuvakkeenaan ilman selaimen käyttöliittymää.

## Tekniikka

- Kartta: [Leaflet](https://leafletjs.com/) + CARTO-taustakartta (tummennettu suodattimella)
- Reaaliaikadata: `https://data.itsfactory.fi/journeys/api/1/gtfs-rt/vehicle-positions/json` (haetaan 5 sekunnin välein)
- Offline-kuori: Service Worker (`sw.js`) välimuistittaa vain sovelluksen kuoren, ei koskaan live-dataa
- Linjasuodatus tekstihaulla tai valitsemalla linjachippejä
