# Web Scraping Flipkart

## Table of Contents

- [Project Title](#project-title)
- [Project Description](#project-description)
- [Project Vision](#project-vision)
- [Key Features](#key-features)

---

## Project Title

**Web Scraping Flipkart**

---

## Project Description

This project is a lightweight Python web scraper built to collect hockey-related product data from [Flipkart](https://www.flipkart.com). It searches for hockey equipment and accessories on Flipkart, then extracts and stores the **product title** and **description** for each listing into a structured CSV file for further analysis or reference.

---

## Project Vision

The goal of this project is to provide a clean, modular, and reusable scraping pipeline that can retrieve product information from Flipkart with minimal setup. By focusing on hockey products, this tool can serve sports enthusiasts, researchers, and e-commerce analysts who want structured data on the availability and variety of hockey gear sold on one of India's largest online marketplaces.

---

## Key Features

- **Targeted Search** — Searches Flipkart specifically for hockey-related products using a configurable query string.
- **Multi-page Scraping** — Iterates across multiple result pages to collect comprehensive data, with configurable page limits.
- **Structured Data Output** — Saves scraped product titles and descriptions into a clean `.csv` file using `pandas`.
- **Modular Design** — The scraper is split into focused functions (`fetch_page`, `parse_products`, `scrape_flipkart`) for easy maintenance and extensibility.
- **Error Handling** — Gracefully handles failed HTTP requests and pages with no results, stopping early to avoid unnecessary calls.

---

## Installation

```bash
pip install requests beautifulsoup4 lxml pandas
```

## Usage

```bash
python flipkart_hockey_scraper.py
```

By default, the scraper queries `"hockey"` across 5 pages and saves results to `flipkart_hockey.csv`.

To customise the query or page count, edit the `scrape_flipkart()` call in `__main__`:

```python
df = scrape_flipkart(query="hockey stick", max_pages=10)
```

## Output

A CSV file (`flipkart_hockey.csv`) with the following columns:

| Column | Description |
|---|---|
| `Product Title` | Full name of the hockey product listing |
| `Description` | Key features or specs listed under the product |

---

## Tech Stack

| Tool | Purpose |
|---|---|
| `requests` | HTTP requests to Flipkart |
| `BeautifulSoup` | HTML parsing |
| `lxml` | Fast HTML parser backend |
| `pandas` | Data structuring and CSV export |

---

## Disclaimer

This project is intended for educational purposes only. Web scraping may be subject to Flipkart's Terms of Service. Use responsibly and ensure compliance with the platform's policies before scraping at scale.
