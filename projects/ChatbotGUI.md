---
layout: project
type: project
image: img/ChatbotGUI.png
title: "ChatbotGUI"
date: 2023
published: true
labels:
  - Artificial intelligence
  - GUI
  - Python
summary: "A simple Tkinter graphical user interface(GUI) based chatbot that leverages OpenAI GPT-4 to generate conversation responses"
---

ChatbotGUI is a project that combines the power of OpenAI's GPT-4 language model with a user-friendly graphical interface built using Python's Tkinter library. The application allows users to create and interact with a customizable AI-powered chatbot, providing a seamless and engaging conversational experience.

For this project, I was the sole developer responsible for designing and implementing the entire application. I started by setting up the OpenAI API integration to leverage the GPT-4 model for generating responses. From there, I developed the graphical user interface using Tkinter, creating a clean and intuitive layout for users to interact with the chatbot.

Key features of the ChatbotGUI include:

1. Customizable chatbot creation: Users can specify the characteristics of their chatbot, allowing for a personalized experience.
2. Real-time conversation: The application enables seamless back-and-forth communication between the user and the AI assistant.
3. Dark mode toggle: Users can switch between light and dark themes for comfortable viewing in different environments.
4. Scrollable chat history: The interface maintains a record of the entire conversation, allowing users to review previous interactions.

Here's a code snippet that illustrates how we send messages to the OpenAI API and receive responses:

```python
def send_message():
    message = user_input.get("1.0", tk.END).strip()
    if message:
        messages.append({"role": "user", "content": message})
        chat_box.insert(tk.END, f"User: {message}\n\n")
        user_input.delete("1.0", tk.END)
        response = openai.ChatCompletion.create(
            model="gpt-4",
            messages=messages,
        )
        reply = response["choices"][0]["message"]["content"]
        messages.append({"role": "assistant", "content": reply})
        chat_box.insert(tk.END, f"Assistant: {reply}\n\n")
```
