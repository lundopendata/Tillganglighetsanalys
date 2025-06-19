# Tillgänglighetsanalys
Här är teknisk dokumentation hur man kan sätta upp ett ramverk för att göra Tillgänglighetsanalys för exempelvis en kommun. vi har hämtat inspiration från Göteborgs stads tillgänglighetsanalys https://tillganglighetsmatt.goteborg.se/ .

# Infrastruktur
## Beräkningar
 * Graphhopper
   * Docker
 * Safe FME
## Presentation
 * ESRI Sites
  * ESRI Dashboard
 
# ToDO
## Docker / Graphhopper
Se till att ha en docker miljö där du kan köra graphhopper.

Dockerfilen vi kör finns här https://github.com/lundopendata/graphhopper/tree/gtfs

Se till att skaffa en API nyckel på https://trafiklab.se/ så att skriptet kan ladda ner gtfs-data "GTFS Regional Static data" (I skriptet så laddas endast data för Skåne).

```
docker build --build-arg GTFS_API_KEY=123abc456def -t graphhopper-gtfs https://github.com/lundopendata/graphhopper.git#gtfs
```
```
docker run -p 8989:8989 graphhopper-gtfs
```

Om allt gått som det ska kan du nu nå graphhopper på http://localhost:8989 om du har den lokalt installerad.

## Grundata
Skapa ett lager med poligoner (hexagoner) och ett lager med dess centrumpunkter. Förslagsvis används verktyget "Generate Tesselation". För att få diameter 200 meter så blir arean 34621 meter.
Skapa även ett lager med centrumpunkter för hexagonerna med samma GRID_ID. Använd exempelvif Feature to Point verktyget.
