# How to Implement a Simple Web Scraper Using `requests` and `BeautifulSoup`?

Web scraping allows you to extract information from websites. In Python, we use the `requests` library to fetch web pages and `BeautifulSoup` to parse the HTML.

---

## **1. Install Required Libraries**
You need to install the following libraries before running the script:

```bash
pip install requests beautifulsoup4
```

---

## **2. Basic Web Scraping Example**

### **Step 1: Import Necessary Libraries**
```python
import requests
from bs4 import BeautifulSoup
```

### **Step 2: Send an HTTP Request**
```python
url = "https://example.com"
response = requests.get(url)

if response.status_code == 200:
    print("Page fetched successfully!")
else:
    print("Failed to retrieve the page")
```

### **Step 3: Parse HTML Content**
```python
soup = BeautifulSoup(response.text, "html.parser")
print(soup.prettify())  # Print formatted HTML content
```

### **Step 4: Extract Specific Data (e.g., Titles, Links)**
```python
# Extracting all <h1> tags
titles = soup.find_all("h1")
for title in titles:
    print(title.text)

# Extracting all links
links = soup.find_all("a")
for link in links:
    print(link.get("href"))
```

---

## **3. Handling Dynamic Content**
Some websites use JavaScript to load data dynamically. In such cases, you may need `Selenium`:

```bash
pip install selenium
```

Use Selenium to interact with JavaScript-heavy websites.

---

## **4. Respect Website Rules**
Before scraping, always check the site's `robots.txt` file (`https://example.com/robots.txt`) to ensure compliance.

---

## **Conclusion**
- `requests` fetches webpage content.
- `BeautifulSoup` parses and extracts data from HTML.
- Be mindful of legal and ethical scraping practices.

🚀 **Start web scraping and extract useful data!**
