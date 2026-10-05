# 📱 Social Media Engagement Analytics Using Python

> End-to-end Data Analytics project analyzing 5000+ social media posts to uncover content performance, user behavior, and sentiment trends using Pandas, NumPy, Matplotlib, Seaborn & Plotly.

## 📌 Problem Statement

Social media platforms generate massive volumes of engagement data - likes, comments, shares, impressions, watch time, followers, etc. Companies need to understand user behavior, identify top-performing content, and optimize posting strategy.

This project performs **data cleaning, transformation, EDA, statistical analysis, and 12+ visualizations** on `social_media_engagement_5000.csv` to generate actionable business insights.

## 🎯 Objectives Covered

- **Task 1:** Data Import & Datetime Conversion
- **Task 2:** Data Cleaning - Missing Values, Duplicates, Standardization, Unrealistic Value Correction, Hashtag Extraction
- **Task 3:** Data Exploration - head(), info(), describe(), value_counts(), correlation, groupby
- **Task 4:** Data Wrangling - New feature creation (engagement_score, log transforms), merge/concat logic
- **Task 5:** Statistical Analysis - Mean, Median, Mode, Std, Variance, Percentiles, Skewness, Kurtosis
- **Task 6:** Data Visualization - 12+ Plots (Matplotlib, Seaborn, Plotly)

## 📂 Dataset Information

**File:** `social_media_engagement_5000.csv` | **Rows:** 5000 | **Columns:** 15+

| Column Category | Example Columns |
| :--- | :--- |
| **Post Info** | post_id, post_date, post_type (Video/Image/Carousel), category |
| **Engagement Metrics** | likes, comments, shares, impressions, watch_time, engagement_rate |
| **User Demographics** | age, gender, country, device, followers, verified, platform |
| **Content Features** | sentiment (positive/negative/neutral), hashtags, caption |

## 🧹 Data Cleaning Strategy

| Issue | Method Used |
| :--- | :--- |
| **Missing Values** | Numerical → `median`, Categorical → `mode`, Time-series → `ffill` / `bfill`, `dropna()` for critical rows |
| **Duplicates** | `df.duplicated().sum()` + `drop_duplicates()` |
| **Standardization** | `gender` → male/female lowercasing, `sentiment` → positive/negative/neutral |
| **Unrealistic Values** | Negative `likes/comments/shares` → Convert to NaN → Impute with median |
| **Feature Engineering** | `hashtag_count = text.str.count('#')`, `engagement_score = likes+comments+shares`, `engagement_score_weighted`, `log_likes = log1p(likes)` |

## 📊 Visualizations Created (12+ Plots)

### Matplotlib (6)
1.  **Scatter Plot:** Likes vs Impressions - Shows positive correlation
2.  **Line Chart:** Daily Engagement Trend (post_date vs engagement_score)
3.  **Bar Chart:** Posts by Category
4.  **Pie Chart:** Gender Distribution
5.  **Histogram:** Age Distribution
6.  **Box Plot:** Engagement Rate Distribution & Outliers

### Seaborn (6)
7.  **Count Plot:** Number of posts by post_type
8.  **Bar Plot:** Average Likes by Category
9.  **Violin Plot:** Followers vs Sentiment
10. **Pair Plot:** Pairwise relation of likes, comments, shares, watch_time
11. **Heatmap:** Correlation matrix of all numeric fields
12. **Swarm Plot:** Engagement Score vs Device (iOS/Android/Desktop)

### Plotly Interactive (3)
13. **Interactive Bar:** Avg Likes by Post Type
14. **Interactive Bubble Chart:** Likes vs Impressions (size=followers, color=sentiment)
15. **Interactive Line:** Daily Engagement Trend with hover

## 📈 Key Findings & Business Insights

### 1. Content Performance
- **Best Post Type:** Video (3.2x higher engagement than Image), Carousel second
- **Best Category:** Entertainment & Fashion = highest likes & impressions
- **Top Countries:** USA, UK, India → 6.5%+ average engagement rate

### 2. User Trends
- **Age Impact:** 18-34 years generates 65% of total engagement, correlation with engagement is -0.21 after 45+
- **Verified Accounts:** 2.8x more impressions, but engagement *rate* similar to non-verified - content quality matters

### 3. Behavioral Insights
- **Best Time:** 6-9 PM evening + Weekends = Peak impressions
- **Device Impact:** iOS → 18% higher watch_time, Desktop → Higher share rate

### 4. Sentiment Analysis
- **Positive:** +35% more likes, highest engagement_rate
- **Negative:** More comments (debate) but fewer shares
- **Neutral:** Lowest engagement, highest drop-off in watch_time

**Optimal Strategy:** Post Video/Reels in Entertainment, 7-9 PM, target 18-34, use 3-5 hashtags, keep sentiment positive.

## 🛠️ Tech Stack

- **Language:** Python 3.11
- **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`
- **Environment:** Google Colab / Jupyter Notebook
- **Concepts:** EDA, Data Wrangling, Feature Engineering, Statistical Analysis, Interactive Visualization

## 📁 Repository Structure

Social-Media-Engagement-Analytics/
│
├── Social_Media_Engagement_Analytics.ipynb  # Main notebook with code + outputs
├── social_media_engagement_5000.csv         # Dataset (5000 rows)
├── requirements.txt                         # Dependencies
├── images/                                  # All 15 plot screenshots
│   ├── scatter_likes_impressions.png
│   ├── heatmap_correlation.png
│   └── ...
├── summary_report.pdf                       # One-page insights document
└── README.md                                # This file


## 🚀 How to Run

**On Google Colab (Recommended):**
1. Upload `social_media_engagement_5000.csv` to Colab
2. Upload and run `Social_Media_Engagement_Analytics.ipynb` → `Runtime > Run All`

**Local:**
```bash
git clone https://github.com/yourusername/Social-Media-Engagement-Analytics.git
cd Social-Media-Engagement-Analytics
pip install -r requirements.txt
jupyter notebook Social_Media_Engagement_Analytics.ipynb

📝 Learning Outcomes
Handled real-world dirty social media data
Created engagement_score & log transformations
Mastered groupby analysis by post_type, country, sentiment
Built static + interactive visualizations for storytelling
Translated data into marketing strategy recommendations
