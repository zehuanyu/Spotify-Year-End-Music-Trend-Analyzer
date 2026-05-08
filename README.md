# Spotify Year-End Music Trend Analyzer

A Python data analysis project that compares year-end music trends from 2020 and 2021 using Spotify playlist data, SQLite database storage, SQL queries, and Matplotlib visualizations.

This project was built to explore how popular artists changed across two consecutive years and to practice a complete data workflow: API collection, data caching, database design, SQL analysis, and visualization.

---

## Overview

Music trends change quickly. Some artists remain popular across multiple years, while others appear only in a specific year because of a hit song, album release, or short-term trend.

This project analyzes year-end music data to answer:

- Which artists appeared in both 2020 and 2021?
- Which artists were unique to each year?
- How can Spotify playlist data be stored and compared using a relational database?
- How can Python visualizations make artist trend patterns easier to understand?

---

## Project Workflow

```text
Spotify API
    ↓
Raw playlist JSON
    ↓
Python data extraction
    ↓
SQLite database
    ↓
SQL artist comparison
    ↓
Matplotlib visualizations
```

The project also includes a secondary Billboard workflow for scraping year-end chart data, storing it in SQLite, calculating artist-level song counts, and generating bar chart visualizations.

---

## Features

- Collects playlist track data from the Spotify Web API
- Saves raw API responses as local JSON files
- Extracts artist names and song titles
- Stores cleaned data in a SQLite database
- Uses SQL joins to compare artists across years
- Identifies artists appearing in both 2020 and 2021
- Identifies artists unique to each year
- Generates pie chart and bar chart visualizations
- Includes an additional Billboard chart analysis workflow

---

## Repository Structure

```text
Spotify-Year-End-Music-Trend-Analyzer/
├── new.py
├── finalproject.py
├── measurement.py
├── Visualization.py
├── 2020.json
├── 2021.json
├── artists_in_both_years.txt
├── DataBase
├── CompletedPreProjectPlan.pdf
├── report.docx
└── repo.txt
```

---

## Main Components

### `new.py`

Main Spotify analysis pipeline.

It handles:

- Spotify API authentication
- Playlist data retrieval
- JSON file export
- SQLite database creation
- Artist and track insertion
- Artist overlap analysis
- Unique artist comparison
- Pie chart and bar chart visualization

### `finalproject.py`

Secondary Billboard data collection script.

It scrapes Billboard year-end Hot 100 song data for 2020 and 2021, stores song rankings and artist information in SQLite, and tracks scraping progress using a `State` table.

### `measurement.py`

Calculates artist-level song count statistics from the Billboard database using SQL joins.

### `Visualization.py`

Creates horizontal bar charts showing the number of songs per artist for each year in the Billboard dataset.

---

## Database Design

The Spotify workflow uses three main SQLite tables:

```text
Artists
Tracks_2020
Tracks_2021
```

The `Artists` table stores unique artist names, while `Tracks_2020` and `Tracks_2021` store song records for each year. This structure makes it easier to compare artists across years using SQL joins.

Example analysis query logic:

```sql
SELECT DISTINCT Artists.Artist_name
FROM Artists
JOIN Tracks_2020 ON Artists.id = Tracks_2020.id
JOIN Tracks_2021 ON Artists.id = Tracks_2021.id;
```

This query finds artists who appeared in both years.

---

## Visualizations

The project generates two main Spotify visualizations:

### Artist Overlap Pie Chart

Shows the proportion of:

- Artists appearing in both years
- Artists only appearing in 2020
- Artists only appearing in 2021

### Unique Artists Bar Chart

Compares the number of unique artists between 2020 and 2021.

These charts make the year-to-year artist trend easier to interpret visually.

---

## Results

The project outputs:

```text
2020.json
2021.json
artists_in_both_years.txt
DataBase
```

The analysis identifies artists who appeared in both years and compares the number of artists unique to each year. The visualizations provide a quick summary of artist overlap and year-specific popularity patterns.

---

## Tech Stack

- Python
- Spotify Web API
- SQLite
- SQL
- Matplotlib
- Requests
- BeautifulSoup
- python-dotenv
- JSON

---

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/zehuanyu/Spotify-Year-End-Music-Trend-Analyzer.git
cd Spotify-Year-End-Music-Trend-Analyzer
```

### 2. Install dependencies

```bash
pip install requests beautifulsoup4 python-dotenv matplotlib
```

### 3. Create a `.env` file

Create a `.env` file in the project root directory:

```text
CLIENT_ID=your_spotify_client_id
CLIENT_SECRET=your_spotify_client_secret
```

### 4. Run the Spotify analysis

```bash
python new.py
```

### 5. Run the Billboard workflow

```bash
python finalproject.py
python measurement.py
python Visualization.py
```

---

## Skills Demonstrated

- API data collection
- JSON data processing
- SQLite database design
- SQL joins and filtering
- Web scraping
- Data cleaning and organization
- Data visualization with Matplotlib
- End-to-end data analysis workflow

---

## Future Improvements

- Add more years of Spotify and Billboard data
- Organize scripts, data, and outputs into separate folders
- Add generated charts directly to this README
- Rename `DataBase` to a clearer database filename
- Add a `requirements.txt` file
- Compare artist frequency, not only artist presence
- Add genre, popularity score, release date, and audio feature analysis
- Build an interactive dashboard with Streamlit or Plotly

---

## Security Note

This project uses Spotify API credentials through a `.env` file. The `.env` file should not be committed to GitHub.

Recommended `.gitignore` entries:

```text
.env
__pycache__/
*.db
*.sqlite
DataBase
```

---

## Author

Zehuan Yu
