# Topic analysis of animal-related FixMyStreet reports

Portfolio project for DLBDSEDA02 Project: Data Analysis (IU), Task 1: identifying the most frequent topics in citizen complaints with NLP.

## Data source

- **Source:** FixMyStreet (UK), public Open311 API (https://www.fixmystreet.com/open311), operated by mySociety.
- **Scope:** 73 animal-related categories (dog fouling, dead animals, dog bins, pests, and other animal issues), selected by a keyword search over all 2,601 category names. The list is saved in `animal_categories.csv`.
- **Period:** October 1, 2025 – September 30, 2026 (UK local time), collected on November 21, 2026.
- **Size:** 20,929 reports from 57 categories, sent to 257 council recipients (including combinations of two councils).
- **Fields used:** title, detail, category, date, council, and reporting channel. Reporter names, coordinates, and photos were dropped.

### Why the data are not in this repository

The report texts were written by citizens and can contain personal details such as addresses. They are therefore not published here; the `data/` folder is excluded via `.gitignore`.

### How to re-collect the data

Run `notebooks/01_data_collection.ipynb` from top to bottom. It downloads the reports per category and month (about 900 requests, 15–20 minutes) and saves one JSON file per month in `data/`.

mySociety describes the API as work in progress, and councils change their categories over time. A later download may therefore differ slightly from the 20,929 reports used here.