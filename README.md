![Beyond the Swipe: Investigating Dating App Marketing and User Perception](graphics/Beyond_the_Swipe_Poster.png)


Final project in collaboration with Helen Tian for **DATASCI 112: Principles of Data Science** with Professor Dennis Sun, Winter '25.  
This project explores how different dating apps are marketed and how they are received by users, combining **qualitative coding, clustering, and natural language analysis**.


## Project Overview
Dating apps are now a major way people connect: nearly **3 in 10 Americans have tried one** [1].  
We conducted an **exploratory analysis** of **17 dating apps across 7 categories** to examine:
- How platforms market themselves through visuals and language.
- How users perceive and review these apps on the Google Play Store.

We combined **manual qualitative coding** with **data science methods** (TF-IDF, clustering, prompt-engineered GPT classification) to uncover themes in both marketing and user feedback.


## Research Questions
1. How do different dating apps approach marketing, and how do their strategies compare?  
2. How are dating apps perceived and reviewed by users?  


## Data Collection
1. **Scraping app data**:  
   - Used [`google-play-scraper`](https://pypi.org/project/google-play-scraper/) [2] to collect app descriptions and the **200 most recent reviews** for each app.  

2. **Qualitative coding of marketing materials**:  
   - Manually annotated Google Play Store advertising spreads (e.g., font style, color palette, model ethnicity, model expression, clothing coverage).  

3. **Qualitative coding of reviews**:  
   - Developed a scheme to capture common topics (UX, monetization, community, etc.).  
   - Hand-coded 100 reviews for reliability testing.  

4. **Scaling with GPT**:  
   - Trained GPT-4o-mini [3] with prompt-engineering to apply our coding scheme to 500 reviews (achieving inter-rater reliability κ ≥ 0.75).  

5. **Additional features**:  
   - Word counts for each review.  
   - Download counts and app ratings (as of March 6, 2025).  


## Methods
- **Marketing Analysis**:  
  - TF-IDF on app descriptions.  
  - One-hot encoding on ad design features.  
  - **K-Means clustering** (K = 4, determined via elbow method).  

- **User Review Analysis**:  
  - Grouped reviews by app and app genre.  
  - Data visualizations highlighting distribution of review topics, sentiment, and review length.  


## Results
- **Marketing clusters**: Apps fell into 4 groups based on branding and description text:
  1. **Queer Male Apps**: Grindr, SCRUFF.  
  2. **General & Niche Apps**: Tinder, Bumble, HER, Zoe, Taimi, Christian Mingle, Muzz, Jswipe, Mutual, Ourtime.  
  3. **Relationship-Oriented**: Hinge.  
  4. **Exclusive/High-Status Apps**: Millionaire Match, Luxy, The League, Senior Match.  

- **Marketing differentiators**:  
  - Color scheme, model expression, and model ethnicity were the strongest distinguishing features.  

- **User review patterns**:  
  - **Negative reviews were longer** than positive ones.  
  - **Queer sapphic apps** had the highest rate of positive sentiment.  
  - **Religious apps** had the highest rate of negative sentiment.  
  - Monetization, user interactions, and poor UX were the dominant negative themes.  


## References:
[1] [Key findings about online dating in the U.S.](https://www.pewresearch.org/short-reads/2023/02/02/key-findings-about-online-dating-in-the-u-s/) (Pew Research Center)

[2] We took inspiration from the [Dating Apps Reviews 2017-2022 (all regions)](https://www.kaggle.com/datasets/sidharthkriplani/datingappreviews) project on Kaggle, which referenced the [google-play-scraper] (https://pypi.org/project/google-play-scraper/)

[3] We used skeleton code from [Rathje et al., 2024](https://www.pnas.org/doi/10.1073/pnas.2308950121) to train GPT on our qualitative coding scheme. Huge thank you to the Stanford SPARQ lab for support in this process.