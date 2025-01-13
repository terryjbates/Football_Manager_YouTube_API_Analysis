# Football Manager YouTube Video Analysis

Analysis of Football Manager (FM) YouTube content to understand trends, high-performing video categories, and viewership patterns using Python, Pandas, Seaborn, Plotly, Microsoft Excel, and DuckDB.


# Table of Contents

* [Project Summary](#project-summary) 
* [Background](#background)
* [Data Overview](#data-overview) 
* [Analytical Techniques](#analytical-techniques)
* [Tools and Technologies](#tools-and-technologies)
* [Analysis Process](#analysis-process)
* [Insights](#Insights)
* [Visualizations](#visualizations)
* [Next Steps](#next-steps)
* [Repository Structure](#repository-structure)


# Project Summary

This project analyzes Football Manager-related YouTube content, identifying key content categories, patterns in viewership trends, and correlations between video performance and metadata. The analysis provides insights for content creators and businesses targeting the Football Manager audience, showcasing the dynamics of high-performing content and its evolution over time.

# Background

## The Football Manager Ecosystem
Football Manager (FM) is a popular football management simulation game with a strong and engaged global community. Content creators on platforms like YouTube play a significant role in promoting the game, sharing gameplay strategies, experiments, challenges, and tutorials that appeal to both casual players and die-hard fans. FM content ranges from rebuilds of historic football clubs to Wonderkid scouting guides and extreme gameplay experiments, all of which contribute to the game's vibrant ecosystem.

## The YouTube Platform for Football Manager Content 
YouTube has become a centralized hub for FM content, with creators building loyal fan bases through various types of videos, covering genres of gameplay, tutorials, and community collaborations with other content creators. Identifying trends and patterns in video performance is essential for understanding what drives engagement in this niche, and how its viewer base has expanded and shifted over time.


# Data Overview

Primary data sources:

* The [YouTube Data API](https://developers.google.com/youtube/v3/docs/search/list) was used to extract video metadata, performance metrics, and channel information. By leveraging the API, we collected data on thousands of Football Manager-related videos. 

* API-extracted data was processed and stored locally [DuckDB](https://duckdb.org/) database tables to allow for efficient querying and data manipulation throughout the project.

* Extracts of dataframe information were exported to CSV and Pivot Tables in [Microsoft Excel](https://microsoft.com/en-us/microsoft-365/excel) were used to categorize video data into genres, as well as the use of area charts to track trends and content creator footprint.

# Analytical Techniques

## Data Cleaning and Processing

To ensure data consistency, columns with inconsistent capitalization, special characters, or missing values were cleaned. Descriptive statistics and exploratory analysis were conducted to summarize the data.

## Categorization

Videos were categorized based on their title and description. Word frequency analysis and clustering techniques helped reveal trends and associations in content. Categories include:

* Challenges
* Experiments
* Rebuilds and Team Development
* Player Development
* Guides and Tutorials
* Community Collaborations
* Discussion

## Correlation Analysis

[Pearson’s Correlation Coefficient](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient) was used to analyze relationships between view counts, like counts, comment counts, and other metrics.

## Time Series Analysis

Video viewership patterns were analyzed over time, with specific attention to periods of increased engagement, such as the months surrounding new FM releases.


# Tools and Technologies

## Data Collection and Storage
- **YouTube Data API**: For fetching video metadata and engagement metrics.
- **DuckDB**: For SQL-based data querying of dataframes and local database storage.
- **Selenium**: Automated browser interactions to simulate user scrolling and dynamically load video lists.
- **Chrome WebDriver**: A tool for controlling Chrome browser sessions programmatically.

## Data Analysis and Processing
- **Python**: Programming language used for API data extraction, data manipulation, and analysis.
  - **pandas**: Data cleaning, transformation, and analysis.
  - **NumPy**: Numerical operations and efficient data handling.
  - **re**: Text processing with regular expressions.
  - **NLTK**: Text processing and stopword removal.
  - **func_timeout**: Managing long-running web scraping activity with timeouts.
  - **datetime**: Handling and formatting timestamps.
  - **langdetect**: Language detection library to detect creator language.


## Data Visualization
- **matplotlib**: Static plot creation.
- **seaborn**: Pairplots, scatterplots, barplots, and other visualizations.
- **Plotly**: Interactive visualizations (e.g., stacked bar plots, scatter plots).
- **WordCloud**: Wordcloud generation from text data.
- **Pivot Tables**: Aggregations of groups of individual data within one or more discrete categories.
- **Area Charts**: Graphic display of quantitative data.

## Workflow and Environment
- **Jupyter Notebooks**: Organization and documentation of data analysis and visualization efforts.
- **Anaconda**: Python development environment and dependencies.
- **Microsoft Excel**: Spreadsheet editor.

# Methodology


This section outlines the steps taken to collect, process, and analyze the data in this project. The methodology follows a structured approach, ensuring clarity, reproducibility, and alignment with data analysis best practices.

## 1. Define Project Objectives and Scope
The goal of this project was to analyze Football Manager (FM) YouTube content, identify key engagement patterns, and explore content trends to uncover actionable insights for creators and analysts. The scope included collecting data from YouTube channels, engagement metrics, and content categories relevant to Football Manager videos.

---

## 2. Data Collection
- **YouTube Data API Integration**:  
  The YouTube Data API was utilized to gather channel and video metadata. Search terms such as “FM24” and “Football Manager” were used to identify relevant content.
- **Manual Scraping with Selenium and Chrome Webdriver**:  
  To bypass YouTube Data API quota limitations, Selenium was employed to extract video IDs directly from playlist URLs.
- **Data Persistence**:  
  All collected data was stored in DuckDB and CSV files for efficient querying and reproducibility.

---

## 3. Data Cleaning and Preprocessing
- **Filtering Non-Relevant Channels**:  
  Channels unrelated to Football Manager were excluded based on domain knowledge and keyword-based filtering.
- **Standardizing Keywords**:  
  Channel branding keywords were cleaned and transformed into lists to enable keyword-specific analysis.
- **Feature Engineering**:  
  Several new columns were created to enhance the dataset, including:
  - `numeric_duration` for video lengths in seconds.
  - `publish_day_name` for day-of-week analysis.
  - `LikeRatio` and `CommentRatio` to normalize engagement metrics.

---

## 4. Exploratory Data Analysis (EDA)
- **Summary Statistics**:  
  Descriptive statistics provided an overview of key metrics like subscribers, views, and likes.
- **Visualizations**:  
  Histograms, scatterplots, and boxplots were used to reveal patterns and distributions in the data.
- **Correlation Analysis**:  
  Relationships between likes, views, comments, and video duration were analyzed using correlation coefficients.

---

## 5. Content Categorization and Trends Analysis
- **Primary and Secondary Categories**:  
  Videos were classified into categories such as “Challenges,” “Experiments,” and “Rebuilds” to uncover dominant themes.
- **Wordcloud Analysis**:  
  Video descriptions were aggregated and visualized to identify prominent terms and content trends.
- **Seasonality Analysis**:  
  Engagement patterns over time were analyzed, with a focus on the release cycles of Football Manager games and their impact on video performance.

---

## 6. Insights and Findings
- **Engagement Patterns**:  
  Strong correlations were observed between views and likes, while moderate correlations existed between likes and comments.
- **Content Trends**:  
  Categories like “Experiments” dominated earlier years, while “Challenges” have gained traction in recent years.
- **Top Creators**:  
  Key creators such as Zealand and NickRTFM were identified as leaders in the Football Manager YouTube content space.

---

## 7. Documentation and Reporting
- **Notebook Organization**:  
  Inline comments and markdown cells documented each step of the analysis process, ensuring transparency and reproducibility.
- **Interactive Visuals**:  
  Generated plots and dashboards provided accessible and engaging insights for readers.




# Insights

The analysis uncovered a vibrant community of 575 YouTube channels producing Football Manager content, with 46% eligible for monetization. Subscriber data reveals a top-heavy distribution, where the top 20% of creators dominate 62% of total subscribers. Among them, secondary channels from creators like Zealand and Lollujo reflect attempts to diversify their audience.

Subscriber count strongly correlates with total views (0.95), and the top-performing videos come from established creators like NickRTFM and Zealand. Interestingly, while 77% of monetizable channels use branding keywords, there is no correlation between their use and engagement metrics like views, likes, or comments. Similarly, running time shows no significant impact on these metrics, offering creators flexibility in content length.

Seasonal trends show spikes in views surrounding Football Manager game release dates, while content like "Challenges" and "Rebuilds" has gained popularity since 2021. The data suggests that niche categories, such as “Experiments” and “Player Development,” may attract high engagement when aligned with audience expectations.


## High-Performing Content
* Challenges and Experiments consistently drew high viewership, with creators like DoctorBenjy FM and TomFM excelling in these categories.
* Player Development and Guides and Tutorials were strong secondary categories, especially for creators like Zealand and WorkTheSpace.

## Viewership Trends
* November 2019 Surge: View counts spiked in November 2019, coinciding with FM20's release. Gameplay features and Twitch streaming may have played a significant role.
* COVID-19 Impact: Although the official lockdown began in March 2020, FM content experienced a steady viewership increase starting in late 2019, likely amplified by global stay-at-home trends.

## Correlation Insights
* Moderate positive correlation between view count and like count (0.67).
* Weak correlation between view count and comment count, suggesting comments are less predictive of overall video engagement.

## Insights Deep Dive

# Repository Structure
* `data/`: Contains raw YouTube video data.
* `notebooks/`: Jupyter notebooks with all analysis and code.
* `images/`: Visualization outputs used in this README.md.
* `README.md`: This document.


