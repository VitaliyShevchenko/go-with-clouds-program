## Project description

### News Aggregator

#### Overview

The news-aggregator application allows users to collect, filter, and display news from various sources. This tool is
designed to provide an efficient and customizable way to stay updated with the latest news based on
user-defined criteria.

First, we're going to implement it in a simplified form as a CLI application. Arguments for execution will be given
through a command-line interface. Then we will make it a web app and, eventually, transform it into a containerized app
running in Kubernetes in the cloud.

##### Key Functionalities of news-aggregator CLI app

1. **News Collection**
    * Users can collect news from a predefined set of sources, some of them are RSS feeds, the others are html news
      pages. Take a look at [the attached files](./data/news-sources) and work with them in your app.
2. **Standardized News Items**
    * The application standardizes the news items collected from different sources, ensuring
      consistency. Each news item includes a title, description, link, and publication date.
3. **Filtering Mechanism**
    * Keyword Filtering: Users can filter news items based on specific keywords. The keyword matching is
      case-insensitive and checks both the title and description of news items. The system uses a stemming algorithm to
      handle different forms and endings of words.
    * Date Range Filtering: Users can filter news items based on a specified date range.
    * Source Filtering: Users can specify from which sources to get the news from (out of the predefined list: e.g. BBC,
      ABC).
4. **Command-Line Interface**
    * Users interact with the application via a command-line interface (CLI).
      The CLI provides a set of arguments to specify filtering criteria and provides help messages for them.
5. **User Input Handling**
    * The application validates user inputs and provides clear error messages for invalid entries,
      ensuring a smooth user experience.
6. **Logging and Error Handling**
    * Logging: The application logs key events and errors during its execution. It helps users to monitor app execution
      and troubleshoot issues.
    * Error Handling: The system gracefully handles parsing errors, and other potential issues,
      providing informative error messages to users.

##### Detailed Description of CLI interface

* **--help**.

Show all available arguments and their descriptions.

Usage: `news-aggregator --help`

* **--sources**

Select the desired news sources to get the news from. Make sure to validate and tell the user about
[the supported news sources](#how-it-gets-the-news).

Usage: `news-aggregator --sources=bbc,usatoday`

* **--keywords**

Specify the keywords to filter the news by.

Usage: `news-aggregator --keywords=Ukraine,China`

* **--date-start** (**--date-end**)

Specify the date range to filter the news by according to some predefined well-known format of your choice.

Usage: `news-aggregator --date-start=2024-18-05 --date-end=2024-19-05`

##### Output Format

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

Add line breaks between news items for better readability.

#### How It Gets the News

The first iteration of the app collects the news from [local rss and html files](./data/news-sources).
The RSS files have .xml extension. As RSS is standardized format of data, you'll have no problems with it.
You might spend more time on investigating the html file and mapping the data you need to the news item fields.

The news sources where the files were downloaded from are:

* https://www.bbc.co.uk
* http://abcnews.go.com
* https://www.usatoday.com
* https://www.washingtontimes.com

Use the libs of your choice for parsing RSS and HTML.

#### Extensibility Instructions

When implementing the app consider the extensibility aspect.
We need to be able to easily read from different news sources and of different types (RSS, html, json).
We start with local RSS feed and HTML files but later will transform into data retrieved via HTTP calls.
When structuring the code in packages, take into account that we will distribute the application in two forms:
as a CLI app and as a web app (HTTP/HTTPS server).

#### Future Improvements

The next iteration of the application will be adjusted to accept the rss feed URLs and make http requests to get the
data. This way the rss news sources will transform from a predefined list of sources to a dynamically supplied list.
Also, we will add ability to read html news pages directly from some websites. Probably, we will try to fetch news from
some social nets API.