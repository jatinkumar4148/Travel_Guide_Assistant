# 🌍 Travel FAQ Assistant — Streamlit + FAISS + FLAN-T5

A simple **Travel Itinerary Generator** web app built using **Streamlit**, **FAISS**, **Sentence-Transformers**, and **FLAN-T5**.

This project allows users to select a destination and generate a **day-wise travel itinerary** based on:
- Number of days
- Budget
- Preferences (food, culture, etc.)

It uses a **retrieval + generation pipeline** where the most relevant travel guide is retrieved using FAISS and then passed to FLAN-T5 for itinerary generation.

---

## 🚀 Features

- ✅ Select destination from a built-in travel guide dataset  
- ✅ Enter trip details: days, budget, preferences  
- ✅ Uses **SentenceTransformer embeddings** for semantic search  
- ✅ Uses **FAISS** for similarity-based retrieval  
- ✅ Uses **FLAN-T5** to generate itinerary from retrieved context  
- ✅ Shows the source travel guide used  

---

## 🧠 How It Works (Pipeline)

1. Travel guides are stored as text documents (Python dictionary).
2. Documents are embedded using:
   - `all-MiniLM-L6-v2`
3. FAISS stores these embeddings in a vector index.
4. User query is embedded and searched in FAISS.
5. Top result (`k=1`) is retrieved as context.
6. FLAN-T5 generates the itinerary using only that context.

---

## 🛠️ Tech Stack

| Purpose | Technology |
|--------|------------|
| Frontend/UI | Streamlit |
| Vector Search | FAISS |
| Embeddings | Sentence Transformers |
| LLM | google/flan-t5-base |
| Language | Python |

---

## 📦 Installation

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
2️⃣ Install Required Libraries
pip install streamlit faiss-cpu
pip install transformers==4.38.2 tokenizers==0.15.2 accelerate==0.27.2 sentence-transformers==2.6.1
▶️ Run the App
streamlit run app.py
The app will run at:

http://localhost:8501
📂 Project Structure
📦 Travel-FAQ-Assistant
 ┣ 📜 app.py
 ┣ 📜 README.md
 ┗ 📜 requirements.txt  (optional)
🧾 Example Input
Destination: Delhi

Days: 3

Budget: 1500

Preferences: food and culture

Output
Day-wise itinerary (bullet points)

3 local tips

Source travel guide used

📌 Notes
This project uses a small built-in dataset (hardcoded travel guides).

Retrieval is currently set to k=1 (top 1 most relevant guide).

You can increase k to improve context retrieval.

🔥 Future Improvements
Add more destinations and travel guides

Multi-document retrieval (k=3 / k=5)

Store travel guides in JSON/CSV instead of hardcoding

Add a chat-based interface

Deploy on Streamlit Cloud / HuggingFace Spaces

👤 Author
Jatin Kumar
B.Tech CSE (AI/ML) Student
AKTU | IMSEC
