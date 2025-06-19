# Tillganglighetsanalys
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
Se till att ha en docker miljö där du kan köra graphhopper.

Dockerfilen vi kör finns här https://github.com/lundopendata/graphhopper/tree/gtfs

Se till att skaffa en API nyckel på https://trafiklab.se/ så att skriptet kan ladda ner gtfs-data "GTFS Regional Static data" (I skriptet så laddas endast data för Skåne).

docker build --build-arg GTFS_API_KEY=123abc456def -t graphhopper-gtfs https://github.com/lundopendata/graphhopper.git#gtfs
