
## Summary of the group work and workflow 

## 1. Fieldwork & Documentation

- **Photographic Collection**: Each student used a smartphone to photograph intriguing limestone wall patterns found throughout Besançon. We gathered over 100 images, ensuring each photo was geotagged for precise location mapping.

## 2. Annotation & Categorization

- **Individual Meaning-Making**: Every participant described what each image resembled to them—resulting in a collaborative “citywide Rorschach test.”
- **Custom Categories**: We then developed codes for recurring motifs (animals, faces, objects, abstract/symbolic forms). To do this, we tested different categorisation methods.

## 3. Analysis and Data Curation

- **Data Structuring**: All annotation data, image links, and geotags were consolidated in a shared Google Sheet and then exported to a CSV file [`Project1_Data_grouped.csv`](https://github.com/Mapping-Aficionados/GroupPresentation/blob/main/Project1_Data_grouped.csv). Multiple description columns allow for cross-comparison and deeper analysis.
- **EXIF data extraction**: We extracted EXIF data from the geotagged photos using the `EXIFR` package and appended latitudes and longitudes to the dataset.

** NEED MORE DESCRIPTION OF PROCESS HERE **

## 4. Technical Processing of Images  
Image files underwent batch compression for storage efficiency. Care was taken to preserve all visually significant pattern details. Images were compressed to facilitate their uploading and we extraccted thumbnails for each image. We used the [ILoveImages](https://www.iloveimg.com/) website. It worked amazingly and it's free.

We also tried to use the Apple **SIPS** utility, but could not get it to work correctly.

## 5. The dataset

Our dataset is stored in the [`ESUDH HDME final geotagged dataset`](https://github.com/Mapping-Aficionados/GroupPresentation/blob/main/data/ESUHDMEfinal_geotagged_dataset.csv)) file.

Each row includes the photo filename, links to different sized versions of the photo, and students' descriptions of what the images reminded them of in addition to the more general categories imputed from the descriptions.

## 6. Map creation 

- We created the map in `QGIS` using the `QGIS2WEB` plugin with two layers, one that focuses on the degree of consensus and another that classifies the data according to the most common category of annotations. In the latter we only use high and medium consensus tags. 
- We designed the pop up boxes to contain the information we wanted to show.
- We matched the color palette for the various categories created in Plotly as described [here](https://mapping-aficionados.github.io/GroupPresentation/Methodology-Clustering.html) 

## Conclusions 

Making the map not only taught us a workflow for creating a categorized map from image data collected with smartphones, but it allowed us to identify several recurring motif clusters. These patterns may hold cultural or architectural significance worth further investigation. We developed improved documentation techniques. New frameworks emerged for interpreting ambiguous urban visual phenomena effectively.  

This project created Besançon's first (and so far unique) systematic wall patterns record.
