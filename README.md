# NLP MIT Quiz - Context-Based QA Chatbot with Memory

This project implements a context-based Question Answering Chatbot with conversation memory as required for the NLP MIT Quiz. The chatbot uses Hugging Face's Transformers library to provide answers based on a given context document.

## Features

✅ **Basic QA Function** - Takes a question and context, returns the best answer found in the context
✅ **Interactive Chatbot** - Provides a user interface to interact with the chatbot in a loop
✅ **Conversation Memory** - Stores previous interactions and resolves pronoun references

## Requirements

- Python 3.7+
- Transformers
- PyTorch
- NLTK

## Installation

1. Install the required packages:

```
pip install transformers torch nltk
```

## How to Run

1. Save the provided Python code to a file named `qa_chatbot.py`
2. Download the context document and save it to your local machine
3. Update the code to use your local file path or paste the context directly into the code
4. Run the script:

```
python qa_chatbot.py
```

## Usage

1. When prompted, enter your questions about the document
2. The chatbot will provide answers based on the context
3. You can use pronouns (it, they, that) to refer to previously mentioned entities
4. Type 'exit' to quit the program
5. Type 'clear' to reset the conversation memory

## Implementation Details

### Part 1: Basic QA Function

The `answer_question()` function:
- Takes a question (string) and the context
- Uses a pre-trained QA model from HuggingFace Transformers
- Returns the best answer found in the context

### Part 2: Chatbot Interaction Layer

The `run_chatbot()` function:
- Prompts the user for input in a loop
- Answers questions based on the loaded context
- Provides an option to exit by typing 'exit'

### Part 3: Chatbot with Memory (40 points)

The `resolve_pronouns()` function:
- Implements conversation memory using a list of dictionaries
- Detects pronoun references (it, they, that model, etc.)
- Resolves them based on previous conversation turns

## Example Interactions

```
Welcome to the Context-Based QA Chatbot with Memory!
==================================================
• Ask questions about the document
• The chatbot can remember previous questions
• Type 'exit' to quit
• Type 'clear' to clear conversation memory
==================================================

You: What is the main topic of this document?
Bot: [Answer based on context]

You: Who created it?
(Resolving pronouns: 'Who created it?' → 'Who created document?')
Bot: [Answer based on context with pronoun resolution]
```
