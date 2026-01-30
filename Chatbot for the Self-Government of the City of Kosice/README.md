# Chatbot for the City of Kosice

This repository contains an AI chatbot created for the city self-government of Košice.  
The chatbot was developed using the **Rasa framework** and **Python** and serves as an automated assistant that provides citizens with information related to municipal services and the city administration.

The project was created as part of **academic bachelor’s thesis work**.

Authors:
- Martin Šarišský
- Matej Ščišľak

---

## Project Description

The main purpose of this project is to demonstrate how conversational artificial intelligence can be used in public administration.  
The chatbot communicates with users in natural language and responds to predefined questions using trained language models and dialogue logic.

The chatbot runs as a backend service and can be accessed through a simple web-based interface.

---

## Used Technologies

The project was built using the following technologies:

- **Rasa** – open-source framework for building conversational AI (NLU and dialogue management)
- **Python** – backend language used for chatbot logic and model training
- **HTML** – simple web interface for user interaction
- **JavaScript** – communication between the web interface and the chatbot backend
- **REST API** – message exchange between frontend and backend
- **YAML** – configuration and training data format
- **Docker** – containerization and deployment support

---

## How It Works

1. The user communicates with the chatbot through a web browser.
2. Messages are sent to the Rasa backend using a REST API.
3. Rasa processes the input using Natural Language Understanding (NLU).
4. Based on trained intents, stories, and rules, the chatbot generates a response.
5. The response is returned to the user in the web interface.

---

## Project Structure

```text
.
├── data/
│   ├── nlu.yml        # Intents and training examples
│   ├── stories.yml    # Conversation flows
│   └── rules.yml      # Dialogue rules
├── domain.yml         # Responses, intents, and entities
├── config.yml         # Rasa pipeline configuration
├── endpoints.yml     # API endpoints
├── credentials.yml   # Channel configuration
├── Dockerfile        # Docker setup
├── index.html        # Web-based chat interface
└── README.md         # Project documentation
