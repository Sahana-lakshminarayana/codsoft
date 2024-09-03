import re

# Define a dictionary of rules and corresponding responses
reply_rules = {
    r'\bhello|hi|hey\b': 'Hello! How can I assist you today?',
    r'\bwhat\'s your favorite color\b': 'As a bot, I don’t have preferences, but I think blue is calming!',
    r'\bdo you like music\b': 'I don’t have ears, but I appreciate all kinds of music!',
    r'\bwhat\'s the weather like\b': 'I can’t check the weather directly, but I can help you find out!',
    r'\bdo you know any fun facts\b': 'Did you know that honey never spoils? Archaeologists have found pots of honey in ancient Egyptian tombs that are over 3,000 years old and still edible!',
    r'\bwhat do you think about AI\b': 'AI is an incredible field with vast potential to improve many aspects of our lives!',
    r'\bwhat\'s the best programming language\b': 'It depends on what you’re trying to achieve! Python is versatile, Java is robust, and JavaScript is great for web development.',
    r'\bcan you recommend a movie\b': 'The movie Chak De India is really good',
    r'\bhow do you work\b': 'I process your questions and respond based on patterns and data available to me.',
    r'\bthanks\b': 'You’re welcome! If you have any other questions, feel free to ask!',
}

# Function to find a matching pattern and return the appropriate response
def generate_response(user_message):
    user_message = user_message.lower()
    for regex_pattern, bot_reply in reply_rules.items():
        if re.search(regex_pattern, user_message):
            return bot_reply
    return "I’m not sure I understand. Could you please ask something else?"

# Chatbot's main loop
print("Chatbot: Hi there! I'm ChatAssistant. Feel free to ask me anything.")
while True:
    user_message = input("You: ")
    if user_message.lower() == 'exit':
        print("Chatbot: Goodbye! Have a great day!")
        break
    bot_response = generate_response(user_message)
    print("Chatbot:", bot_response)