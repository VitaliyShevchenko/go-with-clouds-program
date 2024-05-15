## Project description

### News Aggregator

#### Overview

The News Aggregator CLI Application allows users to collect, filter, and display news from various sources through a
command-line interface.
This tool is designed to provide an efficient and customizable way to stay updated with the latest news based on
user-defined criteria.

##### Key Functionalities

1. News Collection: Collect News from Multiple Sources: Users can collect news from various sources, including RSS feeds
   and web APIs. The system supports the addition of new sources dynamically.
2. Standardized News Items: The application standardizes the news items collected from different sources, ensuring
   consistency. Each news item includes a title, description, link, and publication date.
3. Filtering Mechanism:

- Keyword Filtering: Users can filter news items based on specific keywords. The keyword matching is case-insensitive
  and checks both the title and description of news items. The system uses a stemming algorithm to handle different
  forms and endings of words.
- Date Range Filtering: Users can filter news items based on a specified date range. The system handles various date
  formats and ensures accurate filtering within the defined range.

4. Command-Line Interface (CLI)

- Start News Aggregation: Users can start the news aggregation process through a simple command. The system collects
  news from the defined sources and applies any specified filters.
- Apply Filters: Users can apply keyword and date range filters via command-line arguments to refine the collected news
  items according to their preferences.
- Display Filtered News: The application displays the filtered news items in a readable format, showing the title,
  publication date, and a brief description.

5. User Input Handling

- Specify News Sources: Users can define the news sources (e.g., RSS feed URLs, API endpoints) via command-line
  arguments.
- Provide Filtering Criteria: Users can provide keywords and date ranges for filtering news items through command-line
  arguments.
- Input Validation: The application validates user inputs and provides clear error messages for invalid entries,
  ensuring a smooth user experience.

6. Logging and Error Handling

- Logging: The application logs key events and errors during its execution, helping users monitor the performance and
  troubleshoot issues.
- Error Handling: The system gracefully handles network errors, parsing errors, and other potential issues, providing
  informative error messages to users.

##### Detailed Description of CLI Commands

1. **collect**
   Description: Start the news aggregation process.
   Usage: news-aggregator collect --source <source_url> [--interval <update_interval>]
   Arguments:
   --sources: The URL of the news source (e.g., RSS feed URL, API endpoint).
   --keyword: (Optional) Time interval for collecting news from the source.
   (User friendly time: 1 day, 4 hours). Default: 1 day.
2. **get**
   Description: Get aggregated news.
   Usage: news-aggregator collect --source <source_url> [--interval <update_interval>]
   Arguments:
   --sources: The URLs of the news source: (
   e.g. http://feeds.bbci.co.uk/news/rss.xml, http://rss.cnn.com/rss/edition.rss)
   --keyword: (Optional) Keyword to search by. (e.g. tech)
   --dates: (Optional) Dates interval of article publication dates, e.g.: 2024-05-15 - 2024-05-17) Default: The current
   date.

Output Format:
The application displays the filtered news items in the following format:

```text
Title: <news_title>
Date: <publication_date>
Description: <news_description>
Link: <news_link>
```

```text
Example Output:
Title: Go 1.18 Released
Date: Mon, 14 Mar 2024 10:00:00 +0000
Description: The Go team is proud to release Go 1.18, which includes significant updates and improvements.
Link: https://golang.org/doc/go1.18
```

#### How It Gets the News

The first iteration of the product collects the news from local rss.xml files.

The next iteration supports the following:
- Collecting News from RSS Feeds: It fetches the feed from the provided URL and extracts the news items.
- Collecting News from APIs: The application makes HTTP GET requests to the specified API endpoints and parses the JSON
response to extract news items.
- Dynamic Source Addition: Users can add new news sources by providing the source URL as a command-line argument. The
application handles RSS and API sources dynamically.
