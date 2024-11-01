
# README

## Project Overview
The goal of this project is to clean comment data, perform sentiment analysis, and analyze the data in conjunction with post information. We used `SnowNLP` for sentiment classification and applied merging, analysis, and visualization on the cleaned comment data.

## File List

1. **cleaned_comments.csv**
   - **Description**: This file contains the cleaned comment data, with emojis, URLs, parentheses, and their contents removed. Using regular expressions, unnecessary characters are eliminated to retain the core comment information.
   - **Main Fields**:
     - `comment_id`: Unique identifier for the comment.
     - `content`: Cleaned comment content.
     - `create_time`: Creation timestamp of the comment.
     - `user_id`: Unique identifier of the comment user.
     - `nickname`: User's nickname.
     - `liked_count`: Number of likes.
     - `note_id`: Corresponding post ID.

2. **comments.csv**
   - **Description**: The raw comment data file containing user-posted comments and related information.
   - **Main Fields**:
     - `comment_id`: Unique identifier for the comment.
     - `content`: Raw comment content.
     - `create_time`: Creation time of the comment.
     - `user_id`: Unique identifier of the comment user.
     - `nickname`: User's nickname.
     - `liked_count`: Number of likes.
     - `note_id`: Corresponding post ID.

3. **contents.csv**
   - **Description**: The post data file, which contains posts and related statistics.
   - **Main Fields**:
     - `note_id`: Unique identifier for the post.
     - `type`: Type of post.
     - `liked_count`: Number of likes on the post.
     - `comment_count`: Number of comments on the post.
     - `title`: Title of the post.
     - `last_modify_ts`: Last modification timestamp of the post.

4. **sentiment_analysis_results.csv**
   - **Description**: This file contains sentiment analysis results based on the cleaned comments, along with merged post data.
   - **Main Fields**:
     - `note_id`: Unique identifier for the post.
     - `content`: Cleaned comment content.
     - `sentiment_class`: Sentiment classification using `SnowNLP`, labeled as "positive," "neutral," or "negative."
     - `create_time`: Creation time of the comment.
     - `type`: Type of post.
     - `liked_count`: Number of likes on the post or comment.
     - `comment_count`: Number of comments on the post.

5. **snownlp.ipynb**
   - **Description**: This Jupyter Notebook file contains code for sentiment analysis and data cleaning used in the project. The Notebook uses `SnowNLP` for sentiment analysis on comments and performs further analysis by merging with post data.
   - **Main Functions**:
     - Comment Data Cleaning: Removes emojis, URLs, parentheses, and other unnecessary information.
     - Sentiment Analysis: Uses the `SnowNLP` library to classify comment sentiment.
     - Data Merging and Analysis: Merges cleaned comment data with post data, and provides visualizations and statistical analyses of sentiment classifications.

## Usage Steps

1. **Environment Setup**:
   - Install the required Python libraries:
     ```bash
     pip install pandas snownlp matplotlib
     ```

2. **Run Analysis Code**:
   - Open `snownlp.ipynb` and run the code steps provided in the Notebook. This will:
     - Load `cleaned_comments.csv` and `contents.csv`.
     - Perform sentiment analysis on the comment content and merge with post data.
     - Generate `sentiment_analysis_results.csv` for further analysis.

3. **Data Analysis**:
   - Use the Notebook or other tools to conduct additional statistical analysis or visualization on `sentiment_analysis_results.csv`, such as examining the distribution of comment sentiment, or analyzing the relationship between likes and sentiment.

## References  
- [SnowNLP Documentation](https://github.com/isnowfy/snownlp)
