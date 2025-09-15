# Broskies_hubtasks.day3

📌 Task: Web Scraper for News Headlines

1. What I Built

I developed a Python-based web scraper that automatically collects the latest news headlines from a public news website (e.g., BBC, CNN, Times of India).
The program fetches the web page’s HTML, extracts the headline elements, and saves them into a text file (headlines.txt) for later use.


2. Why I Built It

Automation: Instead of manually visiting a news site and copying headlines, the scraper does it automatically.

Data Collection: Collecting structured data (like headlines) is the first step for larger projects such as news analysis, sentiment analysis, or trend tracking.

Skill Development: This task helps in learning practical web scraping using Python libraries like requests and BeautifulSoup.

Internship Objective: It demonstrates real-world applications of Python for data automation.


3. How I Built It

🔹 Step 1: Import Required Libraries

import requests
from bs4 import BeautifulSoup

requests → fetches the HTML content of the webpage.

BeautifulSoup → parses and extracts useful data (headlines) from HTML.


🔹 Step 2: Fetch the Webpage

URL = "https://www.bbc.com/news"
response = requests.get(URL)

Sent a request to the news site.

Checked if the response was successful (status_code == 200).


🔹 Step 3: Parse the HTML

soup = BeautifulSoup(response.text, "html.parser")

Converted raw HTML into a structured format.

Made it easy to search and extract tags like <h1>, <h2>, <h3>.


🔹 Step 4: Extract Headlines

headlines = []
for headline in soup.find_all(["h1", "h2", "h3"]):
    text = headline.get_text(strip=True)
    if text and text not in headlines:
        headlines.append(text)

Looked for headline tags (h1, h2, h3).

Extracted clean text.

Removed duplicates to keep only unique headlines.


🔹 Step 5: Save to a File

with open("headlines.txt", "w", encoding="utf-8") as f:
    for i, title in enumerate(headlines, start=1):
        f.write(f"{i}. {title}\n")

Wrote all collected headlines into headlines.txt.

Each headline is numbered for clarity.


4. Outcome

✅ A working script that automatically collects news headlines and saves them into a text file.
✅ Demonstrates practical use of Python for automation and data scraping.
✅ Can be extended for:

Sentiment analysis on news.

Daily news reports via automation.

Feeding machine learning models with real-world text data.


📖 Final Summary for Report/Internship:

> I built a Python web scraper to automate the collection of top news headlines from a public website. Using requests to fetch HTML and BeautifulSoup to parse it, the program extracts headlines from <h1>, <h2>, and <h3> tags. The collected titles are stored in a text file (headlines.txt) for further use. This project was important to learn web scraping, data automation, and real-world Python applications in data processing.

📌 Interview Questions & Answers

1. What is a GET request?

A GET request is an HTTP method used to request data from a server.

It is used to retrieve information (not modify it).

Example: Opening a web page in a browser sends a GET request.


2. How do you install external packages in Python?

You install packages using pip (Python package manager).

pip install package_name

Example:

pip install requests beautifulsoup4


3. What is a User-Agent in HTTP?

A User-Agent is a string in the HTTP header that identifies the client making the request (like a browser, mobile app, or script).

Example: "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"

Websites use it to serve appropriate content or block bots.


4. What is soup.find_all() used for?

In BeautifulSoup, soup.find_all() is used to find all HTML elements that match a given tag, class, or attribute.
Example:

soup.find_all("h2")

→ Finds all <h2> tags in the HTML.


5. What are the risks of web scraping?

Legal issues → Some websites prohibit scraping in their Terms of Service.

Blocking → Sites may block your IP if scraping is too aggressive.

Unstable data → Website structure may change, breaking your scraper.

Performance → Too many requests can overload a website.


6. What is the difference between id and class in HTML?

id → Unique identifier for a single element (only one per page).

class → Used to group multiple elements with the same style or behavior.


7. What is an HTML tag?

An HTML tag defines the structure and content of a webpage.

Example: <h1>Heading</h1>

Here, <h1> is the tag and Heading is the content.


8. What does .text return in BeautifulSoup?

.text extracts the visible text content inside an HTML element, removing the tags.
Example:

soup.h1.text

If <h1>Welcome</h1> → returns "Welcome".

9. What is a try-except block?

A try-except block is used for error handling in Python.

It allows code to run even if an error occurs.


Example:

try:
    x = 10 / 0
except ZeroDivisionError:
    print("You can't divide by zero")

10. What are HTTP status codes?

HTTP status codes are 3-digit numbers returned by a server to indicate the response of a request.

200 → OK (success)

301 → Redirect

404 → Not Found

500 → Internal Server Error





