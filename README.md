# Digital Storefront Recommendation System

A Machine Learning-powered recommendation engine built for digital gaming storefronts. This project utilizes Content-Based Filtering to suggest games to users based on shared metadata rather than user purchase history.

This repository contains a complete Jupyter Notebook (Digital Storefront Recommendation System.ipynb) that walks through data cleaning, feature engineering, and the deployment of a custom recommendation function with real-world budget and hardware constraints.

🧠 Project Workflow & Methodology

This project follows a strict data science pipeline:

Data Cleaning: Inspecting the Kaggle Steam dataset (steam.csv) for missing values using .isnull().sum() and selectively dropping nulls in crucial text columns (name, genres, steamspy_tags) to prevent computational errors.

Feature Engineering (The "Metadata Soup"): Combining individual columns (developer, categories, genres, steamspy_tags) into a single, comprehensive text string for each title. Semicolons used in the raw data were systematically replaced with spaces to ensure clean parsing.

TF-IDF Vectorization: Utilizing TfidfVectorizer (with English stop-words removed) to convert text data into numerical vectors. This down-weights hyper-common terms (like "Singleplayer") and prioritizes highly specific niche identifiers.

Cosine Similarity: Calculating the mathematical angle between game vectors to generate a comprehensive similarity matrix.

Custom Filtering Logic: Passing the similarity results through custom parameters (Max Price and Required Platform) to ensure the recommendations are actionable for the user's specific constraints.

🛠️ Tech Stack

Language: Python

Environment: Jupyter Notebook

Data Manipulation: Pandas

Machine Learning: Scikit-Learn (TfidfVectorizer, cosine_similarity)

Dataset: Steam Store Games Dataset (steam.csv)

🚀 Quick Start (Local Installation)

To run this notebook on your local machine, follow these steps:

1. Clone the repository:

git clone [https://github.com/](https://github.com/)<your-username>/digital-storefront-recommender.git
cd digital-storefront-recommender


2. Install dependencies:
Make sure you have Python and Jupyter installed, then run:

pip install pandas scikit-learn jupyter


3. Run the notebook:

jupyter notebook "Digital Storefront Recommendation System.ipynb"


💻 Usage & Example Output

The core function get_recommendations() accepts a game title and optional constraints for wallet budget (max_price) and operating system (required_platform).

Code Execution:

# User wants games similar to "Counter-Strike"
# Constraint 1: Must be under $10.00
# Constraint 2: Must be playable on MacOS

print("Recommendations for Counter-Strike (Under $10, Mac compatible):")
print(get_recommendations('Counter-Strike', max_price=10.00, required_platform='mac'))


System Output:

Recommendations for Counter-Strike (Under $10, Mac compatible):
['Team Fortress Classic ($3.99)', 'Deathmatch Classic ($3.99)', 'Ricochet ($3.99)', 'Counter-Strike: Condition Zero ($7.19)', 'Half-Life Deathmatch: Source ($0.0)']


📂 Repository Structure

├── steam.csv                                      # The core dataset
├── Digital Storefront Recommendation System.ipynb # The main project notebook
└── README.md                                      # Project documentation


🔮 Future Enhancements

Interactive Web App: Wrap the Python logic into a Streamlit or Gradio interface so non-technical users can interact with the engine using UI sliders.

Hardware Integration: Integrate additional datasets containing Minimum VRAM or CPU requirements to filter out games a user's PC cannot physically run.

Data Manipulation: Pandas

Machine Learning: Scikit-Learn (TfidfVectorizer, cosine_similarity)

Dataset: Steam Store Games Dataset (Kaggle)

🚀 Quick Start (Local Installation)
To run this project on your local machine, follow these steps:

1. Clone the repository:

Bash
git clone https://github.com/<your-username>/digital-storefront-recommender.git
cd digital-storefront-recommender
2. Install dependencies:
Make sure you have Python installed, then run:

Bash
pip install -r requirements.txt
(Note: Ensure your requirements.txt includes pandas and scikit-learn)

3. Run the script:

Bash
python app.py
💻 Usage Example
The core function get_recommendations() accepts a game title and optional constraints.

Python
# User wants games similar to "Counter-Strike"
# Constraint 1: Must be under $10.00
# Constraint 2: Must be playable on MacOS

