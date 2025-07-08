# 🚗 Scraping Instructor Information from DrivingKing.hk

## 📄 Overview

This project uses **Selenium** to scrape instructor data from the DrivingKing.hk coaching directory. The scraper collects:

- Summary data from coach cards
- Detailed profile information from modal/profile pages

All data is saved into a structured dictionary and exported for analysis.

---

## 🔍 Scraping Steps

### ✅ Extract Basic Info from Coach Cards
- Instructor name, school, region, fee indicators, etc.

### ✅ Extract Detailed Info from Profile Page
- Insurance details, faculty fees, lesson area coverage, and more.

### ✅ Scrape All Pages
- Iterate through all paginated listings.

---

## 📊 Basic Analysis

After scraping, data is restored from CSV into a DataFrame for quick querying and statistical analysis.

---

## 📌 Parameter: `area`

**Description:**  
Represents the geographical region associated with each instructor. Common combinations of three Hong Kong regions:

- 香港 (Hong Kong Island)
- 九龍 (Kowloon)
- 新界 (New Territories)

**Data Summary:**

| Area                | Count |
|---------------------|-------|
| 新界 九龍           | 126   |
| 香港                | 25    |
| 九龍                | 14    |
| 香港 九龍 新界      | 18    |
| 香港 九龍           | 4     |
| 新界                | 4     |

**Analysis:**

- **九龍 新界** is the most common region combo (126 entries).
- **香港** (25) and **九龍** (14) have moderate representation.
- **新界** alone is rarely listed (4 entries), suggesting it is often grouped with 九龍.
- Listings that cover all three regions are less frequent.

---

## 📌 Parameter: `faculty fee`

**Description:**  
Special rates or discounts offered to faculty members.

**Top 3 Most Common Faculty Fees (HKD):**

| Faculty Fee | Count |
|-------------|-------|
| 450         | 62    |
| 400         | 28    |
| 500         | 24    |

**Analysis:**

- Most common fees cluster around **450**, **400**, and **500 HKD**.
- Some entries are missing (`No entry`: 6) or marked `"none"` (18).
- Higher fees (e.g., 600, 700 HKD) appear occasionally.

---

## 📌 Parameter: `insurance certificate`

**Description:**  
Indicates the type of insurance coverage and accident compensation responsibility provided by instructors.

**Top 3 Most Common Insurance Types:**

| Insurance / Status                               | Count |
|--------------------------------------------------|-------|
| Third Party Insurance with half compensation     | 106   |
| Comprehensive Insurance with half compensation   | 54    |
| No accident compensation method provided         | 21    |

**Analysis:**

- Most instructors offer **third-party insurance** with **half compensation** in case of accidents.
- A smaller portion offers **comprehensive insurance** with similar terms.
- **Missing or unclear insurance info** is common (21+ entries).
- Few instructors cover **full compensation** — these are rare but valuable for learners.

---

## 📁 Files

- `drivingking_scraper.ipynb` – Main notebook for scraping
- `instructors_data.csv` – Scraped dataset
- `README.md` – This file

---

## 🛠 Requirements

- Python 3.8+
- Selenium
- pandas
- BeautifulSoup4
- ChromeDriver (matching your Chrome version)

---

## 💡 Notes

- Always respect a site’s `robots.txt` and terms of service.
- This scraping project is for educational/research purposes.

---

## 📬 Contact

For questions, suggestions, or contributions, feel free to open an issue or pull request.
