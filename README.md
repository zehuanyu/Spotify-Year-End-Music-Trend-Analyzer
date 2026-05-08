# Spotify Year-End Music Trend Analyzer

This project analyzes Spotify year-end music trends by comparing popular tracks and artists from 2020 and 2021. It uses the Spotify Web API to collect playlist track data, stores the cleaned information in a SQLite database, and visualizes artist overlap and unique artist trends across the two years.

The goal of this project is to practice API data collection, database design, SQL queries, data processing, and Python-based visualization in one complete data analysis workflow.

## Project Overview

Music popularity changes quickly from year to year. This project focuses on comparing Spotify playlist data from 2020 and 2021 to answer questions such as:

- Which artists appeared in both years?
- Which artists were unique to 2020 or 2021?
- How many unique artists appeared in each year?
- How can music trend data be stored, queried, and visualized using Python?

The project retrieves track and artist information from Spotify playlists, saves the data into a SQLite database, performs SQL-based analysis, and generates visual charts to summarize the results.

## Features

- Retrieves playlist track data from the Spotify Web API
- Extracts artist names and track names from playlist JSON data
- Stores artists and tracks in a SQLite database
- Uses relational database tables for artists and yearly track records
- Identifies artists appearing in both 2020 and 2021
- Identifies artists unique to each year
- Writes shared-artist results to a text file
- Creates visualizations using Matplotlib

## Repository Contents

```text
SI206FinalProject/
├── new.py
├── finalproject.py
├── Visualization.py
├── measurement.py
├── 2020.json
├── 2021.json
├── artists_in_both_years.txt
├── DataBase
├── CompletedPreProjectPlan.pdf
├── report.docx
└── repo.txt
