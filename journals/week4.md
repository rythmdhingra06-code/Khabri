## Week 4: UML Design and Start of Implementation


Objectives
- Complete the UML design.
- Begin building the ingestion engine.
Work Done
- Prepared the class diagram with the classes User, NewsArticle, Category, NewsAggregator, NewsProcessor, Cache and Database, and defined their relationships.
- Prepared the sequence diagram for a news feed request: User, Web UI, Backend API, News Aggregator.
- Prepared the activity diagram: fetch, clean and normalise, duplicate check, store, tag, cache, display.
- Started the ingestion module:
  - Fetching data from news endpoints.
  - Normalising dates and removing HTML tags.
  - Duplicate detection by hashing article URLs (MD5/SHA256).
- Tested the endpoints in Postman.

Challenges
- Different APIs return dates and fields in different formats.
- Raw article text contained HTML tags.

Learnings
- Normalising data early makes every later step simpler.
- Hashing the URL gives a fast, reliable duplicate check.

Plan for Next Week
- Add topic categorisation and caching.
- Begin testing.

---
