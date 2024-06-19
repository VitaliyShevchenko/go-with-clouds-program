### HTTP server + REST API)

Build a simple HTTP server for the news-aggregator project.

1. Create a GoLang server to handle HTTP requests, using **net/http** library.
2. Use **JSON** to accept requests and reply to them.
3. GoLang server should have the next handler **GET** `/news` (user API). This handler should allow a user to get news based on the filters (use news-aggregator lib which you implemented on task #1).
4. **UPDATE** Instead of having static news sources, the news-aggregator should be able to fetch the same sources from Internet. (hint: do it one by one: rss, html, json)
5. GoLang server should be able to dynamically register news sources, the next handler should be implemented **GET**, **PUT**, **POST**, **DELETE** `/sources`. (admin API)

Additional details:
1. News sources (which will be fetched) can be stored in memory or files (recommend this option).
2. New GoLang server should be defined as a separate go module and news-aggregator go module should be used in the GoLang server module. (both modules should be private)

**Note**: A good level of documentation and unit test coverage is required.

#### Something to read

* [TCP/IP](https://www.objc.io/issues/10-syncing-data/ip-tcp-http/) — must read
* [TCP Technical overview](https://medium.com/@jimmyclem/a-technical-overview-of-tcp-pt-1-62e777c0d01)
* [Data serialization](https://towardsdatascience.com/what-why-and-how-of-de-serialization-in-python-2d4c3b622f6b)
* [Data serialization formats](https://study-ccna.com/data-serialization-formats-json-yaml-xml/)
* [URL & URI](https://danielmiessler.com/study/difference-between-uri-url/)
* [GoLang & JSON](https://gobyexample.com/json)
