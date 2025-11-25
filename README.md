# GLOCAL NL Government Department Web Scraper | Python & Selenium

This project is a Python automation script that uses Selenium to scrape department information from the Government of Newfoundland and Labrador website.

It automatically navigates through the list of departments and collects:

- Department name  
- Minister name  
- “About”/overview text  
- Contact email  
- Department URL  

All results are saved into a structured CSV file for further analysis or integration into other systems.

---

## Project Overview

The script:

1. Opens the main departments page: `https://www.gov.nl.ca/departments/`
2. Extracts each department’s name and URL from the department list
3. Visits each department page individually
4. Scrapes:
   - The first relevant “About” paragraph found on the page  
   - Minister information (e.g., “Honourable …”, “Minister …”, “Premier …”)  
   - Contact email for the department  
5. Writes the consolidated dataset to `result.csv`

---

## Tech Stack

- **Language:** Python  
- **Automation & Scraping:** Selenium  
- **Parsing & Regex:** `re`  
- **Data Handling:** pandas  
- **Browser:** Chrome + ChromeDriver

---

## Repo Structure

```
NL Government Department Web Scraper
├── scraper.py        # Main Selenium automation script
├── result.csv        # Output file (generated after running)
├── requirements.txt  # Python dependencies (selenium, pandas, etc.)
└── README.md
