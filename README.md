# Laptop Data Scraper & Analysis (Flipkart)

This project scrapes laptop product data from Flipkart for laptops under ₹50,000 and performs exploratory data analysis using Python.  
It extracts product details such as name, ratings, reviews, price, specifications, and image URLs, then stores them in a CSV file for further analysis.

> **Note:** Flipkart often blocks direct scraping. If you face HTTP 500 or blocking issues, see the “Troubleshooting” section below.
⚠️ Troubleshooting (Important)

Flipkart blocks requests without a User-Agent header.
If you see:

HTTP Error 500 / 403


Replace:

httpObject = urlopen(url)


With:

from urllib.request import Request, urlopen
req = Request(url, headers={'User-Agent': 'Mozilla/5.0'})
httpObject = urlopen(req)

---

## 📌 Features

- Scrapes multiple pages of laptop listings from Flipkart
- Extracts:
  - Product Name
  - Star Ratings
  - Number of Ratings & Reviews
  - Current Price & MRP
  - Processor, RAM, and Storage details
  - Product Image URL
- Stores data into `laptops_info.csv`
- Loads data into a pandas DataFrame for:
  - Sorting
  - Filtering by features or price
  - Finding best-rated or lowest-price laptops
- Data visualization & correlation insights

---

## 🛠️ Technologies Used

| Library            | Purpose                             |
|-------------------|-------------------------------------|
| `BeautifulSoup`    | Web scraping                        |
| `urllib.request`   | Fetching webpage HTML               |
| `pandas`           | Data loading & analysis             |
| `numpy`            | Data operations                     |
| `matplotlib`       | Visualization                        |
| `seaborn`          | Visualization                        |
| `scikit-learn`     | (Optional) ML operations            |

---

## 📂 File Output

The script generates the following file:

| File Name           | Description |
|--------------------|-------------|
| `laptops_info.csv`  | Contains the scraped laptop dataset |

---

## ▶️ How to Run

1. Clone or Download the project.
2. Install required libraries:
   ```bash
   pip install beautifulsoup4 pandas numpy matplotlib seaborn scikit-learn
