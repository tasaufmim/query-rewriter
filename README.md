**Personalized Query Rewriting AI**
An interactive NLP system that rewrites user queries based on user profile data to provide personalized and context-aware search inputs. The system uses a large language model (LLM) for rewriting, evaluates semantic similarity with BERTScore, and applies heuristic checks for personalization.


**Dataset**
The system uses a JSON-based user profile as its dataset. Each profile contains:
Demographics: age, gender, location, marital status
Education & Job history: degrees, past and current jobs
Preferences: activities, clothing, gadgets, food, sports
Interests & Lifestyle: hobbies, movies, daily habits
Search behavior & customer support history: past searches, service interactions


**Assumptions**
The user profile contains sufficient context for query personalization.
Queries are in English.
Rewritten queries must strictly use profile information if relevant.
Heuristic evaluation uses substring matching to determine personalization.


**Setup Instructions**
1. Clone the repository:
git clone https://github.com/yourusername/personalized-query-rewriter.git
cd personalized-query-rewriter

2. Install dependencies:
pip install -r requirements.txt

3. Create a .env file with your Groq API key:
GROQ_API_KEY=your_api_key_here

4. Prepare user_profile.json with the user profile data.

5. Run the chat loop:
python query_rewriter.py


**Project Structure**
query-rewriter/
│
├── chat_rewriter.py      # Main chat loop script
├── user_profile.json     # User profile JSON
└── .env


**Technologies Used**
- Python 3.10+
- Groq LLM API for query rewriting
- BERTScore for semantic similarity
- JSON for storing user profiles
- dotenv for environment variable management
