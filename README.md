CO_Data
===

Files useful for merging Colombia GIS records with [IPUMS microdata](https://international.ipums.org/international/), at least for the 2005 census. 

Data Sources
---
The original Colombia department shapefile was obtained from [https://sites.google.com/site/seriescol/shapes](https://sites.google.com/site/seriescol/shapes). I found this shapefile to be superior to the one found at [http://www.diva-gis.org/gdata](http://www.diva-gis.org/gdata) which lacked Bogotá.

Files
---

- `CO_DEPT_IPUMS.tsv`: Mapping with FIPS-10, MIGCO2, and DEPTCO codes.
- `CO_IPUMS_DEPT_W_GEO.tsv`: Mapping that also includes some geographic characteristics, including centroid positions as per the CRS in `CO_DEPT_IPUMS.prj`.
- `CO_DEPT_IPUMS.shp`: Shapefile including the same information as `CO_IPUMS_DEPT_W_GEO.tsv`, along with the polygons bounding each department.
- `CO_MUNI_IPUMS.tsv`: Mapping with FIPS-10, MIGCO2, DEPTCO, MUNICO, and MPIOS codes. The MATCH_QUAL field can be interpreted as confidence in the match (100 is high). 
- `CO_IPUMS_MUNI_W_GEO.tsv`: Mapping that also includes some geographic characteristics, including centroid positions as per the CRS in `CO_MUNI_IPUMS.prj`.
- `CO_MUNI_IPUMS.shp`: Shapefile including the same information as `CO_IPUMS_MUNI_W_GEO.tsv`, along with the polygons bounding each department.

Notes
---
- In IPUMS, `DEPTCO` merges Vaupés and Guainía whereas `MIGCO2` keeps them distinct!
- In IPUMS, according to the [website](https://international.ipums.org/international-action/variables/MUNICO#codes_section), `Villagarzón, PUTUMAYO` and `Puerto Caicedo, PUTUMAYO` are both coded as both `525` and `526` for `MUNICO` and `MIGCO4`. I think it is a typo in the table, therefore I code them as 526 only.
- In IPUMS, for `MUNICO` and `MIGCO4`, there are municipalities encoded as belonging to `CASANARE and VICHADA` and `GUAVIARE and VAUPES`.
- Four municipalities in IPUMS could not be matched: `Sácama, Boyacá`, `San José de Ocune, Vichada`, `Getucha, Caquetá`, and `Santa Rita, Vichada`. `San José de Ocune, Vichada` and `Santa Rita, Vichada` are both contained within `Cumaribo` on the map which is already matched exactly. Furthermore, there are no nearby polygons that are plausible. `Sácama, Boyacá` and `Getucha, Caquetá` also had no nearby plausible polygons. These four municipalities are dropped from the final shapefiles and tsv files. There are also four unmatched `MPIOS` codes: `88000`, `94663`, `91530`, `91430`. Clearly, having four unmatched polygons and four unmatched IPUMS codes is suggestive, but I believe it is just a coincidence.


Acknowledgements
----------------

These files were generated for use within a project funded by AFRL,
managed by JHU/APL. I (John B Nelson) am the sole author, and I am responsible
for any bugs or errors.