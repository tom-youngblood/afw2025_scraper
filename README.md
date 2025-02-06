# AFW 2025 Scraper

## Overview
The **AFW 2025 Scraper** is a Python-based web scraping project that extracts and processes event and lead data from the Affiliate Summit West 2025 event platform. The project consists of multiple scripts that scrape event attendees, event metadata, and lead information, then store the extracted data in structured CSV files.

## Repository Structure
```
AFW2025_Scraper/
│── afw_event_scraper/         # Event data scraping scripts and notebooks
│   ├── afw_events_scraper.ipynb
│   ├── event_data/            # Scraped event attendee data (CSV files)
│
│── afw_lead_scraper/          # Lead data scraping scripts and notebooks
│   ├── afw_2025_scraper.ipynb
│   ├── lead_data.csv          # Processed leads
│   ├── all_profiles_final.csv # Merged profile data
│   ├── leads_links.csv        # Extracted LinkedIn profile links
│   ├── html.txt               # Raw HTML data (if applicable)
│   ├── merge.ipynb            # Notebook to merge scraped data
│
│── final_results/             # Final processed datasets
│   ├── event_data/            # Cleaned and structured event CSV files
│   ├── lead_data.csv          # Final merged lead dataset
```

## Features
- **Scrapes event attendees:** Collects names, job titles, and companies of attendees for each event.
- **Extracts event metadata:** Retrieves event names, times, and locations.
- **Gathers lead data:** Collects LinkedIn profiles and other relevant details.
- **Stores data in CSV format:** Organized data is saved in structured files for further analysis.
- **Handles pagination & scrolling:** Uses Selenium to navigate popups and dynamically loaded content.

## Installation & Setup
### Prerequisites
- Python 3.x
- Required libraries:
  ```sh
  pip install selenium beautifulsoup4 pandas
  ```
- A valid **Chrome WebDriver** for Selenium.

### Running the Scraper
1. **Clone the repository:**
   ```sh
   git clone https://github.com/tom-youngblood/afw2025_scraper.git
   cd afw2025_scraper
   ```
2. **Run the Event Scraper:**
   ```sh
   python afw_event_scraper/afw_events_scraper.ipynb
   ```
3. **Run the Lead Scraper:**
   ```sh
   python afw_lead_scraper/afw_2025_scraper.ipynb
   ```

## Data Output
The scraper outputs two main datasets:

### Event Data
Stored in `final_results/event_data/` with separate CSV files for each event.

Each event file contains:
```
| Event Name  | Event Time | Event Location | User Name | Job Title | Company |
|------------|------------|---------------|-----------|----------|---------|
```

### Lead Data
Processed and stored in `final_results/lead_data.csv`.

Each lead file contains:
```
| Name | Job Title | Company | Full Link | Profile URL | About Me | Attendee Type | Lead Generation Business | Vertical | Company Size | Solutions Needed | Objective For Attending | Social Media | Contact Details | Affiliate Type |
|------|----------|---------|-----------|-------------|----------|---------------|-------------------------|---------|-------------|-----------------|----------------------|-------------|----------------|---------------|
```
1. **Event Data:** Stored in `final_results/event_data/` with separate CSV files for each event.
2. **Lead Data:** Processed and stored in `final_results/lead_data.csv`.

Each event file contains:
```
| Event Name  | Event Time | Event Location | User Name | Job Title | Company |
|------------|------------|---------------|-----------|----------|---------|
```

## Notes
- The scraper requires **manual login authentication** for some sources.
- The project uses **Selenium for browser automation** and **BeautifulSoup for HTML parsing**.
- Ensure WebDriver is properly configured before execution.
