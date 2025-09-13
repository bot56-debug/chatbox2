import webbrowser
import datetime

def chatbot_response(chatbox):
    chatbox = chatbox.lower()

    match True:
        case _ if "hello" in chatbox or "hi" in chatbox:
            return "Hello!\nHow can I help you today?"
        
        case _ if "your name" in chatbox:
            return "I'm DOOM,\nyour friendly Python chatbot!"   
        
        case _ if "how are you" in chatbox:
            return "I'm just a bunch of code,\nbut I'm doing great!"
        
        case _ if "time" in chatbox:
            now = datetime.datetime.now().strftime("%H:%M:%S")
            return f"The current time is {now}"
        
        case _ if "date" in chatbox:
            today = datetime.date.today().strftime("%B %d, %Y")
            return f"Today's date is {today}"
        
        case _ if "take me to google" in chatbox or "open google" in chatbox:
            webbrowser.open("https://www.google.com")
            return "Opening Google..."
        
        case _ if "take me to youtube" in chatbox or "open youtube" in chatbox:
            webbrowser.open("https://www.youtube.com")
            return "Opening YouTube..."
        
        case _ if "open instagram" in chatbox:
            webbrowser.open("https://www.instagram.com")
            return "Opening Instagram..."
        
        case _ if "open github" in chatbox:
            webbrowser.open("https://www.github.com")
            return "Opening GitHub..."
        
        case _ if "open chatgpt" in chatbox or "take me to chatgpt" in chatbox:
            webbrowser.open("https://chat.openai.com")
            return "Opening ChatGPT..."
        
        case _ if "search" in chatbox:
            query = chatbox.replace("search", "").strip()
            if query:
                webbrowser.open(f"https://www.google.com/search?q={query}")
                return f"Searching Google for: {query}"
            else:
                return "What would you like me to search for?"
        
        case _ if "youtube search" in chatbox:
            query = chatbox.replace("youtube search", "").strip()
            if query:
                webbrowser.open(f"https://www.youtube.com/results?search_query={query}")
                return f"Searching YouTube for: {query}"
            else:
                return "What would you like me to search on YouTube?"
       
     
    
        case _ if "thanks" in chatbox or "thank you" in chatbox: 
         return "You're welcome!"
        
        case _ if "bye" in chatbox:
            return "Goodbye! Have a great day!"
        
    
    print("DOOM: Hello! \n(Type 'bye' to exit.)")
while True:
    chatbox = input("You: ")
    response = chatbot_response(chatbox)
    print("DOOM:", response)
    if "bye" in chatbox.lower():
        break
