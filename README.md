# HumanAI_ISSR3_test

## Background
Mental health crises, substance use disorders, and suicide risk are growing global concerns, often exacerbated by social, economic, and environmental stressors. Timely intervention is crucial, but traditional approaches rely on self-reporting, which may be delayed or inaccurate. In recent years, AI and data-driven approaches have emerged as powerful tools for identifying distress patterns and enabling early interventions.
This project leverages AI-powered behavioral analysis to detect signs of mental health crises, suicide risk, and substance use disorders by analyzing textual and geospatial data. By applying Natural Language Processing (NLP), sentiment analysis, and machine learning, the system identifies high-risk individuals and communities based on social media posts, online forums, and other public discourse. Additionally, longitudinal geospatial trend analysis enables tracking crisis hotspots over time, helping policymakers and mental health professionals deploy resources effectively.

## Tasks
**Task 1** : Social Media Data Extraction & Preprocessing (API Handling & Text Cleaning)
**Data Collection Using Reddit API (PRAW)**
- Used PRAW (Python Reddit API Wrapper) to access Reddit posts.
- Defined a list of relevant subreddits (e.g., r/depression, r/SuicideWatch, r/mentalhealth, r/addiction).
- Extracted:
  - Title and selftext (post content).
  - Comments (engagement analysis).
  - Upvotes/Downvotes (engagement analysis).
  - Timestamp (for longitudinal analysis).
  - Subreddit Name (to identify crisis-focused communities).
  - Post Id
**Following is the snapshot the dataset extracted**
    
![image](https://github.com/user-attachments/assets/605f6565-33cb-4bfc-baff-9b542dae8a8e)

**Data Preprocessing**
- Text Cleaning:
  - Removed special characters, stopwords, and URLs.
  - Converted text to lowercase for uniformity.
  - Used NLTK to remove stopwords.
    
**Following is the cleaned dataset for NLP Analysis**

![image](https://github.com/user-attachments/assets/cfd86f5d-6bb3-41d7-a0d5-86d241eeafe5)

## **Task 1 Deliverable**
- Python Script to retrieve and store filtered social media posts [Script](https://github.com/2002hk/HumanAI_ISSR3_test/blob/main/Reddit_data.ipynb)
- cleaned dataset ready for NLP analysis [cleaned_data.csv](https://github.com/2002hk/HumanAI_ISSR3_test/blob/main/reddit_cleaned_data%20(1).csv)


