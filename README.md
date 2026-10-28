# Peri Chatbot

A Turkish-language retrieval-based chatbot for a cafe information use case. The application matches user queries against a local knowledge base using TF-IDF vectors and cosine similarity.

## Overview

The project demonstrates a text-processing pipeline that converts Turkish input into a searchable representation and retrieves a predefined response. It runs locally through a command-line interface.

## Processing Pipeline

1. Load question-response pairs from `veriler.json`.
2. Normalize text, tokenize input and remove Turkish stopwords.
3. Apply Turkish stemming with Snowball.
4. Build TF-IDF vectors with Scikit-learn.
5. Rank stored queries by cosine similarity and return the corresponding response.

## Technology Stack

Python · NLTK · Scikit-learn · NumPy · Snowball Stemmer

## Setup

```bash
git clone https://github.com/ceylanumit/peri-chatbot.git
cd peri-chatbot
python -m venv .venv
```

Activate the virtual environment, then install the dependencies:

```bash
python -m pip install nltk scikit-learn numpy snowballstemmer
python -m nltk.downloader punkt punkt_tab stopwords
```

Keep `veriler.json` in the same working directory as `main.py`. The JSON file contains records with `user_input` and `bot_response` fields.

## Usage

```bash
python main.py
```

Enter a Turkish query at the prompt. Use `Ctrl+C` to end the session.

## Example

![Peri Chatbot command-line interface](ornek.png)

## Current Scope

Responses are retrieved from the supplied dataset rather than generated. The current implementation returns the closest match even when similarity is below the configured threshold.
