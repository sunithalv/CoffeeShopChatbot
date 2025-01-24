# Coffee Shop Chatbot

This project builds an AI-powered Agent based chatbot to enhance customer experiences in a coffee shop app. Leveraging the power of LLMs (Large Language models), Natural Language Processing (NLP), and RunPod's infrastructure, this chatbot can assist with taking orders, answering detailed menu queries, and providing personalized product recommendations—all within a React Native mobile app.The chatbot can:
* Have real-time customer interactions and assist customers in placing orders. 
* Provide details on the items in the menu including ingredients and allergens using **RAG**.
* Provide personalized product recommendations through **Market basket analysis** powered recommendations.

## React Native Coffee Shop App
![Screenshot_20250123-193016_Expo Go](https://github.com/user-attachments/assets/efc22085-6315-4ea2-b06c-e1ccd8c342ce)
     ![Screenshot_20250123-193452_Expo Go](https://github.com/user-attachments/assets/2135afca-8387-4021-86e1-1c0deb378208)
     ![Screenshot_20250123-193512_Expo Go](https://github.com/user-attachments/assets/1876e1dc-d974-47a2-b09f-9ffcf649bf9c)     ![Screenshot_20250123-193518_Expo Go](https://github.com/user-attachments/assets/0cc8b3ae-2b86-44ae-8b49-905e517138c4)

The React Native Coffee Shop App serves as the front-end interface for customers to interact with the AI-powered chatbot and explore the menu. The app integrates the chatbot for real-time customer service, enabling users to place orders, receive personalized product recommendations, and get detailed information about menu items.There is also provision for user to place order manually from the home page.

### Key Features:
* **Home Page:** Displays featured menu items and product categories.User can filter different categories of items and view them accordingly.
* **Item Details Page:** Provides detailed descriptions for each item.
* **Cart Page:** Allows users to review and modify their order before checkout.
* **Chatbot Interface:** Enables customers to interact with an AI chatbot for order assistance, recommendations, and order related queries.
  
## Tech used:
* **LLM** : Llama 3.1 Instruct via RunPod
* **Embeddings LLM**: Embeddings LLM via Runpod
* **API endpoint**: Agent-based system with specialized agents like Order Taking, Details, and Guard agents in Runpod.
* **Vector Database**: Pinecone vector database for storing coffee shop menu and product information.
* **Storage Database** : Google Firebase database to store the menu details and images required for react native app.
* **React Native app** : Mobile based app for the chatbot

## Chatbot Agent Architecture
![chatbot_agent_architecture](https://github.com/user-attachments/assets/c3c9ec42-af56-495f-b56e-6d5a4a573528)

The chatbot in this project is designed using a modular agent-based architecture, where each agent is responsible for a specific task, ensuring a seamless and efficient interaction between the user and the coffee shop’s services. This architecture enables the chatbot to perform complex actions by delegating tasks to specialized agents, making the system highly flexible, scalable, and easy to extend.

### Key Agents in the System:
1. **Guard Agent:**
This agent monitors all incoming user queries and ensures that only relevant and safe messages are processed by the other agents.
2. **Classification Agent:**
It classifies incoming user queries and determines which agent is best suited to handle the task. By categorizing user intents, it ensures that queries are routed efficiently, whether the user is asking for recommendations, placing an order, or inquiring about specific menu details.
4. **Order Taking Agent:**
This agent is responsible for guiding customers through the order placement process. It uses chain-of-thought prompt engineering to simulate human-like reasoning, ensuring the order is accurately structured and all customer preferences are captured.
4. **Recommendation Agent:**
This agent handles personalized product recommendations by working with the market basket recommendation engine. Triggered by the Order Taking Agent, it analyzes the user's current order or preferences and suggests complementary items. 
5. **Details Agent (RAG System):**
Powered by a Retrieval-Augmented Generation (RAG) system, the Details Agent answers specific customer questions about the coffee shop, including menu details, ingredients, allergens, and other frequently asked questions. It retrieves relevant data stored in the vector database(Pinecone) and combines it with LLM capabilities to provide clear and precise responses.

# Directory Structure
```bash
├── coffee_shop_customer_service_chatbot
│   ├── coffee_shop_app_folder # Contains React Native app code   
│   ├── python_code
│       ├── API/               # Chatbot API for agent-based system
│       ├── dataset/           # Dataset for training recommendation engine    
│       ├── products/          # Product data (names, prices, descriptions, images)   
│       ├── build_vector_database.ipynb             # Builds vector database for RAG model   
│       ├── firebase_uploader.ipynb                 # Uploads products to Firebase    
│       ├── recommendation_engine_training.ipynb    # Trains recommendation engine 
```
