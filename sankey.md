# Interactive Sankey Diagram of Global Journeys

This page showcases an interactive Sankey diagram created with R, visualizing the flow of travelers between various global cities. The final destination for all journeys is Besançon.

---

## The Visualization

The diagram below is fully interactive. You can hover over the paths (links) and cities (nodes) to see the number of travelers. You can also drag the nodes to rearrange the diagram for better clarity.

The width of each path is directly proportional to the number of people traveling that specific route.

<!-- This uses HTML to embed your interactive R output directly into the page -->
<iframe src="sankey_diagram.html" width="100%" height="550px" style="border:1px solid #ddd;"></iframe>

> *A direct link to the interactive diagram can be found [here](sankey_diagram.html).*

---

## About the Data and Code

The visualization was generated from a dataset tracking the multi-step journeys of several individuals. The core task was to aggregate the individual journey legs to calculate the total flow between each source and target city.

## R Code

The following R code was used to process the data and generate the Sankey diagram using the `dplyr` and `networkD3` packages.

``` R
# Load required libraries
library(dplyr)
library(networkD3)
```

# Original travel data

```
travel_data <- data.frame(
  Source_Name = c('Peru', 'Sevilla', 'Madrid', 'Barcelona', 'Paris', 'Cairo', 'Lyon', 'Bruges', 'Brussels', 'Luxembourg', 'Shanghai', 'Xiamen', 'Paris', 'Lyon', 'Dijon', 'Tokyo', 'Shanghai', 'Paris', 'Komenda Slovenia', 'Ljubljana', 'Zagreb', 'Basel', 'Mulhouse', 'Yinchuan', 'Shanghai', 'Paris', 'Jacksonville il', 'Chicago', 'Zurich'),
  Target_Name = c('Sevilla', 'Madrid', 'Barcelona', 'Paris', 'Besançon', 'Lyon', 'Besançon', 'Brussels', 'Luxembourg', 'Besançon', 'Xiamen', 'Paris', 'Lyon', 'Dijon', 'Besançon', 'Shanghai', 'Paris', 'Besançon', 'Ljubljana', 'Zagreb', 'Basel', 'Mulhouse', 'Besançon', 'Shanghai', 'Paris', 'Besançon', 'Chicago', 'Zurich', 'Besançon')
)

``` R

### Step 1: Aggregate the data to get flow values

``` R
links <- travel_data %>%
  group_by(Source_Name, Target_Name) %>%
  summarise(value = n(), .groups = 'drop') %>%
  rename(source = Source_Name, target = Target_Name)
```

### Step 2: Prepare nodes and links for the diagram
``` R
nodes <- data.frame(
  name = unique(c(as.character(links$source), as.character(links$target)))
)
```

### Create numeric IDs for the source and target nodes
``` R
links$IDsource <- match(links$source, nodes$name) - 1
links$IDtarget <- match(links$target, nodes$name) - 1
```

### Step 3: Create the Sankey Diagram
``` R
sankey <- sankeyNetwork(Links = links, Nodes = nodes,
                        Source = "IDsource", Target = "IDtarget",
                        Value = "value", NodeID = "name",
                        units = "Travelers",
                        fontSize = 12, nodeWidth = 30)
```

### To display the plot in RStudio
``` R
sankey
```

### To save the plot to an HTML file for embedding
``` R
htmlwidgets::saveWidget(sankey, "sankey_diagram.html")
```