# Methology for Directory Map

This map was created by:

1. Taking a [photograph](Photographs\IMG_5773.JPG) of a Besancon directory from ca. 1907.
2. Doing OCR on the photograph
3. Processing the OCR to create columlar data, with the householder's name, occupation, and address.
4. A geolocation service processed the addresses and produced lat/lon data for each address.
5. The resulting CSV file was visualized using [kepler.gl](https://kepler.gl/), which creates an HTML file.

You may wonder why there is a point in the center of the map with a whole **lot** of texts written on it. This is the center point for the city and used as the default value by the GeoCoder when it couldn't provide a more precise location. This happened with any record that lacked clear street number / street name data.