CO_Data
===

Files useful for merging Colombia GIS records with [IPUMS microdata](https://international.ipums.org/international/), at least for the 2005 census. 

Data Sources
---
The original Colombia department shapefile was obtained from [https://sites.google.com/site/seriescol/shapes](https://sites.google.com/site/seriescol/shapes). I found this shapefile to be superior to the one found at [http://www.diva-gis.org/gdata](http://www.diva-gis.org/gdata) which lacked Bogotá.

Files
---

- `CO_IPUMS.tsv`: Mapping with FIPS-10, MIGCO2, and DEPTCO codes.
- `CO_IPUMS_W_GEO.tsv`: Mapping that also includes some geographic characteristics, including centroid positions as per the CRS in `CO_IPUMS.prj`.
- `CO_IPUMS.shp`: Shapefile including the same information as `CO_IPUMS_W_GEO.tsv`, along with the polygons bounding each department.

Notes
---
- In IPUMS, `DEPTCO` merges Vaupés and Guainía whereas `MIGCO2` keeps them distinct!


Acknowledgements
----------------

These files were generated for use within a project funded by AFRL,
managed by JHU/APL. I (John B Nelson) am the sole author, and I am responsible
for any bugs or errors.