
# Context
" Do global crisis affect the real estate market in France?"

This analysis studies the real estate transactions in France between 2014 & 2022.

# Data source

https://www.kaggle.com/datasets/benoitfavier/immobilier-france?datasetId=2832731&sortBy=dateRun&tab=profile

**About Dataset**
From kaggle, I use  only the dataset containing the history of nearly all of the real estate transactions concerning a single house/apartment in France from 2014 to 2022 from DVF.

This dataset is provided under a permissive licence, and is free to use for commercial applications. It has a vocation of helping research concerning the dynamics of real estate prices.

DVF stands for "Requests for property values" dataset, published and produced by the Directorate General of Public Finance, provides information on property transactions over the last five years in mainland France and the French overseas departments and territories, with the exception of Alsace, Moselle and Mayotte. The data contained in this database is derived from notarised deeds and cadastral information.

**Sources of geojson file**
INSEE for names and codes (2018 edition).
IGN / Admin Express COG for the routes (2018 edition)
How were these files generated?
The data comes from a conversion of the routes from the SHP format supplied by IGN to the GeoJSON format via Mapshaper (cli).

IGN data is extremely accurate, so to optimise file size the files have been simplified in 2 ways:

The precision of the coordinates has been limited (in accordance with the recommendations of the GeoJSON standard) to 5 digits after the decimal point, which corresponds to a margin of around 1.11 metres.
The plots have been simplified (using the "visvalingam weighted" method) to 25% (the lower the figure, the greater the simplification).
Example of a mapshaper command to convert an IGN shapefile (input.shp) to geojson format with the parameters described above 

The file used is *departements-version-simplifiee.geojson*:
https://github.com/gregoiredavid/france-geojson/blob/master/departements-version-simplifiee.geojson
### Questions

##### trends
- What is the real estate trend in France?
- How major events (COVID pandemic, Ukrainian war) impact the real estate dynamic

##### geographic
- What are the regions/ departments with the most/the least transactions?
- How the region affect the number of transactions ?

##### Property type
- What kind of property is the most exchanged on the market?
- How the number of rooms affect the property price?
-  What is the evolution of price based on type of building?

### Data types

- check excel doc: Data manipulations report

### Limitations & Ethics

#### Limitations
**Geographic:** In terms of geographical scope, DVF is available for mainland France, excluding Alsace and Moselle, as well as the French overseas departments and territories (DROM), except Mayotte.

**Privacy Concerns:** The dataset potentially contains sensitive information about property buyers and sellers. While personal identifiers may be removed, there could still be privacy implications when analyzing and sharing this data.

#### Ethical Considerations

**Privacy:** the dataset is anonymised but care must be taken because of the precise adress information we have

The data is free to use under an open 2.0 licence:
https://www.etalab.gouv.fr/wp-content/uploads/2018/11/open-licence.pdf


### Data manipulations

check Data manipulations report.xlsx

### Specific notes
The dataset has a "number of room" variable which display sometimes a value of "0".
the documentation advices to merge 0 & 1.
http://doc-datafoncier.cerema.fr/dv3f/doc/variable/local/nbpprinc


