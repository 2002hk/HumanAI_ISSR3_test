# HumanAI_ISSR3_test

## Background
Mental health crises, substance use disorders, and suicide risk are growing global concerns, often exacerbated by social, economic, and environmental stressors. Timely intervention is crucial, but traditional approaches rely on self-reporting, which may be delayed or inaccurate. In recent years, AI and data-driven approaches have emerged as powerful tools for identifying distress patterns and enabling early interventions.
This project leverages AI-powered behavioral analysis to detect signs of mental health crises, suicide risk, and substance use disorders by analyzing textual and geospatial data. By applying Natural Language Processing (NLP), sentiment analysis, and machine learning, the system identifies high-risk individuals and communities based on social media posts, online forums, and other public discourse. Additionally, longitudinal geospatial trend analysis enables tracking crisis hotspots over time, helping policymakers and mental health professionals deploy resources effectively.

## Tasks
**Task 1** : **Social Media Data Extraction & Preprocessing (API Handling & Text Cleaning)**
**Data Collection Using Reddit API (PRAW)**
- Used PRAW (Python Reddit API Wrapper) to access Reddit posts.
- Defined a list of relevant subreddits (e.g., r/depression, r/SuicideWatch, r/mentalhealth, r/addiction).
- Extracted:
  - Title and selftext (post content).
  - Comments (engagement analysis).
  - Upvotes/Downvotes (engagement analysis).
  - Timestamp (for longitudinal analysis).
  - Subreddit Name (to identify crisis-focused communities).
  - Post Id.

**Below is the snapshot of the dataset extracted**
    
![image](https://github.com/user-attachments/assets/605f6565-33cb-4bfc-baff-9b542dae8a8e)

**Data Preprocessing**
- Text Cleaning:
  - Removed special characters, stopwords, and URLs.
  - Converted text to lowercase for uniformity.
  - Used NLTK to remove stopwords.
    
**Below is the cleaned dataset for NLP Analysis**

![image](https://github.com/user-attachments/assets/cfd86f5d-6bb3-41d7-a0d5-86d241eeafe5)

## **Task 1 Deliverable**
- Python Script to retrieve and store filtered social media posts [Script](https://github.com/2002hk/HumanAI_ISSR3_test/blob/main/Reddit_data.ipynb)
- cleaned dataset ready for NLP analysis [cleaned_data.csv](https://github.com/2002hk/HumanAI_ISSR3_test/blob/main/reddit_cleaned_data%20(1).csv)

**Task 2** : **Sentiment & Crisis Risk Classification (NLP & Text Processing)**
## Sentiment Analysis Methods
**VADER Sentiment Analysis (get_vader_sentiment)**
- Uses VADER (Valence Aware Dictionary and sEntiment Reasoner) to get sentiment scores.
- Extracts the compound score (ranges from -1 to +1).
- Classifies sentiment based on thresholds:
  - ≥ 0.05 → Positive
  - ≤ -0.05 → Negative
  - Between -0.05 and 0.05 → Neutral
- Best suited for short text and social media data, as VADER considers emoticons, capitalization, and punctuation.

**TextBlob Sentiment Analysis (get_textblob_sentiment)**
- Uses TextBlob to determine the polarity score (ranges from -1 to +1).
- Classification logic:
  - Greater than Zero  Positive
  - Less than Zero Negative
  - Equal to Zero Neutral
- Based on a lexicon-based approach, which works well for longer, grammatically correct sentences.

**Comparison Between VADER and TextBlob**
| Feature | VADER | TextBlob | 
|-----------------|-----------------|-----------------|
| Type of Analysis  | Rule-based  | Lexicon-based
| Handles Emojis, Slang, Punctuation  | ✅ Yes  | ❌ No
| Works Best For  | Short, informal text (tweets, Reddit, chat)  | Long, structured text (news, reviews
| Sentiment Score Used  | Compound polarity  | Polarity score
| Performance on Social Media  | Better (handles context well)  | Weaker (misses sarcasm, slang)

## **Task 2 Deliverable**
- script that classifies posts based on sentiment and risk level. [Script](https://github.com/2002hk/HumanAI_ISSR3_test/blob/main/sentiment_classification_of_reddit_data.ipynb)
- Below is plot showing the distribution of posts by sentiment and risk category.
  
![image](https://github.com/user-attachments/assets/2b42eb75-ffff-47bd-a162-68303513c6e9)


![image](https://github.com/user-attachments/assets/6dad79ca-c9ed-40d7-b139-9d607aad1bc7)

**Task 3** : **Crisis Geolocation & Mapping (Basic Geospatial Analysis & Visualization)**
**Limitations & Missing Locations:**
- Reddit does not provide geotags or direct location metadata for posts.
- This meant that locations had to be manually extracted from post content instead of using metadata.

## Location Extraction Process:
- Extracted location names from:
  - Post titles & body text (e.g., "Flooding in Mumbai, India")
- Used Named Entity Recognition (NER) (spaCy or NLTK) to detect place names (cities, countries).
- Converting Locations to Latitude & Longitude:
  - Used Geocoder (geopy) to convert extracted place names into latitude & longitude coordinates.
  - This helped in mapping crisis discussions geographically.
  - Used Folium & Plotly to generate a heatmap showing crisis discussion intensity.

## **Task 3 Deliverable**
- A Python script that geocodes posts and generates a heatmap of crisis discussions. [Script](https://github.com/2002hk/HumanAI_ISSR3_test/blob/main/sentiment_classification_of_reddit_data.ipynb)
- Below is visualization of regional distress patterns in the dataset.

![image](https://github.com/user-attachments/assets/886ad2a4-a483-4d6e-928b-2bce88658ad3)
