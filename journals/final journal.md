# Week 1 — Project Ideation, Problem Identification and Scope

## Problem / Challenge

During the initial stage of the project, our team had to identify a real-world problem that could be solved through a Software Engineering project.

We noticed that users have to visit multiple news websites to understand a single topic. Different platforms present different information and perspectives, which makes it difficult to compare news and identify possible bias.

After selecting this problem, the next challenge was defining the scope clearly and explaining what would make our project different from a generic news website or news aggregator.

## Solution

We finalized **KHABRI**, an AI-powered news aggregation and analysis platform, as our project.

The initial scope focused on:

> Searching news based on a user query

> Collecting articles from multiple sources

> Summarizing the collected articles using AI

> Article-level bias analysis with reasoning

After finalizing the concept, we prepared the problem statement, objectives and proposed solution.

---

# Week 2 — News Data Collection

## Problem / Challenge

After finalizing the project idea, the next challenge was deciding how KHABRI would collect news articles from different sources.

Collecting articles manually from multiple websites is time-consuming, and every website presents its information in a different format.

## Problems Faced

One of the main difficulties was that the backend needed every article in the same format, but different sources provide different fields and layouts.

For example, one source may provide a headline and published date, while another provides only a page with text, advertisements and links.

Therefore, we decided that every retrieved article should be converted into a common structure:

Title → Source → URL → Content

This made it possible to process articles from all sources in the same way.

## Solution

We selected the **Tavily API** to retrieve relevant news articles based on the user's query.

The data collection flow was defined as:

> User query is sent to Tavily

> Relevant articles are retrieved from multiple sources

> Required fields are extracted from each article

> Articles are processed by the backend

> Processed articles are passed to the AI workflow

---

# Week 3 — Frontend and Backend Communication

## Problem / Challenge

The next challenge was connecting the user interface with the backend.

The frontend and backend perform different responsibilities. The frontend accepts the user's search query and displays results, while the backend retrieves and processes the news. Without proper communication, the query and the generated results cannot be transferred between them.

## Problems Faced

The main difficulty was deciding the format in which data would be exchanged, because both applications run separately and must understand the same structure.

For example, the frontend sends only a search query, but the backend has to return several results, each with a summary and a bias score.

The request and response were therefore defined as:

Request → { query }

Response → { articles, summary, bias score, reasoning }

This kept the communication between both sides consistent.

## Solution

We used **React** for the frontend and **Python with FastAPI** for the backend.

The communication workflow included:

> A search input on the React frontend

> An API endpoint in the FastAPI backend

> Sending the user query through an API request

> Returning processed results in JSON format

> Displaying the results on the frontend

---

# Week 4 — News Processing and Workflow Management

## Problem / Challenge

After establishing communication, the next challenge was organizing how the retrieved articles would be processed.

Articles go through multiple stages, such as searching, summarizing and bias analysis, before they can be shown to the user. Writing all of these stages inside a single function would make the system difficult to maintain.

## Problems Faced

One of the main difficulties was deciding how to divide the processing into separate stages and how each stage would receive the output of the previous one.

For example, the summarization stage cannot start until the search stage has collected the articles, and the bias analysis stage needs both the articles and their content.

The workflow was therefore defined as:

Search → Summarize → Bias Analysis → Final Output

A shared state was used so that each stage could read and update the same information.

## Solution

We explored **LangGraph** to divide the workflow into separate nodes.

The workflow design included:

> A separate node for each task

> A defined order of execution between nodes

> A shared state storing the query, articles and results

> Transfer of information between nodes through the shared state

---

# Week 5 — News Summarization

## Problem / Challenge

The next challenge was presenting the retrieved news in a form that users can understand quickly.

News articles are often lengthy and contain information that is not essential to the main event, so users may find it difficult to identify the key points.

## Problems Faced

The main difficulty was making sure the summary kept the important facts while removing unnecessary details.

For example, an article may contain background information, repeated details and quotes, while the main point is only a few lines long.

Therefore, the summarization step was designed to focus on:

Main Event → Key Facts → Short Summary

## Solution

We integrated the **Google Gemini API** through **LangChain** to generate concise summaries of the retrieved articles.

The summarization approach included:

> Passing the article content to Gemini

> A prompt asking for the main points in a concise form

> Storing the generated summary in the workflow's shared state

---

# Week 6 — News Bias Analysis

## Problem / Challenge

After summarization, the next challenge was helping users understand how individual articles present an event.

Different news sources may present the same event from different perspectives, and readers may find it difficult to identify possible bias in an individual article.

## Problems Faced

One of the main difficulties was that bias cannot be shown clearly using only general descriptions such as "neutral" or "one-sided", because such descriptions cannot be compared across articles.

Another difficulty was that a score alone does not explain why an article was considered biased.

Therefore, each article's analysis was defined as:

Article → Bias Score (1 to 5) → Reasoning

This made the results comparable and easier for users to understand.

## Solution

We designed an AI-based analysis mechanism using **Gemini**.

The bias analysis included:

> Analysing each article individually

> Assigning a bias score between 1 and 5

> Generating reasoning that explains the assigned score

> Adding bias analysis as a step in the AI workflow

---

# Week 7 — Data Validation and Error Handling

## Problem / Challenge

The next challenge was making the system reliable when data is missing or incorrect.

External APIs may return empty responses, invalid data or unexpected errors. AI-generated responses may also fail to follow the expected output structure.

## Problems Faced

The main difficulty was that the workflow expects data in a fixed structure, but the AI may return its answer as plain text.

For example, the system expects a bias score and reasoning as separate fields, but the response may be a single sentence such as "The bias score is around 3 because…".

If this happens, or if an external API fails, the next stage of the workflow cannot use the data.

## Solution

We prepared a validation and error-handling strategy.

The strategy included:

> **Pydantic** models for the expected output structure

> Validation of AI-generated responses

> Exception handling for API failures

> Handling of timeout errors

> Handling of invalid inputs and unexpected responses

---

# Week 8 — Testing and Reliability

## Problem / Challenge

The next challenge was planning how to verify that the system works correctly.

A system may work under normal conditions but fail when users provide invalid inputs, external APIs become unavailable or unexpected responses are received.

## Problems Faced

The main difficulty was that testing only a valid search does not show how the system behaves in failure situations.

For example, the system must also respond correctly when the query is empty, the API key is invalid or the AI response is not in the expected format.

Therefore, the test cases were divided into:

Normal Cases → Invalid Inputs → API Failures → Validation Failures

## Solution

We prepared test cases covering:

> Valid searches

> Empty queries

> Duplicate articles

> Invalid API credentials

> Gemini API failures

> JSON validation

**Pytest** and **Postman** were selected as testing tools to verify individual modules and the overall application workflow.

---

# Conclusion

During the development of KHABRI, different technical and functional challenges were identified and addressed through suitable software engineering approaches. The project involved news retrieval, AI-based summarization, bias analysis, workflow management, data validation and testing.

The problem-solution approach helped us understand the importance of modular development, API integration, structured data processing and system reliability. Further work will focus on strengthening error handling, executing automated tests, and improving the accuracy and performance of the platform.
