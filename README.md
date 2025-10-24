# Multi-Turn-Intent-Classification

# Setup and Run Instructions

    * Install the requirements.txt
    * Run the Multi_Turn_Intent_Classifier.ipynb 
    * Upload conversations.json

# Explanation of model choice

    * Used model is Gemma 2 (google/gemma-2-2b-it)
    * It handles multi-turn conversations effectively using prompt-based classification.
    * Selected because it balances accuracy and speed

# Sample predictions

    * The input conversations are provided in conversations.json, and the corresponding predictions are saved as predicted_intents.json and predicted_intents.csv. One example is given below.

    * Input  

        {
            "conversation_id": "conv_001",
            "messages": [
                {"sender": "user", "text": "Hi, I'm looking for a 2BHK in Dubai"},
                {"sender": "agent", "text": "Great! Any specific area in mind?"},
                {"sender": "user", "text": "Preferably Marina or JVC"},
                {"sender": "agent", "text": "What's your budget?"},
                {"sender": "user", "text": "Max 120k. Can we do a site visit this week?"}
            ]
        }

    * Output

        JSON -{
            "conversation_id": "conv_001",
            "predicted_intent": "Book Appointment",
            "rationale": "The user requested a site visit after discussing budget and location."
            }

        CSV -conversation_id,predicted_intent,rationale
            conv_001,Book Appointment,"The user requested a site visit after discussing budget and location."

    
# Any limitations or edge cases

    * The truncation limit must be manually adjusted; for long conversations, the value of N should be high.

    * The model can predict only one intent, even if multiple intents are present in the conversation.

    * The system requires a GPU or high-memory CPU for efficient inference.

    * Occasionally, the model may fail to predict an intent on the first run, but predicting again usually works.

    * Hugging Face authentication is required to access the model.

    * The model performs best with English-language conversations.

           





