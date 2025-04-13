## BikePathAI
=========================

### Problem Area
This project addresses the challenge of finding safe, efficient, and enjoyable bike routes in urban areas. Existing navigation tools (e.g., Google Maps) prioritize speed over safety or scenic value, leading to:
- Dangerous routes: Cyclists often face high-traffic roads without bike lanes.
- Avoidable climbs: Paths with high elevation gains are recommended unnecessarily.
- Inefficient planning: Tourists and commuters spend excessive time researching routes manually.

### Affected Stakeholders
- Cyclists: Commuters, tourists, and recreational riders.
- City planners: Agencies improving bike infrastructure (e.g., NYC DOT).
- Businesses: Cafés/shops along bike routes benefit from increased foot traffic.
- Environmental groups: Promoting biking reduces car emissions.

### Proposed Data Science Solution
We aim to develop a route-scoring model that recommends bike paths based on:
1. Safety: Bike lane availability, traffic volume, accident history.
2. Riding ease: loew elevation gain, minimal hard climbs.
3. Scenery/Amenities: Proximity to parks, landmarks, water bodies, bike shops, and cafes.

### Models to Compare:
1. Graph Algorithms
2. Clustering
3. Regression

### Impact
Potential benefits include:
- Increased biking adoption: Safer routes could reduce car usage by 5–10% in target cities (EPA, 2021).
- Economic growth: Bike-friendly cities see tourism revenue boosts (Adventure Cycling, 2022).
- Health/safety: Reduced cyclist fatalities (NHTSA reports 850/year in the U.S.).

### Dataset Description
Our analysis utilizes a dataset from Kaggle - Describing New York City Roads. The dataset includes:
1. Data on specific NYC streets (divided into road sections by speed limit lines)
2. Bike lane classes on each road section

| Variable | Description | Type |
|----------|-------------|------|
| street | Street name | String |
| st_width | Width of the street in ft | Int |
| bike_lane | NYC bike lane class, if present | Float |
| rw_type | Type of road (highway, bridge, etc) | Str |
| traf_dir | One-way or Two-way street | Str |
| bike_traf_dir | Direction of bike traffic | Str |
| start_contour | Vertical position at the start of the road | Int |
| end_contour | Vertical position at the end of the road| Int |

This dataset aggregates data from the New York City Department of Transportation (NYCDOT) on New York City Speed Limits and The New York City Centerline and allows us to have a comprhensive look at NYC roads for cyclists.

### Methodology
1. Data Preprocessing: Clean NYCDOT data.
2. Feature Engineering: Calculate safety/riding scores.
3. Model Implementation using graph algorithms with custom edge weights.
4. Visualization of routes and best paths
5. Evaluation: Compare to Strava/Komoot routes

### Limitations
- Data Availability: My current datasets lack amenities (cafés, parks) and subjective scenery metrics, forcing reliance on proximity-based approximations.
- Subjectivity: "Pleasantness" is user-dependent (e.g., some cyclists prefer quiet streets, others prioritize directness). Current models don’t personalize recommendations.
- Geographic Scope: NYC-specific data (e.g., NYCDOT bike lane classifications) may not generalize to other cities with different infrastructure standards.

### Future Work
- Enhance Data with APIs/OSM: Use Google Places API or OpenStreetMap to tag amenities (coffee shops, bike repair) and natural features (parks, waterfronts).
- Personalization: Add user preference inputs (e.g., "Avoid hills" or "Prioritize bike lanes") via a weighted scoring system. Implement collaborative filtering to recommend routes based on similar users’ preferences.
- Generalize to Other Cities: Build a pipeline for OpenStreetMap data extraction (globally available) to replicate the analysis in cities like SF or Berlin.
- Real-Time Integration: Incorporate live traffic data (e.g., NYC 311 feeds) or weather APIs to adjust recommendations dynamically.
- Advanced Modeling: Use computer vision on Street View images to infer road quality (potholes, lane width) and scenicness.
- Policy Impact Analysis: Simulate how proposed bike lanes (e.g., NYC’s 2025 Bike Plan) would improve route options using network analysis.

------------------------------------------------------------------------------

# Capstone Template

This is a template repository for setting up your capstone project: it includes a simple folder structure and placeholder files for the most important assets you will be creating.

## Usage

1. Start a new GitHub repo using this template.
2. Update your `LICENSE` file with date and owner.
3. Update your `README.md` file to reflect the project - see a sample structure below and please refer to Synapse on what needs to be included here. 
4. Set up and activate your conda environment:
    - Create a new `conda` environment for your capstone project.
    - Activate the environment and export:
        ```bash
        conda env export > conda.yml
        ```
    - Make sure re-export every time after you update the environment.
    - You can reset your conda environment by running:
        ```bash
        conda env create -f conda.yml
        conda activate <your-env-name>
        ```
5. Add your own notebooks in `./notebooks/` and remove placeholders.
6. Add your own data in `./data/` and remove placeholder. Note: `.gitignore` will ignore the data folder when you push to github, save a copy of your raw and processed data, pickled models in a Google Drive folder and add the link in the `data_links.md` file.
7. Add your project documents, figures, reports, presentation pdf's in the `./docs` and remove placeholders.
8. Add your references (tutorials, papers, books etc.) in `./references`. 
9. Add your own scripts in `./src/` and remove unnecessary folders.

Feel free to rename the folder and customize the project structure to best fit your work - this template is just the starting point.

------------------------------------------------------------------------------

### Demo

... Show your work:
...     Data visualizations
...     Interactive demo (e.g., `streamlit` app)
...     Short video of users trying out the solution


### Methodology

... High-level diagrams of entire process:
...     various data processing steps
...     various modelling directions
...     various prototyping directions


### Organization

#### Repository 

* `data` 
    - contains link to copy of the dataset (stored in a publicly accessible cloud storage)
    - saved copy of aggregated / processed data as long as those are not too large (> 10 MB)

* `model`
    - `joblib` dump of final model(s)

* `notebooks`
    - contains all final notebooks involved in the project

* `docs`
    - contains final report, presentations which summarize the project

* `references`
    - contains papers / tutorials used in the project

* `src`
    - Contains the project source code (refactored from the notebooks)

* `.gitignore`
    - Part of Git, includes files and folders to be ignored by Git version control

* `conda.yml`
    - Conda environment specification

* `README.md`
    - Project landing page (this page)

* `LICENSE`
    - Project license

#### Dataset

... Google Drive links to datasets and pickled models

### Credits & References

... Include any personal learning
