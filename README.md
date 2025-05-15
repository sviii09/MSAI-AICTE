News Sentiment Analyzer with Real-Time Alerts
 
A Python-based tool that scrapes news headlines from Google News, performs sentiment analysis, visualizes sentiment trends, and sends SMS alerts for critical negative news. Built for real-time monitoring of news sentiment, this project is ideal for researchers, businesses, or individuals tracking public perception.
Table of Contents

Project Overview
Features
Tech Stack
Installation
Usage
Sample Output
Deployment
Future Enhancements
References
License
Contact

Project Overview
This project automates the process of tracking news sentiment by scraping headlines, analyzing their emotional tone, and alerting users to critical negative events. It combines web scraping, natural language processing (NLP), data visualization, and real-time notifications, making it a versatile tool for sentiment analysis.
Problem Statement: News overload makes it challenging to identify emotionally charged events manually. This system provides automated, real-time sentiment tracking and alerts.
Goal: Enable users to monitor news sentiment and receive timely notifications for critical events, improving decision-making and awareness.
Features

Real-Time News Scraping: Fetches headlines from Google News based on user-defined keywords.
Sentiment Analysis: Uses TextBlob to score headline sentiment (-1 to +1) and classify as Positive, Negative, or Neutral.
Interactive Visualizations: Generates Plotly bar charts to display sentiment distribution.
SMS Alerts: Sends notifications via Twilio for highly negative news (sentiment ≤ -0.5).
Web Interface: Flask-based dashboard for viewing results and interacting with the system.
Scalable Design: Suitable for deployment on free hosting platforms like PythonAnywhere.

Tech Stack

Web Scraping: BeautifulSoup, Requests
Sentiment Analysis: TextBlob
Data Visualization: Plotly, Pandas
Alerts: Twilio API
Web Framework: Flask
Environment: Python 3.8+, Google Colab or local Jupyter Notebook
Deployment: PythonAnywhere (free tier)

Installation

Clone the Repository:
git clone https://github.com/your-username/news-sentiment-analyzer.git
cd news-sentiment-analyzer


Install Dependencies:
pip install -r requirements.txt

Or manually install:
pip install requests beautifulsoup4 textblob plotly twilio flask pandas


Set Up Twilio Credentials:

Sign up for a Twilio account.
Obtain account_sid, auth_token, and a Twilio phone number.
Add credentials to config.py or directly in the code (not recommended for production).


Optional: Configure environment variables for sensitive data:
export TWILIO_ACCOUNT_SID='your_sid'
export TWILIO_AUTH_TOKEN='your_token'
export TWILIO_PHONE_NUMBER='+1234567890'



Usage

Run Locally:
python app.py

Access the web interface at http://127.0.0.1:5000.

Run in Google Colab:

Copy the code from main.ipynb into a Colab notebook.
Install dependencies using !pip install ....
Execute cells sequentially to scrape news, analyze sentiment, and generate visualizations.


Customize Keyword:

Modify the keyword parameter in scrape_news(keyword="AI") to track specific topics (e.g., "climate change", "technology").


Enable SMS Alerts:

Uncomment the send_sms_alert() call in the code.
Ensure Twilio credentials are configured.


Example Command:
from scraper import scrape_news, analyze_sentiment
news_df = scrape_news(keyword="Artificial Intelligence", num_articles=10)
news_df = analyze_sentiment(news_df)
print(news_df)



Sample Output



Title
Link
Sentiment
Label



AI Breakthrough in Cancer Research
https://news.google.com/...
0.82
Positive


Tech Layoffs Due to AI Automation
https://news.google.com/...
-0.65
Negative


Sentiment Distribution: 
SMS Alert Example:
⚠️ Negative Alert: Tech Layoffs Due to AI Automation

Deployment

PythonAnywhere:

Sign up at PythonAnywhere.
Upload project files via the Files tab.
Configure a web app with Flask (follow PythonAnywhere's Flask setup guide).
Set up a scheduled task for periodic scraping using APScheduler or cron jobs.


Local Server:

Run app.py with a public-facing server (e.g., using ngrok for testing).
Ensure Twilio webhook is configured for SMS functionality.


Scaling:

Migrate to FastAPI for better performance in production.
Use a database (e.g., SQLite) for storing historical data.



Future Enhancements

Social Media Integration: Add Twitter/X sentiment analysis using Tweepy.
Stock Correlation: Correlate news sentiment with stock price movements.
PDF Reports: Generate automated reports using FPDF.
Chrome Extension: Build a browser extension for live page analysis.
Multi-Source Scraping: Include additional news sources (e.g., BBC, CNN).

References

Pang, B., & Lee, L. (2008). Opinion Mining and Sentiment Analysis. Foundations and Trends in Information Retrieval.
TextBlob Documentation
Twilio API Documentation
Plotly Python Documentation
Dataset: Google News (scraped in real-time)



Issues: Feel free to open an issue for bugs or feature requests!


⭐ If you find this project useful, please give it a star on GitHub!Contributions are welcome via pull requests.
