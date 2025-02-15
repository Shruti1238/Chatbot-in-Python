# Building a Modern Python Chatbot with NLTK
*A journey from ELIZA to your own AI companion*

![Alt text](https://cdn-images-1.medium.com/max/800/1*pPcVfZ7i-gLMabUol3zezA.gif)

## Overview
In 1966, Joseph Weizenbaum created ELIZA - a groundbreaking chatbot that simulated a psychotherapist using just 200 lines of code. Today, we'll honor that legacy by building our own modern chatbot using Python and NLTK. While our bot won't compete with ChatGPT, it's an excellent introduction to Natural Language Processing (NLP) fundamentals and chatbot architecture.

## Project Goals
- Create a functional chatbot using modern Python practices
- Learn core NLP concepts through hands-on development
- Build a foundation for more advanced conversational AI projects

## Technical Requirements

### Core Dependencies
```bash
pip install nltk pandas scikit-learn
```

### NLTK Resources
```python
import nltk
nltk.download([
    'punkt',
    'wordnet',
    'averaged_perceptron_tagger',
    'popular'
])
```

## Project Structure
```
modern-chatbot/
├── src/
│   ├── chatbot.py
│   ├── preprocessor.py
│   └── responses.py
├── data/
│   └── training_data.json
├── tests/
│   └── test_chatbot.py
└── requirements.txt
```

## Implementation Guide

### 1. Natural Language Processing Pipeline
- Tokenization: Breaking input into meaningful units
- Lemmatization: Converting words to their base form
- Part-of-speech tagging: Understanding word contexts
- Pattern matching: Identifying user intent

### 2. Response Generation
- Rule-based responses using pattern matching
- Context tracking for more natural conversations
- Fallback responses for unknown inputs

### 3. Running the Bot
```python
from src.chatbot import ModernChatbot

bot = ModernChatbot()
bot.train()

while True:
    user_input = input("You: ")
    if user_input.lower() == 'quit':
        break
    response = bot.get_response(user_input)
    print(f"Bot: {response}")
```

## Advanced Features

### Sentiment Analysis
```python
from textblob import TextBlob

def analyze_sentiment(text):
    analysis = TextBlob(text)
    return analysis.sentiment.polarity
```

### Context Management
```python
class ConversationContext:
    def __init__(self):
        self.current_topic = None
        self.user_sentiment = 0
        self.conversation_history = []
```

## Best Practices

1. **Error Handling**
   - Graceful handling of unexpected inputs
   - Meaningful error messages
   - Logging for debugging

2. **Code Organization**
   - Modular design
   - Clear separation of concerns
   - Comprehensive documentation

3. **Testing**
   - Unit tests for core functionality
   - Integration tests for the complete system
   - Regular validation of responses

## Future Enhancements

1. **Machine Learning Integration**
   - Training on conversation datasets
   - Dynamic response generation
   - Personalization based on user interaction

2. **API Integration**
   - Weather updates
   - News headlines
   - Knowledge base queries

3. **Voice Interface**
   - Speech-to-text integration
   - Text-to-speech output
   - Voice emotion detection

   
## How to run
* Jupyter Notebook [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/parulnith/Building-a-Simple-Chatbot-in-Python-using-NLTK/master)

You can run the [chatbot.ipynb](https://github.com/parulnith/Building-a-Simple-Chatbot-in-Python-using-NLTK/blob/master/Chatbot.ipynb) which also includes step by step instructions.
* Through Terminal
```
python chatbot.py
```


## Contributing
We welcome contributions! Please check our contribution guidelines and feel free to submit pull requests.

## License
This project is licensed under the MIT License - see the LICENSE file for details.
