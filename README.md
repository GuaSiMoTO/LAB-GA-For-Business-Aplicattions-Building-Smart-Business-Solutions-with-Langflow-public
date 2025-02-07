# LAB-GA-For-Business-Aplicattions-Building-Smart-Business-Solutions-with-Langflow

![Langflow Logo](https://user-images.githubusercontent.com/970858/63474771-d6734700-c469-11e9-83bb-9429da563909.png)

## Initial Setup

### Requirements

1. Fork and clone the provided GitHub repository into your workspace.
2. Install the required libraries listed in the `requirements.txt` file.
3. Ensure you have **Ollama** and langflow installed and running locally.

## Introduction

Welcome to the **Virtual Assistant with Langflow** lab. In this exercise, you will use Langflow’s visual interface to design an interactive virtual assistant that retains conversation context. 

You will learn how to connect nodes to capture user input, store dialogue history, process data files, and generate personalized responses using a language model. This hands-on approach will help you understand how different components integrate to build a robust and adaptable conversational system.

---

### Iteration 1: Setting Up Langflow

1. Launch Langflow and access the interface in your browser.
2. Start a new project to design the virtual assistant.

---

### Iteration 2: Adding Chat Input and Memory

1. Add a **Chat Input** node to capture user queries, which will serve as the entry point for interactions.
2. Add a **Memory** node to store conversation history. Configure it to retain recent exchanges or summarize longer conversations.
3. Connect the **Chat Input** node to the **Memory** node to pass user queries through the memory.

---
### Iteration 3: Adding File Input and Parsing Data

1. Add a **File** node in **Data** component to allow the assistant to load the `book_store.json` file. 
   - Configure the **File** node to accept `.json` files.

2. Add a **Parse Data** node in **Processing** component to process the JSON file.
   - Configure the node to extract and format the list of books from the JSON file.
   - The extracted data should be in a format that can be passed as input to the **Prompt Template** node.

3. Connect the **File** node to the **Parse Data** node to enable the file content to be processed and parsed.

---

### Iteration 4: Adding a Prompt Template

1. Add a **Prompt Template** node to organize the assistant's behavior and responses.
2. Configure the prompt to include:
   - The user's current query.
   - The conversation history stored in memory.
   - The parsed book data from the `book_store.json` file.
3. Connect the **Chat Input** and **Memory** nodes to the **Prompt Template** node.

```
You are a helpful virtual assistant for an online bookstore. Use the following conversation history, the user's current query, and the list of available books to provide accurate and concise responses. If the user asks for book recommendations, suggest books based on previous genres mentioned.
Available Books: {book_store}
Conversation History: {history}
User Message: {user_message}
AI:
```

---

### Iteration 5: Connecting the Model and Chat Output

1. Add a **Model Node** to process the prompt and generate responses using an Ollama model.
  - Model Name: Use a supported model, such as llama3 or any custom model installed in your Ollama setup.
  - Temperature: Adjust for creative (>0.7) or deterministic (~0.1) outputs.
3. Add a **Chat Output** node to display the assistant's response to the user.
4. Connect the **Prompt Template** node to the **Model Node** and the **Model Node** to the **Chat Output** node.

---

### Iteration 6: Testing the Langflow Assistant

1. Test the flow by interacting with the assistant through the **Chat Input** node.
2. Verify that the assistant retains context and provides personalized, accurate responses based on previous exchanges.

---

### Iteration 7: Build a RAG for a book assistant 


Build a book assistant that uses **Qdrant** to store book synopses and retrieve relevant information through vector search.

#### 1. Preparing the Book Dataset

**Searching or Generating Data:**

- **Option A:** Search for a dataset in repositories like Kaggle.
- **Option B:** Generate synopses with AI (e.g., ChatGPT or GPT-4) for 30+ popular books.

**Example of Synopsis (JSON Format):**

```json
[
    {
        "title": "Dune",
        "synopsis": "In a distant future, the struggle for control of the desert planet Arrakis is at the center of a complex political and ecological plot."
    },
    {
        "title": "Neuromancer",
        "synopsis": "A hacker ventures into cyberspace and faces powerful corporations in a dystopian world."
    }
]
```

#### 2. Add the Books to Qdrant

#### 3. Design the RAG Flow in Langflow

#### 4. Testing and Validation

- Run the flow in Langflow.
- Test queries such as:
  - *"Recommend me a book with a futuristic setting."*
  - "What is the plot of Dune?"

---

## Submission

1. Push your completed Langflow JSON file script to your GitHub repository.
2. Create a Pull Request with a description of your implementations.

---

## Additional Resources

- [Langflow Documentation](https://docs.langflow.com/)

![Happy Coding](https://user-images.githubusercontent.com/970858/63899010-c23fc480-c9ea-11e9-84a2-542907e42362.png)

