## About The Project

> All functionality is consolidated within a single notebook `HomeMatch.ipynb`.
> It is a real estate recommendation system that matches buyers with
> properties using semantic search and AI personalization. It stores 18 LLM-generated
> listings in a ChromaDB vector database, embeds buyer preferences (collected as
> structured Q&A) using OpenAI embeddings, and retrieves the top matching properties
> via cosine similarity. Each matched listing's description is then rewritten by
> GPT-4o-mini to highlight aspects most relevant to the buyer — without altering any
> factual details like price, bedrooms, or size.

> The generated listing are stored in `./resources/chatgpt_listings.json`.

## Dependencies

```bash
micromamba create -n jupyterlab4 python=3.10 jupyterlab -c pytorch -c conda-forge -c nvidia -y
micromamba run -n jupyterlab4 pip install -r requirements.txt
```

<details>
<summary>Project Instructions:</summary>

# 🏠 HomeMatch Application — Project Instructions

## Overview
Build the **HomeMatch** application in a Jupyter Notebook or Python file(s). Submit a zip file containing the application and supporting documentation.

---

## Step 1: Setting Up the Python Application

- Initialize a new Python project with a virtual environment
- Install necessary packages:
  - `LangChain`
  - An LLM library (e.g., OpenAI's GPT)
  - A vector database package (e.g., **ChromaDB** or **LanceDB**)
- Starter files are available in the workspace as an application skeleton if you prefer not to start from scratch

---

## Step 2: Generating Real Estate Listings

Use an LLM to generate **at least 10 real estate listings**. Create prompts that produce property descriptions in the following format:

```
Neighborhood: Green Oaks
Price: $800,000
Bedrooms: 3
Bathrooms: 2
House Size: 2,000 sqft

Description: Welcome to this eco-friendly oasis nestled in the heart of Green Oaks.
This charming 3-bedroom, 2-bathroom home boasts energy-efficient features such as
solar panels and a well-insulated structure...

Neighborhood Description: Green Oaks is a close-knit, environmentally-conscious
community with access to organic grocery stores, community gardens, and bike paths...
```

> These listings will populate the database for testing and development.

---

## Step 3: Storing Listings in a Vector Database

1. **Vector Database Setup** — Initialize and configure ChromaDB (or similar)
2. **Generate Embeddings** — Convert LLM-generated listings into embeddings that capture semantic content
3. **Store Embeddings** — Save the embeddings in the vector database

---

## Step 4: Building the User Preference Interface

Collect buyer preferences via structured questions or free-form natural language input. You may hard-code preferences or collect them interactively.

**Example questions & answers:**

```python
questions = [
    "How big do you want your house to be?",
    "What are 3 most important things for you in choosing this property?",
    "Which amenities would you like?",
    "Which transportation options are important to you?",
    "How urban do you want your neighborhood to be?",
]

answers = [
    "A comfortable three-bedroom house with a spacious kitchen and a cozy living room.",
    "A quiet neighborhood, good local schools, and convenient shopping options.",
    "A backyard for gardening, a two-car garage, and a modern, energy-efficient heating system.",
    "Easy access to a reliable bus line, proximity to a major highway, and bike-friendly roads.",
    "A balance between suburban tranquility and access to urban amenities like restaurants and theaters.",
]
```

- Implement logic to **interpret and structure** these preferences for querying the vector database

---

## Step 5: Searching Based on Preferences

- **Semantic Search** — Use structured buyer preferences to query the vector database and retrieve the closest matching listings
- **Fine-tune Retrieval** — Optimize the algorithm to ensure relevance based on semantic similarity

---

## Step 6: Personalizing Listing Descriptions

- **LLM Augmentation** — For each retrieved listing, use the LLM to tailor the description to the buyer's specific preferences, subtly emphasizing relevant aspects
- **Maintain Factual Integrity** — The augmentation should enhance appeal **without altering any factual information**

---

## Step 7: Deliverables & Testing

- [ ] Test with multiple different buyer preference inputs
- [ ] Ensure all rubric requirements are met (project code will be executed during assessment)
- [ ] Code is well-commented and logically structured
- [ ] Include **example outputs** showing how preferences are processed and descriptions are personalized (in comments or saved notebook outputs)

---

## Step 8: Project Submission

| File | Description |
|---|---|
| `listings` | Your synthetically generated real estate listings |
| `README.md` | Explains functionality, how to run, prerequisites, and dependencies |
| Notebook / `.py` | Your Jupyter Notebook or Python program |

Submit the zip file on the **Project Submission Page**.

---

## ⭐ Stand-Out Suggestion

> Want to go above and beyond? Add **images** to real estate listings and implement **multi-modal search** using [CLIP](https://openai.com/research/clip) for image-based semantic search.

</details>
