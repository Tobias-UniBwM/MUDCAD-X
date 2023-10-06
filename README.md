# MUDCAD-X

MUDCAD-X stands for _e**X**tended **M**ultispectral **D**ataset for **Ca**mouflage **D**etection_ and contains multiple camouflaged targets that were captured with a multispectral camera system in nadir perspective. The [dataset](dataset) features 853 captures, each consisting of a single image file for each band and a label mask, in which each camouflaged target has been annotated with a unique color. The color coding (RGB) is defined in the [labels file](dataset/labels_rgb.yaml). The ground sample distance is 10$`\frac{cm}{px}`$ as defined [here](dataset/gsd.yaml).

Detailed information about MUDCAD-X and our research can be found in our publication [*Measuring and Predicting Sensor Performance for Camouflage Detection in Multispectral Imagery*](https://doi.org/10.3390/s23198025).

### Folder Structure

- dataset/\<season\>/\<date\>/\<location\>/\<area\>/\<flight_number\>/\<region\>/\<capture_number\>
    - \<band_a\>.png
    - \<band_b\>.png
    - ...
    - label.png

#### Directory Descriptions

- season: the season the data was captured
- date: the actual date the data was captured
- location: a location code for the local area (internal scheme; constant across all captures)
- area: the area the data was captured, either a or b
- flight_number: the number of the flight on that date (min: 1; max: 7)
- region: region code inside the area; *h* stands for horizontal and *v* for vertical line; if suffixed by *r* it's the same line but the captures are rotated by 45°
- capture_number: the number of the capture in the region

### Bands

Each capture consists of 7 different bands: visual (VIS), blue, green, red, edge-infrared (EIR), near-infrared (NIR), long-wave infrared (LWIR). 

| Band  | Center Wavelength | Bandwidth  |
| :---: | :---: | :---: |
|  VIS | - | - |
| blue | 475nm | 32nm |
| green | 560nm | 27nm |
| red | 668nm | 14nm |
| EIR | 717nm | 12nm |
| NIR | 842nm | 57nm |
| LWIR | 10.5μm  | 6μm |

### Targets

The following camouflaged objects were captured in the dataset: 

1. artificial turf
2. artificial hedge 
3. green tarp
4. green 2D camouflage net
5. green 3D camouflage net
6. anthracite fleece
7. gray tarp
8. gray 3D camouflage net
9. persons in two different green military uniforms
10. persons in two different yellow military uniforms

All targets were placed in visually similar appearing environments.

## Cite

If you use MUDCAD-X in your research please cite the following publication:

```
@Article{s23198025,
    author = {Hupel, Tobias and Stütz, Peter},
    title = {Measuring and Predicting Sensor Performance for Camouflage Detection in Multispectral Imagery},
    journal = {Sensors},
    volume = {23},
    year = {2023},
    number = {19},
    article-number = {8025},
    url = {https://www.mdpi.com/1424-8220/23/19/8025},
    issn = {1424-8220},
    abstract = {To improve the management of multispectral sensor systems on small reconnaissance drones, this paper proposes an approach to predict the performance of a sensor band with respect to its ability to expose camouflaged targets under a given environmental context. As a reference for sensor performance, a new metric is introduced that quantifies the visibility of camouflaged targets in a particular sensor band: the Target Visibility Index (TVI). For the sensor performance prediction, several machine learning models are trained to learn the relationship between the TVI for a specific sensor band and an environmental context state extracted from the visual band by multiple image descriptors. Using a predicted measure of performance, the sensor bands are ranked according to their significance. For the training and evaluation of the performance prediction approach, a dataset featuring 853 multispectral captures and numerous camouflaged targets in different environments was created and has been made publicly available for download. The results show that the proposed approach can successfully determine the most informative sensor bands in most cases. Therefore, this performance prediction approach has great potential to improve camouflage detection performance in real-world reconnaissance scenarios by increasing the utility of each sensor band and reducing the associated workload of complex multispectral sensor systems.},
    doi = {10.3390/s23198025}
}
```

