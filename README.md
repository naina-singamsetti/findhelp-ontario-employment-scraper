# findhelp-ontario-employment-scraper
Web scraper to extract employment services (e.g., Better Jobs Ontario) from feat.findhelp.ca for cities across Ontario using BeautifulSoup and pandas.

# 🧭 Ontario Employment Services Scraper – FindHelp.ca

This project is a Python-based web scraper that extracts structured information about employment services (such as Better Jobs Ontario programs) from [feat.findhelp.ca](https://feat.findhelp.ca/), a public directory of social services across Ontario.

It is tailored to extract services for selected cities (e.g., Acton, Ajax, Toronto) and store the results in a clean Excel dataset suitable for further analysis.

---

## 📊 Key Features

- Extracts **organization name**, **service name**, **contact numbers**, **addresses**, **website**, and more.
- Focused on the **"Looking for Work"** category, especially **Employment Services including Better Jobs Ontario**.
- Stores structured data into **Pandas DataFrames** and exports to **Excel** format.
- Easily extensible to scrape multiple cities by modifying URL and coordinate parameters.

---

## 📂 Files in the Repository

| File Name              | Description                                              |
|------------------------|----------------------------------------------------------|
| `findhelp2.ipynb`      | Jupyter notebook containing the full scraping logic      |
| `df_acton_combined.xlsx` | Scraped data for Acton city – structured and clean       |
| `README.md`            | Project documentation                                    |
| `requirements.txt`     | Python dependencies (requests, bs4, pandas)              |

---

## 🧪 Sample Extracted Data

| Organization             | Service Name                     | City    | Phone Numbers             |
|--------------------------|----------------------------------|---------|----------------------------|
| VPI Working Solutions    | Integrated Employment Services   | Acton   | 1-888-336-9500, 905-873-9816 |
| HOPE Start               | Integrated Employment Services   | Acton   | 519-823-9333               |
| COSTI Immigrant Services | Resume Workshops                 | Ajax    | 905-123-4567               |

---

## ⚙️ Technologies Used

- `requests` – Sending HTTP requests
- `BeautifulSoup` – Parsing and extracting data from HTML
- `pandas` – Cleaning and storing data
- `Jupyter Notebook` – Interactive development

---

## ❗ Challenges Faced

### ❌ Sitemap.xml Not Available
As a first step toward ethical scraping, we attempted to locate a `sitemap.xml` file at:
https://feat.findhelp.ca/sitemap.xml
However, this URL does not exist or is not publicly accessible. This meant we could not easily extract all URLs or programmatically detect endpoints from the sitemap, which would have simplified the scraping workflow significantly.

### ❌ Selenium-Based Approach (Initially Attempted)
We initially used **Selenium** to interact with the site due to the assumption that most content was rendered dynamically via JavaScript. However, we encountered several issues:
- **Unstable rendering** of results in headless mode
- Frequent **timeouts and missing elements**
- **API and AJAX calls** were difficult to trace or replicate reliably
- Dependency on **browser drivers** like ChromeDriver, which introduced compatibility issues

### ✅ Switched to BeautifulSoup
Upon inspecting network requests and page source, we discovered that the key information was available in the **static HTML**. Switching to a `requests` + `BeautifulSoup` approach offered several benefits:
- Lightweight and faster scraping
- Easier to deploy and maintain (no browser automation required)
- More reliable data extraction

## 📁 Project Structure
web-scraper-ontario/
├── scrape_jobs.py # Main scraping script
├── README.md # This documentation
└── requirements.txt # Python dependencies

👩‍💻 Author
Naina Singamsetti

Data Scientist | Toronto, Canada
Feel free to fork, improve, or use for research purposes.

