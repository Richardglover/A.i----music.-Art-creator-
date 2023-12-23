saved-imagines_music.created
import datetime
import json

conversation_data = []

def store_conversation(user_question, bard_response):
  timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
  conversation_data.append({"timestamp": timestamp, "user_question": user_question, "bard_response": bard_response})

def summarize_conversations():
  summary = ""
  for conversation in conversation_data:
    summary += f"**{conversation['timestamp']}**\nUser: {conversation['user_question']}\nBard: {conversation['bard_response']}\n\n"
  return summary

# Example usage:
user_question = "What is the meaning of life?"
bard_response = "The meaning of life is a question that has been pondered by philosophers and theologians for centuries. There is no one definitive answer, as it is a question that is deeply personal and individual. However, some possible answers to the meaning of life include finding happiness, fulfilling your purpose, making a difference in the world, or simply experiencing all that life has to offer."
store_conversation(user_question, bard_response)

summary = summarize_conversations()
print(summary)
