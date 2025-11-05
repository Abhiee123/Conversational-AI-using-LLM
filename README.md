<h1 align="center"> AI Doctor with Vision and Voice</h1><p align="center">
  <i>A multimodal AI medical assistant that can listen, see, analyze, and speak — simulating a doctor-patient interaction using speech, vision, and language models.</i></p>

---

## 🧩 Project Overview

This project integrates **speech recognition**, **image analysis**, and **text-to-speech** technologies to build an intelligent AI assistant that acts like a doctor.
The user can **speak their symptoms**, **upload a medical image**, and receive a **spoken diagnosis** — all through a single interface.

By combining **Groq’s Whisper & LLaMA Vision models**, **Google Text-to-Speech**, and **Gradio**, this project demonstrates a practical use of **multimodal AI** in healthcare simulation.

---

## 🧠 System Architecture

Patient (Voice + Image)
↓
🎙️ **Voice of Patient** (Speech-to-Text via Groq Whisper)
↓
🧠 **Brain of Doctor** (Image + Query → Diagnosis using Groq LLaMA Vision)
↓
🗣️ **Voice of Doctor** (Text-to-Speech via gTTS)
↓
Doctor’s Spoken Response

---

## 🎯 Objective

To develop a **virtual doctor assistant** capable of:
* Understanding patient speech (symptom description)
* Analyzing uploaded medical images
* Responding like a human doctor using natural, empathetic language
* Speaking back the response to the patient

---

## ⚙️ Key Features

✅ **Speech-to-Text:** Converts patient’s voice into text using Groq Whisper (`whisper-large-v3`)
✅ **Vision Analysis:** Analyzes uploaded medical images using Groq LLaMA 3.2 Vision Model
✅ **Text-to-Speech:** Generates lifelike voice responses using Google TTS (`gTTS`)
✅ **Human-Like Output:** Answers formatted as if a real doctor is speaking
✅ **Gradio Interface:** Clean, easy-to-use UI for voice and image input

---

## 🧰 Tech Stack

| Component | Tool / Library |
| :--- | :--- |
| **Language** | Python |
| **Framework** | Gradio |
| **Speech-to-Text** | Groq Whisper Large V3 |
| **Image Analysis** | Groq LLaMA 3.2 Vision |
| **Text-to-Speech** | Google gTTS |
| **Audio Processing** | Pydub |
| **Recording** | SpeechRecognition |
| **Environment Management** | Pipenv |
| **Deployment** | Localhost / Cloud-ready |

---

## 🧠 Modules Explanation

### 1️⃣ `voice_of_patient.py` – Voice to Text
* Records user voice input using **SpeechRecognition**.
* Converts `.wav` audio to text using **Groq Whisper Large V3**.
* Handles noise adjustment and logging.

### 2️⃣ `brain_of_doctor.py` – Vision + Query Understanding
* Encodes the uploaded medical image to Base64.
* Sends the image + query text to Groq LLaMA Vision model.
* Generates a short, human-like diagnostic statement.
* The AI prompt ensures:
    > “Speak like a real doctor — concise, direct, and empathetic, without mentioning that you’re an AI.”

### 3️⃣ `voice_of_doctor.py` – Text to Speech
* Uses Google Text-to-Speech (gTTS) to convert doctor’s response into natural voice.
* Automatically saves and plays `.mp3` or `.wav` output.
* Cross-platform compatible for Windows, macOS, and Linux.

### 4️⃣ `gradio_app.py` – User Interface
* Brings all modules together into a single Gradio-based web app.
* Includes three main tabs:
    * **Predict:** Speak and upload image for diagnosis.
    * **Bulk Predict:** (Optional extension) Handle batch predictions.
    * **Model Info:** Display instructions and model details.

---



