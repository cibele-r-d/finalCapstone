# Sentiment Analysis and Sentence Similarity

This Python script performs sentiment analysis and computes sentence similarity using spaCy and TextBlob libraries. The script takes a Pandas DataFrame containing text data and operates on the 'reviews.text' column, assuming it contains textual reviews.

## Dependencies
- Python 3.x
- spaCy
- pandas
- TextBlob

## Usage
1. Ensure you have installed the required dependencies.
2. Provide a CSV file containing text data with a column named 'reviews.text'. Make sure the file is accessible to the script.
3. Run the script.

## Functions
### `analyze_sentiment(text)`
- Analyzes sentiment of the given text using TextBlob.
- Returns a tuple of polarity and subjectivity.

### `sentimental_and_similarity(dataframe)`
- Analyzes sentiment and computes similarity of sentences in the given DataFrame.
- Prints out sentiment analysis and sentence similarity for each sentence.

## Example
```python
import spacy
import pandas as pd
from textblob import TextBlob

# Function definitions...

try:
    amazon_dataframe = pd.read_csv("amazon_product_reviews.csv").dropna(subset=["reviews.text"])
except FileNotFoundError:
    print("Error: File not found.")
except pd.errors.ParserError:
    print("Error: Invalid file format.")

sentimental_and_similarity(amazon_dataframe["reviews.text"].sample(n=5))

print(f"Dataframe Columns: {amazon_dataframe.shape[1]} Rows: {amazon_dataframe.shape[0]}")
