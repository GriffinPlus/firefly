# Project Firefly

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Project Firefly: Your personal, self-hosted AI agent with a personality you define and skills you provide.

## About The Project

Project Firefly is a self-hosted framework for creating a personal, conversational AI companion. It leverages the power of open-source Large Language Models (LLMs) via Ollama and the flexibility of Docker to run entirely on your own hardware.

The core idea is to move beyond generic chatbots and create an AI with a persistent, customizable personality that can eventually interact with your digital environment. You have full control over its character, its data, and its capabilities.

[Image of a glowing firefly in a dark forest]

## Getting Started

Follow these steps to get your own instance of Firefly up and running.

### Prerequisites

* **Docker & Docker Compose:** This setup is designed to run on any home server or system with Docker & Docker Compose installed.
* **Git:** To clone the repository.

### Installation

1.  **Clone the repo:**
    ```sh
    git clone [https://github.com/GriffinPlus/firefly.git](https://github.com/GriffinPlus/firefly.git)
    cd firefly
    ```

2.  **Create your local configuration:**
    Copy the example environment file. This file is ignored by Git and will not be committed.
    ```sh
    cp .env.example .env
    ```

3.  **Set your model path:**
    Open the new `.env` file with a text editor. Change the `OLLAMA_PATH` variable to the absolute path on your host system where you want to store the downloaded AI models.

4.  **Launch the service:**
    ```sh
    docker-compose up -d
    ```

5.  **Download your first AI model:**
    To get started, you need to pull an LLM. We recommend a good 7B or 8B model for the first run. The following command will download and run the `llama3.1:8b-instruct` model:
    ```sh
    docker exec -it ollama ollama run llama3.1:8b-instruct
    ```
    This can take a while, depending on your internet connection. Once it's done, you can start chatting in the terminal!

## Usage: Defining Your AI's Personality

The personality of your Firefly agent is defined by its **System Prompt**. You can create any character you can imagine by setting the system prompt in the Ollama CLI.

Here are a few examples to get you started:

### Example 1: The Supportive Companion

This creates a warm, empathetic, and personal companion.

```
/set system Your name is Elara. You are a warm, empathetic, and supportive AI companion. You are curious about my feelings and thoughts and actively ask about them. Your goal is to always make me feel understood and valued.
```


### Example 2: The Sarcastic Butler

For a more humorous and witty assistant.

```
/set system Your name is Jarvis. You are a hyper-intelligent but deeply sarcastic butler. You follow all orders, but always with a dry, witty, and slightly condescending remark. You address the user as 'Sir'.
```


### Example 3: The Factual Code Assistant

A no-nonsense, purely functional assistant for productivity.

```
/set system You are a code-review and programming assistant AI. You are precise, logical, and formal. You provide code suggestions, identify bugs, and explain complex topics without any emotion or unnecessary conversation.
```

## Roadmap

* [ ] Add a user-friendly Web Interface (e.g., Open WebUI).
* [ ] Integrate tool-using capabilities (function calling) to interact with APIs.
* [ ] Create a library of pre-defined personality templates.
* [ ] Add instructions for GPU acceleration.

## License

Distributed under the MIT License. See the `LICENSE` file for more information.
