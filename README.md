# Personalized Query Rewriting AI

An **interactive NLP system** that rewrites user queries based on user profile data to provide personalized and context-aware search inputs. The system uses a **large language model (LLM)** for rewriting, evaluates semantic similarity with **BERTScore**, and applies **heuristic checks** for personalization.

---

## Dataset

The system uses a **JSON-based user profile** as its dataset. Each profile contains:

* **Demographics:** age, gender, location, marital status
* **Education & Job history:** degrees, past and current jobs
* **Preferences:** activities, clothing, gadgets, food, sports
* **Interests & Lifestyle:** hobbies, movies, daily habits
* **Search behavior & customer support history:** past searches, service interactions

**Example JSON:**

```json
{
  "user_id": "u123",
  "full_name": "Daniel Scott",
  "demographics": {"age": 34, "gender": "Male", "location": "Austin, Texas"},
  "preferences": {"activities": "cycling, reading sci-fi, gaming", "food": "BBQ, Mexican, sushi"},
  "interests": "AI research, space exploration, NBA news",
  "movies": "sci-fi thrillers, documentaries, comedies",
  "lifestyle": "Tech-savvy remote worker, spends evenings biking or gaming"
}
```

---

## Assumptions

* The **user profile contains sufficient context** for query personalization.
* Queries are in **English**.
* Rewritten queries must **strictly use profile information** if relevant.
* Heuristic evaluation uses **substring matching** to determine personalization.

---

## Setup Instructions

1. Clone the repository:

```bash
git clone github.com/tasaufmim/query-rewriter
cd query-rewriter
```

2. Install dependencies:

```bash
!pip install groq python-dotenv --quiet
!pip install bert-score --quiet
```

3. Create a `.env` file with your Groq API key:

```
GROQ_API_KEY=your_api_key_here
```

4. Prepare `profile.json` with the user profile data.

5. Run the chat loop:

```bash
python chat_rewriter.py
```

---

## Evaluation Summary

Each rewritten query is evaluated using:

1. **BERTScore** – Measures semantic similarity with the original query.
2. **Heuristic Evaluation** – Checks for the presence of profile-related keywords in the rewritten query.
3. **Combined Confidence Score** – Weighted combination of BERTScore (70%) and heuristic (30%).

**Example Output:**

```
User: best food to order
Rewritten: Best high-protein Mexican or BBQ dishes in Austin, Texas
BERTScore: 0.89
Heuristic Evaluation: Personalized
```

---
