# Dynamic energy prices
If you want to make smart decisions regarding electricity prices one needs to know the actual electricity price.
## APEX Energy price 
Plain energy prices from APEX can be obtained via [energy-charts.info](https://energy-charts.info) in EUR/MWh

More information on the api can be found here: [https://api.energy-charts.info/#/prices](https://api.energy-charts.info/#/prices)
This node-red flow can be easily adjusted to any of the countries below by replacing NL to the corresponding country code in the http request node

- AT (Austria)
- BE (Belgium)
- CH (Switzerland)
- CZ (Czech Republic)
- DE-LU (Germany, Luxembourg)
- DE-AT-LU (Germany, Austria, Luxembourg)
- DK1 (Denmark 1)
- DK2 (Denmark 2)
- FR (France)
- HU (Hungary)
- IT-North (Italy North)
- NL (Netherlands)
- NO2 (Norway 2)
- PL (Poland)
- SE4 (Sweden 4)
- SI (Slovenia) 
![energy-charts.info flow](/images/energy-charts.info.gif)

## Frank energie
Frank energie is a energy provider in The Netherlands and Belgium. In The Netherlands the total energy price for consumers is a sum of the following:
- APEX price + VAT
- Additional energy tax for 2025 it is € 0,10154 (ex VAT) or €0,1286 (inc VAT) for households [belastingdienst](https://www.belastingdienst.nl/wps/wcm/connect/bldcontentnl/belastingdienst/zakelijk/overige_belastingen/belastingen_op_milieugrondslag/energiebelasting/)
- Fee energy provider

Even though APEX prices changes every 15min, Frank energie applies hourly prices. The hourly price applied by Frank energie is the average of APEX price for that hour.

Frank energie has a GraphQL api available, more details can be found through this link: [https://reversed.notion.site/Marktprijzen-API-89ce600a88ac4abe8c2ad89d3167a83e](https://reversed.notion.site/Marktprijzen-API-89ce600a88ac4abe8c2ad89d3167a83e) 
Node-red flow to request the day ahead price for Frank energie.
![Frank energie flow](/images/Frank%20energie.gif)
