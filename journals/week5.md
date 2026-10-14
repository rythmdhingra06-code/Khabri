## Week 5: Categorisation, Caching, Testing and Mid-Sem Report


Objectives
- Add topic tagging and a cache.
- Test the prototype and prepare the mid-semester report.

Work Done
- Implemented topic tagging (Technology, Sports, Business) and keyword extraction.
- Added search functionality.
- Added a Redis/local cache so repeated requests do not call the external APIs again.
- Handled API rate limits using an exponential back-off strategy and by serving cached articles when the limit is hit.
- Carried out testing:
  - Unit testing of ingestion functions and URL scrapers.
  - Integration testing between the backend APIs and the database.
  - Performance testing of request throughput.
  - User testing on mobile and desktop browsers.
- Recorded results: response time 85 ms, categorisation accuracy 92.4%, throughput 650 req/s.
- Prepared the mid-semester report with all diagrams and the SDLC section.

Challenges
- Rate limits on free APIs caused occasional blocks during testing.

Learnings
- Caching cut redundant fetches by more than 60%.
- Back-off plus a cache keeps the service available even when an external API fails.

Plan for Next Weeks
- Add sentiment analysis (BERT/Transformers).
- Add user authentication for saved topic preferences.
- Add push notifications for breaking news and containerise with Docker.

---
