# Smart Document Assistant for Financial Domain

## Objective:
The project aims to build an intelligent document assistant for the financial domain, capable of performing tasks like information retrieval, text summarization, sentiment analysis, and named entity recognition (NER) for financial documents.

## Features:
- **Information Retrieval**: Use FAISS for fast document retrieval based on query input.
- **Text Summarization**: Generate concise summaries of retrieved documents using the T5 model.
- **Sentiment Analysis**: Analyze the sentiment of retrieved document summaries, providing a positive or negative sentiment.
- **Named Entity Recognition (NER)**: Extract key financial terms and entities using a BERT-based NER model.
- **Explainability**: Use LIME to explain the sentiment analysis by highlighting the key words or phrases contributing to the sentiment.

## Dataset:
- The project uses the dataset `IndianFinancialNews.csv` containing financial documents with titles and descriptions.

## There is also a report here for you to create your own model

## Workflow:
1. **Data Preprocessing**:
   - Tokenization, stop word removal, and lemmatization are performed on the text data.
2. **Information Retrieval**:
   - FAISS is used to create an index and search for top-5 relevant documents based on a query.
3. **Summarization**:
   - The T5 model is used to summarize retrieved documents.
4. **Sentiment Analysis**:
   - A sentiment analysis model is used to classify document summaries into positive or negative sentiment.
5. **NER**:
   - A pre-trained BERT model is used to extract financial terms and entities.
6. **Explainability**:
   - LIME is used to explain the sentiment prediction by identifying important contributing words/phrases.

## Requirements:
To run the project, ensure the following dependencies are installed:

### Python Packages:
- pandas
- numpy
- sentence-transformers
- faiss-cpu
- transformers
- spacy
- sklearn
- torch
- lime
- nltk

## Setup:
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/smart-document-assistant.git
   cd smart-document-assistant

2. Install required dependencies:
   pip install -r requirements.txt

3. Download and install spacy models:
   python -m spacy download en_core_web_sm

4. Download the dataset (IndianFinancialNews.csv) and place it in the project folder. ("Indian Financial News Ar􀆟cles (2003-2020) from Kaggle")

## Usage:
1. Import the functions and call search_financial_term(query) with a financial term to retrieve relevant documents.
2. The function will return a list of results, each containing the document title, summary, sentiment, and key contributions to the sentiment.
Example: 
from assistant import search_financial_term

query = "reliance"
results = search_financial_term(query)

for i, result in enumerate(results):
    print(f"Result {i + 1}:")
    print(f"Title: {result['Title']}")
    print(f"Summary: {result['Summary']}")
    print(f"Sentiment: {result['Sentiment']} (Confidence: {result['Confidence']:.2f})")
    print("Key Contributions to Sentiment:")
    for word, score in result['Contributions']:
        print(f"  {word}: {score:.2f}")

## Challenges:
1. Handling missing values in the dataset.
2. Fine-tuning models for domain-specific tasks.
3. Integration of multiple NLP tasks (retrieval, summarization, sentiment analysis, and NER) into a cohesive pipeline.

## Future Improvements:
1. Implement a more advanced retrieval system (e.g., Elasticsearch).
2. Fine-tune the models with more specific financial data.
3. Add a user-friendly web interface.

## License:
This project is licensed under the MIT License.