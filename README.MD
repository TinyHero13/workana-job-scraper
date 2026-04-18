# Workana Job Scraper

## About

A Python web scraper that collects freelance job listings from [Workana](https://www.workana.com/) using Selenium. It extracts job titles, prices, descriptions, required skills, publication dates, and bid counts, then exports the cleaned data to a CSV file.

## Collected Data

The scraper navigates through up to 50 pages of Portuguese-language job listings and outputs a `workana.csv` file with the following columns:

| Column | Description |
|---|---|
| `Title` | Job listing title |
| `Price` | Budget or price range |
| `Description` | Full job description |
| `Skills` | Required skills (comma-separated) |
| `Published` | Publication date |
| `Bids` | Number of proposals received |
| `Category` | Job category (extracted from description) |
| `SubCategory` | Job subcategory (extracted from description) |

## Requirements

- Python 3.8+
- Google Chrome installed
- ChromeDriver matching your Chrome version

## Installation

```bash
pip install -r requirements.txt
```

> Make sure your `requirements.txt` includes: `selenium`, `pandas`

## Usage

1. Ensure Google Chrome and ChromeDriver are installed and accessible in your PATH.
2. Run the script:

```bash
python scraper.py
```

3. The scraper will open a Chrome window, paginate through Workana job listings, and save the results to `workana.csv` in the current directory.

> The script handles cookie consent and login prompts automatically on the first page.

## Notes

- The scraper covers **up to 50 pages** of listings by default. To change this, update the range in the loop:

```python
for page_num in range(1, 50):  # change 50 to your desired page limit
```

- A `time.sleep()` delay is used between interactions to avoid being blocked. Adjust values if needed depending on your connection speed.
- Listings without skills will show `N/A` in the `Skills` column.

## Project Structure

```
.
├── scraper.py         # Main scraping script
├── requirements.txt   # Python dependencies
└── workana.csv        # Scraped output (created on run)
```

## Contributing

Suggestions and improvements are always welcome! Feel free to open a pull request or reach out to discuss ideas.

## Connect with me

- [Portfolio](https://yasmim-portifolio.vercel.app)
- [LinkedIn](https://www.linkedin.com/in/yasmim-abrahao-311491227/)
