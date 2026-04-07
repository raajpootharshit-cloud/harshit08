# harshit08

import nltk
from textblob import TextBlob
nltk.download('punkt')
user_name = ""
def  get_sentiment(text):
    analysis = TextBlob(text)
    polarity = analysis.sentiment.polarity
    if polarity > 0 :
        return "happy"
    elif polarity < 0 :
        return "sad"
    else :
        return "neutral"
print("HELLO! What is your name")
user_name = input("you : ")
print(f" chatbot: nice to meet you , {user_name}" )

while True:
    user_input = input(f"{user_name}:").lower()

    if "bye" in user_input:
        print(f"chatbot:sayonara{user_name}")
        break
    elif user_input in ["hi" , "yo"," kaise ho", "kyaa hall"]:
        print(f"chatbot:hello{user_name}, how are you")
    else :
        mood = get_sentiment(user_input)

        if mood == "happy":
            print(f"chatbot:achha lgaa sun k")
        elif mood == "sad":
            print(f"chatbot:ohh soryy what happened{user_name}, no woory cz i am here")
        else:
            print(f"chatbot:i see {user_name} tell me more")

