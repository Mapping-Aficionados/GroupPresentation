# The Journey to Besançon: A Spatial Narrative of ESU workshop participants trajectories

Welcome to the `mapping_aficionados` project for the **"Humanities Data and Mapping Environments"** workshop at ESU 2025!

<iframe style='width: 50%; ' src='workshop/ClassPhoto.jpg'></iframe>

This project visualizes the collective journey of our workshop participants from around the globe to our meeting point in Besançon, France. Using Kepler.gl, we transform a simple dataset of departure points and travel stops into a rich spatial narrative, telling the story of how our academic community comes together.

## The Project

The core of this project is to take tabular geographic data and use it to tell a visual story. We are mapping not just static locations, but the dynamic paths of travel that connect our individual starting points to our shared destination.


## The Dataset

Our dataset is stored in the `/data/students_trajectories.csv` file. It captures the geographic origins and travel itineraries of each participant.

All locations are represented by latitude and longitude coordinates, making them ready for mapping.

## Telling a Story with Layers in Kepler.gl

A map is more than just points; it's a canvas for storytelling. In our Kepler.gl visualization, we use different layers to build a narrative of our journey:

#### 1. Points Layer: Our Academic Origins
*   **What it shows:** This layer plots the location of each participant's **Home Institution**.
*   **The Story:** These points represent our global academic network. They visualize the diverse and international origins of the knowledge and perspectives converging at this workshop.

#### 2. Arc Layer: The Journeys to Besançon
*   **What it shows:** This is the heart of our story. We use an **Arc Layer** to draw lines from each participant's `home_lat_lon` (start point) to their `final_lat_lon` (end point).
*   **The Story:** These arcs are the visual representation of travel. They trace the paths taken across continents and countries. When viewed together, they create a powerful image of a community converging on a single point.

#### 3. Points Layer: The Stops Along the Way
*   **What it shows:** This layer highlights the intermediate `Stop_1`, `Stop_2`, etc., as individual points.
*   **The Story:** These points enrich our narrative, showing that a journey is often more than just a direct line from A to B. 

## How to Explore the Map

We invite you to interact with the map to discover these stories for yourself.

<iframe style='width: 800px; height: 600px;' src='MappersTravels.html'></iframe>

Once you have the map open, you can:

1.  **Toggle Layers**: Use the layer controls on the left to turn different layers (Institutions, Journeys, Stops) on and off to focus on different aspects of the data.
2.  **Filter the Data**: Use the filter tool to focus on a specific participant's journey. You can create a filter based on the `Name` column.
3.  **Hover for Details**: Move your cursor over points and arcs to see tooltips displaying more information, such as the participant's name or the city they stopped in.
4.  **Change Your Perspective**: Zoom in, pan around, and tilt the map to explore the geographic relationships from different angles.

# Sankey visualization

Here's another visualization of the data using R, with a [sankey diagram](sankey.md). 

# A third visualization

Here's a third visualization of the [data with avatars](GroupPresentation/ESU_HDME_Students_Journey.html). 

# What we've been doing so far in the course? 

We have prepared a [brief summary](workshop/week1_summary.md) of it!
