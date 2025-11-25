# GLOCAL NL Government Department Web Scraper

This project is a Python automation script that uses Selenium to scrape department information from the Government of Newfoundland and Labrador website.

It automatically navigates through the list of departments and collects:

- Department name  
- Minister name  
- “About”/overview text  
- Contact email  
- Department URL  

All results are saved into a structured CSV file for further analysis or integration into other systems.

### Install ChromeDriver
Ensure ChromeDriver matches your local Chrome version:
https://googlechromelabs.github.io/chrome-for-testing/

---

## Project Overview

Manually visiting each department page and copying information is time-consuming and error-prone.  
This project automates that process end to end:

1. Open the main **Departments** page.
2. Extract department names and URLs from the department list.
3. Visit each department page in turn.
4. Scrape:
   - The first relevant “About” paragraph  
   - Minister information (e.g., text starting with *Honourable*, containing *Minister* or *Premier*)  
   - A contact email address, if available  
5. Save everything into a single CSV file: `scrape_result.csv`.

If the website structure changes (e.g., HTML tags / layout), the script will print a warning so you know to review the selectors.

---

## Key Features

- **Browser automation with Selenium** – controls Chrome to navigate and scrape multiple pages.
- **Element handling** – uses `WebDriverWait` and CSS selectors to work with dynamic content.
- **Data extraction logic**:
  - Identifies ministers by patterns in `<strong>` tags.
  - Uses regex to locate email addresses.
  - Captures the first meaningful “About” paragraph on the page.
- **Error handling**:
  - Handles missing ministers or emails.
  - Catches timeouts when pages don’t load expected content.
- **Structured output** – exports a clean CSV with one row per department.

---

## Repo Structure

```
NL Government Department Web Scraper
├── NL_scraper.py        # Main Selenium automation script
├── scrap_result.csv        # Output file (generated after running)
├── requirements.txt  # Python dependencies (selenium, pandas, etc.)
└── README.md
