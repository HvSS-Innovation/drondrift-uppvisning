# DRÖNDRIFT — uppvisningsläge

Publik webbsida som beräknar avdrift vid motorbortfall för UAV06A med **live vinddata** från [Open-Meteo](https://open-meteo.com/).

Denna site är en variant av kalkylatorn på [7srapport.com/drondrift.html](https://7srapport.com/drondrift.html). Skillnaden är att den här siten:

- Hämtar realtids-vind och -riktning från ett externt API (Open-Meteo, EU)
- Använder browser-geolocation för att veta var du är
- Är publik och **inte** del av den OPSEC-skyddade 7srapport.com-miljön

Sidan är tänkt för **uppvisningsläge** — civil publik närvarande, planeringssituation där OPSEC-känslig användning inte är aktuell.

## Live URL

https://hvss-innovation.github.io/drondrift-uppvisning/

## Funktion

1. Tillåt geolocation (eller skriv ort manuellt)
2. Ange flyghöjd
3. Hämta vinddata-knappen → Open-Meteo svarar med vindstyrka och vindriktning på ungefärlig flyghöjd
4. Kalkylatorn räknar säkerhetszon nedvinds (samma modell: ballistisk + 1:1-regeln, det större värdet rekommenderas)

## Vad lagras?

- **Ingenting** skickas till denna repos servrar (det finns inga — det är statisk site på GitHub Pages)
- Senaste valda höjd/vind/riktning sparas i **localStorage** på din enhet
- Vinddata-anrop går till Open-Meteo. De [loggar inte IP-adresser per sin policy](https://open-meteo.com/en/terms)
- Ingen telemetri, inga cookies, inga tredjepartsskript utöver Open-Meteo-anropet

## Säkerhetsrapporter

Mejla nijoda@gmail.com — märk ämnesraden "drondrift-uppvisning security".

## Licens

AGPL-3.0. Se [LICENSE](LICENSE).

## Tredjepartsdata

Vinddata från [Open-Meteo](https://open-meteo.com/) (CC-BY 4.0 enligt deras attribution-krav). Geokoding via [Open-Meteo Geocoding API](https://open-meteo.com/en/docs/geocoding-api).
