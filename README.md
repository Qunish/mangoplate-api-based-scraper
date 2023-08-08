# MangoPlate API Scraper

This Python script scrapes restaurant data from the MangoPlate website using their API and stores it in a MongoDB database. It consists of two main parts: scraping restaurant URLs and details, and then inserting the data into MongoDB.

## Prerequisites

- Python 3.x
- Selenium (for scraping restaurant details)
- ChromeDriver (for Selenium)
- pymongo (for interacting with MongoDB)
- requests (for making HTTP requests)

## Usage

1. Install the required packages:
   ```bash
   pip install selenium pymongo requests
   ```

2. Download and install the [ChromeDriver](https://sites.google.com/chromium.org/driver/) appropriate for your Chrome browser version.

3. Update the `headers` and `data` variables in the code snippet that sends requests to the MangoPlate API. Adjust the `keyword` parameter to match the location or type of restaurants you want to scrape.

4. Replace `"localhost"` and `27017` with your MongoDB server's hostname and port in the MongoDB client initialization:
   ```python
   client = pymongo.MongoClient("localhost", 27017)
   ```

5. Run the script using:
   ```bash
   python mangoplate_api_scraper.py
   ```

## Code Explanation

1. The script first sends requests to the MangoPlate API to fetch restaurant data based on the specified keyword (e.g., "Hongdae").

2. The scraped restaurant data is inserted into the MongoDB collection `hongdae_lv`.

3. The script then iterates through the scraped restaurant data and uses Selenium to fetch additional details from the restaurant's URL.

4. The fetched details are stored in the `data_dict` dictionary.

5. The script continues to scrape details for each restaurant URL and stores the scraped data in the `hongdae_pv` collection in MongoDB.

6. The script stops when 200 restaurants' data have been scraped and stored.

## Note

- Make sure to set up the MongoDB connection properly before running the script.
- This script is based on the MangoPlate website structure while writing the script. Any changes to the website structure may require modifications to the script.# mangoplate-api-based-scraper
