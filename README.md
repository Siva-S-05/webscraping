#Web Scraping – eBay Product Data Extractor
A Python-based web scraping application developed to collect structured product information from eBay search result pages. The tool leverages BeautifulSoup for HTML parsing and is intended for data analysis, research, and educational use cases.

#Features
Multi-page Data Extraction
Scrapes product information across multiple pages of eBay search results.

#Detailed Product Attributes
Collects product title, listed price, item condition, shipping details, and direct product URLs.

#CSV Data Export
Exports scraped data into CSV format for downstream analytics and reporting.

#Price Analysis Module
Provides basic statistical insights such as average, median, minimum, and maximum prices.

#Error Resilience
Implements exception handling to manage request failures and missing fields gracefully.

#Polite Scraping Practices
Introduces delays between requests to reduce load on the target server.

#Modular and Reusable Codebase
Designed using object-oriented principles for maintainability and extensibility.

#Requirements
beautifulsoup4 == 4.12.2
requests == 2.31.0
pandas == 2.1.0

#Installation
Clone the repository:
git clone https://github.com/Siva-S-05/webscraping.git
cd web-scraping

#Install dependencies:
pip install -r requirements.txt

#Usage
Basic Example
from ebay_scraper import EbayScraper
scraper = EbayScraper()

# Scrape eBay for laptops (2 pages)
scraper.scrape_ebay(search_query='laptop', pages=2)

# Save results to CSV
df = scraper.save_to_csv('ebay_laptops.csv')

# Display price statistics
scraper.get_price_statistics()

Advanced Usage
products = ['iphone 13', 'macbook pro', 'gaming laptop']

for product in products:
    scraper = EbayScraper()
    scraper.scrape_ebay(search_query=product, pages=3)
    scraper.save_to_csv(f'ebay_{product.replace(" ", "_")}.csv')

#Output Schema
The generated CSV file contains the following columns:
Column	Description
title	Product name
price	Listed price
condition	Item condition (New, Used, etc.)
shipping	Shipping information
link	Direct product URL

#Sample Output
Price Statistics
Average Price: $456.78
Median Price: $399.99
Minimum Price: $89.99
Maximum Price: $1,299.00
Total Items Analyzed: 58

Configuration Options
scraper = EbayScraper()

#Use Cases
Market and pricing trend analysis
Product price tracking over time
Dataset creation for data analytics or machine learning
Competitive product comparison
Academic and educational research

#Important Considerations
Ensure compliance with eBay’s terms of service and robots.txt
Use responsible rate limiting to avoid excessive server requests
Designed strictly for educational and personal research purposes
Does not support authenticated or restricted content
Users are responsible for legal and ethical compliance

#License

This project is distributed under the MIT License. Refer to the LICENSE file for more information.
