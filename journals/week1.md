## Week 1 – Problem Identification

**Problem:**  
Users have to visit multiple news websites to understand a single topic. Different platforms present different information, making it difficult to compare news and identify possible bias.

**Solution:**  
We proposed KHABRI, an AI-powered news aggregation and analysis platform that collects news from different sources and provides summarized information with article-level bias analysis.

**Outcome:**  
The project problem statement, objectives, and proposed solution were finalized.

---

## Week 2 – News Data Collection Problem

**Problem:**  
Collecting relevant news articles from multiple sources manually is time-consuming. Different sources also provide information in different formats.

**Solution:**  
We selected Tavily API to retrieve relevant news articles based on user queries. The retrieved information is processed by the backend before being passed to the AI workflow.

**Outcome:**  
A structured approach for retrieving news articles was established.

---

## Week 3 – Frontend and Backend Communication Problem

**Problem:**  
The frontend and backend perform different responsibilities. Without proper communication, user search queries and generated news results cannot be transferred efficiently.

**Solution:**  
We used React for the frontend and Python with FastAPI for the backend. API requests are used to send user queries to the backend and return processed results.

**Outcome:**  
The frontend-backend communication workflow was established.

---

## Week 4 – News Processing and Workflow Management Problem

**Problem:**  
Retrieved news articles require multiple processing stages before they can be presented to users. Managing these operations in a single function can make the system difficult to maintain.

**Solution:**  
We explored LangGraph to divide the processing workflow into separate nodes. Each node performs a specific task, such as searching and summarizing news. Shared state is used to transfer information between nodes.

**Outcome:**  
A modular AI processing workflow was designed.

---

## Week 5 – News Summarization Problem

**Problem:**  
News articles are often lengthy and contain unnecessary information. Users may find it difficult to understand the main points quickly.

**Solution:**  
We integrated Google Gemini API through LangChain to generate concise and meaningful summaries of retrieved news articles.

**Outcome:**  
An AI-based news summarization approach was established.

---

## Week 6 – News Bias Analysis Problem

**Problem:**  
Different news sources may present the same event with different perspectives. Readers may find it difficult to understand the possible bias in individual articles.

**Solution:**  
We designed an AI-based analysis mechanism using Gemini to generate an article-level bias score between 1 and 5, along with reasoning to explain the assigned score.

**Outcome:**  
The platform's article-level bias analysis functionality was developed as part of the AI workflow.

---

## Week 7 – Data Validation and Error Handling Problem

**Problem:**  
External APIs may return empty responses, invalid data, or unexpected errors. AI-generated responses may also fail to follow the expected output structure.

**Solution:**  
We explored Pydantic models for structured output validation and identified exception-handling mechanisms for API failures, timeout errors, invalid inputs, and unexpected responses.

**Outcome:**  
A validation and error-handling strategy was prepared to improve system reliability.

---

## Week 8 – Testing and Reliability Problem

**Problem:**  
A system may work correctly under normal conditions but fail when users provide invalid inputs, external APIs become unavailable, or unexpected responses are received.

**Solution:**  
We prepared test cases covering valid searches, empty queries, duplicate articles, invalid API credentials, Gemini API failures, and JSON validation. Pytest and Postman were selected as testing tools.

**Outcome:**  
A testing plan was prepared to verify individual modules and the overall application workflow.

---

## Conclusion

During the development of KHABRI, different technical and functional challenges were identified and addressed through suitable software engineering approaches. The project involved news retrieval, AI-based summarization, bias analysis, workflow management, data validation, and testing.

The problem-solution approach helped us understand the importance of modular development, API integration, structured data processing, and system reliability. Further improvements will focus on strengthening error handling, executing automated tests, and improving the accuracy and performance of the platform.
---
