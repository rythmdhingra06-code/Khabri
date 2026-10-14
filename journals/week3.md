## Week 3: System Architecture and Use Case Modelling


Objectives
- Design the overall architecture.
- Create the use case model.

Work Done
- Designed a three-layer architecture:
  1. Data Ingestion Layer (RSS feeds and REST APIs)
  2. Core Processing Pipeline (cleaning, de-duplication, ML)
  3. Presentation Layer (web service delivering news cards)
- Drew the high-level architecture diagram.
- Identified the actor (User) and the use cases: Search News, Filter by Topic, View News Feed, Subscribe to Topics, Read News Article.
- Identified the internal system use cases: Aggregate News, Remove Duplicates, Categorize News and Cache Results.
- Wrote the use case descriptions table.

Challenges
- Deciding which functions belong to the user and which to the system.

Learnings
- Layered design keeps each component independent and easier to test.
- A use case diagram separates what the user does from what the system does internally.

Plan for Next Week
- Prepare the UML class, sequence and activity diagrams.
- Start implementing the ingestion module.

---
