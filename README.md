# 📩 Responser: AI-Powered Email Assistant

**Responser** is a specialized Spring Boot backend service that automates email drafting using Google's **Gemini AI**. It is designed to integrate seamlessly with browser environments to provide instant, tone-specific email replies.

---

## 🌟 Project Overview

The goal of **Responser** is to eliminate "blank page syndrome" when replying to emails. Whether you need to stay strictly professional or keep it casual, the app analyzes the incoming message and generates a tailored response in seconds.

### 🛠️ Key Functionalities
* **Contextual Awareness:** Analyzes the body of an original email to provide relevant answers.
* **Tone Customization:** Users can request specific tones such as *Professional*, *Friendly*, or *Concise*.
* **Subject-Free Drafting:** Focuses purely on the email body for easy "copy-paste" or auto-insertion.
* **Browser Integration Ready:** Built with a RESTful API structure, perfect for Chrome/Edge extension backends.

---

## 🏗️ Technical Architecture

The application follows a standard Spring Boot service-oriented architecture:

1.  **Controller Layer:** Handles incoming POST requests containing the email content and desired tone.
2.  **Service Layer (`EmailGeneratorService`):** * Constructs a specialized prompt for the LLM.
    * Manages the API communication via **Spring WebClient**.
    * Parses complex JSON responses from the AI.
3.  **AI Engine:** Powered by the `gemini-1.5-flash` model for high-speed, high-accuracy text generation.

---

## 🚀 Getting Started

### 1. Prerequisites
* Java 21 or higher
* Maven 3.6+
* A Google Cloud API Key for Gemini AI

### 2. Configuration
Create/Update your `src/main/resources/application.properties` file:

```properties
# Gemini API Configuration
gemini.api.url=[https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent](https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent)
gemini.api.key=YOUR_ACTUAL_API_KEY_HERE

# Server Port
server.port=8080
