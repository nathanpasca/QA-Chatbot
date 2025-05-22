# NLP Question-Answering Chatbot
A Python-based question-answering (QA) chatbot leveraging the `distilbert-base-cased-distilled-squad` model from Hugging Face's Transformers library. This project was developed as part of a Natural Language Processing course assignment to demonstrate natural language processing (NLP) techniques for answering questions based on a given context.

## Prerequisites
Before running this system, make sure you have:
- Python 3.9+
- A working internet connection to download the pre-trained model and tokenizer
- Required Python libraries (listed below)

## Installation
1. Clone the repository:
```bash
git clone https://github.com/nathanpasca/nlp-qa-chatbot
cd nlp-qa-chatbot
```

2. Install dependencies:
```bash
pip install transformers torch nltk
```

3. Download required NLTK data:
- The script automatically downloads the `punkt` and `punkt_tab` NLTK packages when run for the first time.

## Usage
Run the script:
```bash
python3 nlp_chatbot.py
```

The system will:
- Load the `distilbert-base-cased-distilled-squad` model and tokenizer for question answering
- Use a predefined context about NLP (included in the script) to answer user questions
- Support pronoun resolution to handle questions with pronouns (e.g., "What does it do?") by referencing previous interactions
- Maintain a short memory of up to 5 previous question-answer pairs for context-aware responses

Example interaction:
```
NLP QA Chatbot (type 'exit' to quit)

You: What is NLP?
Bot: Natural Language Processing

You: What does it do?
(Resolving pronouns: 'What does it do?' → 'What does Natural Language Processing do?')
Bot: returns a precise answer drawn from a given context or dataset

You: Give examples of NLP applications
Bot: machine translation systems like Google Translate

You: exit
Goodbye
```

## Note
- The chatbot uses a predefined context about NLP. To use a different context, modify the `context` variable in the script or provide a file path to a custom context file.
- Pronoun resolution is basic and relies on the last 3 interactions to identify relevant entities. It may not handle complex pronoun references accurately.
- The system is designed for single-turn or simple multi-turn conversations. For production use, additional dialogue management and error handling may be needed.

## Academic Disclaimer
This project was developed as part of an academic assignment in Machine Learning. While it demonstrates NLP question-answering concepts, it may require additional features, robustness, and optimization for production use.

## Acknowledgments
- [Hugging Face Transformers](https://huggingface.co/transformers/)
- [NLTK](https://www.nltk.org/)
- [PyTorch](https://pytorch.org/)
