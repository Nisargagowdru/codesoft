# codesoft
# internship tasks1 # chatbot #AI
import re

def simple_chatbot(user_input):
    # Define patterns and corresponding responses
    patterns = {
        r'.*(hello|hi).*': 'Hi there! How can I help you?',
        r'.*(how are you|how are you doing).*': 'I am a chatbot, but thanks for asking!',
        r'.*(your name|who are you).*': 'I am a simple chatbot.',
        r'.*(bye|goodbye).*': 'Goodbye! Have a great day!',
        r'.*your favorite (color|food|movie).*': 'I am a bot, I do not have preferences.',
        # Add more patterns and responses as needed
    }

    # Check user input against patterns
    for pattern, response in patterns.items():
        if re.match(pattern, user_input, re.IGNORECASE):
            return response
    
    # If no match is found, provide a default response
    return "I'm sorry, I don't understand. Can you please rephrase?"

# Simple loop to run the chatbot
while True:
    user_input = input("You: ")
    if user_input.lower() == 'exit':
        print("Chatbot: Goodbye!")
        break
    response = simple_chatbot(user_input)
    print("Chatbot:", response)


