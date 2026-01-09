# webscraping
A Python-based web scraping tool that extracts product data from eBay search results. Built with BeautifulSoup and designed for data analysis and research purposes.
🚀 Features

Multi-page Scraping: Extract data from multiple pages of search results
Comprehensive Data Collection: Captures title, price, condition, shipping info, and product links
Data Export: Save results to CSV format for further analysis
Price Analytics: Built-in statistical analysis of scraped prices
Error Handling: Robust error management for reliable scraping
Respectful Scraping: Includes delays between requests to avoid server overload
Clean Code: Object-oriented design with reusable components

📋 Requirements
beautifulsoup4==4.12.2
requests==2.31.0
pandas==2.1.0
🛠️ Installation

Clone the repository:

bashgit clone https://github.com/Siva-S-05/webscraping.git
cd web-scrapeing

Install required packages:

bashpip install -r requirements.txt
💻 Usage
Basic Example
pythonfrom ebay_scraper import EbayScraper

# Create scraper instance
scraper = EbayScraper()

# Scrape eBay for laptops (2 pages)
scraper.scrape_ebay(search_query='laptop', pages=2)

# Save to CSV
df = scraper.save_to_csv('ebay_laptops.csv')

# View price statistics
scraper.get_price_statistics()
Advanced Usage
python# Scrape multiple products
products = ['iphone 13', 'macbook pro', 'gaming laptop']

for product in products:
    scraper = EbayScraper()
    scraper.scrape_ebay(search_query=product, pages=3)
    scraper.save_to_csv(f'ebay_{product.replace(" ", "_")}.csv')
📊 Output Format
The scraper generates CSV files with the following columns:
ColumnDescriptiontitleProduct title/namepriceListed priceconditionProduct condition (New, Used, etc.)shippingShipping informationlinkDirect URL to product listing
📈 Example Output
Price Statistics:
Average Price: $456.78
Median Price: $399.99
Min Price: $89.99
Max Price: $1,299.00
Total items with prices: 58
⚙️ Configuration
You can customize the scraper behavior:
pythonscraper = EbayScraper()

# Modify headers (optional)
scraper.headers['User-Agent'] = 'Your Custom User Agent'

# Scrape with custom parameters
scraper.scrape_ebay(
    search_query='gaming laptop',
    pages=5
)
🎯 Use Cases

Market Research: Analyze pricing trends for products
Price Monitoring: Track product prices over time
Data Analysis: Create datasets for machine learning projects
Competitive Analysis: Compare product offerings and prices
Academic Research: Gather data for studies and analysis

⚠️ Important Notes

Ethical Scraping: Always respect website terms of service and robots.txt
Rate Limiting: Built-in delays prevent server overload
Personal Use: This tool is designed for personal research and educational purposes
No Authentication: Cannot access content requiring login
Legal Compliance: Ensure your use complies with local laws and eBay's policies

🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the repository
Create your feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
