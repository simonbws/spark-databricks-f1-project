# Presentation Layer

The files are responsible for transforming data from the `f1_raw` layer into an analytical form in the `f1_presentation` database.

This is where data from different sources (races, results, drivers, constructors) is combined to create ready-to-use datasets and metrics.

## Main Components

- **race_results** — joins data from races, drivers, teams, and circuits, creating a single results dataset.  
- **driver_standings** — aggregates driver points and positions based on each season.  
- **constructor_standings** — calculates constructor rankings based on the combined performance of team drivers.  
- **calculated_race_results** — calculates scoring and performance metrics for further analysis (e.g., average points, number of race starts).  
- **create_presentation_database** — creates the final `f1_presentation` database, which serves as the foundation for reporting and visualization.

## Purpose

To create a **consistent and unified data model**, ready for reporting and analysis in the notebooks from the analysis folder.
