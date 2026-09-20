# Hockey Team Statistics Scraper 🏒📊

A robust, multi-page Python web scraper designed to collect historical hockey team statistics. The script automatically traverses through paginated web forms using custom attribute targeting, extracts structural data, and outputs a clean dataset into a CSV file.

## ⚠️ Educational Disclaimer
This project was built strictly for **educational and learning purposes** to practice web scraping, pagination logic, and data extraction techniques. 
- It uses a sandbox website (`scrapethissite.com`) specifically designed for developers to legally practice scraping.
- The repository does not intend to infringe on any data rights or terms of service, and it should not be used as an aggressive, real-world data-harvesting tool.

## 🚀 Features
- **Multi-Page Navigation:** Dynamically locates and follows paginated "Next" links via BeautifulSoup's element attribute dictionary (`attrs`) matching.
- **Anti-Scraping Bypasses:** Integrates user-agent rotation via `fake-useragent` and custom request headers to mimic real human traffic patterns safely.
- **Data Exportation:** Collects and formats detailed performance indicators directly into a structured, comma-separated format (`.csv`).

## 📊 Extracted Metrics
The dataset captures the following metrics across multiple seasons:
* Team Name
* Year / Season
* Total Wins
* Total Losses
* Winning Percentage (Win %)
* Goals For (GF)
* Goals Against (GA)

## 🛠️ Tech Stack & Requirements
This project runs entirely on Python 3 and relies on the following standard libraries and packages:
* **BeautifulSoup4** (for parsing target HTML elements)
* **Requests** (for executing HTTP data fetches)
* **Fake-Useragent** (for header optimization and identity masking)
* **CSV** & **JSON** (for data writing and payload handling)

### Installation
Ensure you have the required dependencies installed before running the script:
```bash
pip install beautifulsoup4 requests fake-useragent
```

## 💻 How It Works
The script initializes an automated crawling loop on the target destination:
1. Sets up localized environment headers to avoid bot detection.
2. Finds the target historical statistics table layout.
3. Iterates over rows containing the individual team statistics.
4. Utilizes `soup.find('a', attrs={'aria-label':'Next'})` to securely track down pagination targets with hyphenated names, altering the loop's execution URL on every pass until no further pages exist.

## 📄 Output Data Sample
Running the scraper creates a `hockey_team.csv` payload formatted as follows:

```csv
Team Name,Year,Wins,Losses,win %,Goals for,Goals Against
Boston Bruins,1990,44,24,0.55,299,264
Buffalo Sabres,1990,31,30,0.388,292,278
Calgary Flames,1990,46,26,0.575,344,263
```

## ⚖️ License
This project is open-source and intended for educational web scraping exploration.

