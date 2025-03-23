---
title: "[FYP] Evolution of AI-Powered Voice Interaction Robot"
description: "Final Year Project (FYP) exploring AI-driven speech recognition, real-time video analysis, and interactive robotics."
image: cover.jpg
date: 2024-11-15 10:00:00+0800
tags: 
    - AI
    - Robotics
    - NLP
    - Speech Recognition
    - Flask
    - WebSocket
    - OpenAI
    - Azure AI
    - FYP
categories:
    - School Project
    - IT
    - AI & Automation
---

# 🤖 Evolution of AI-Powered Voice Interaction Robot  
**From Telegram-based control to real-time WebSocket communication.**  

## **📌 Project Overview**  
This **Final Year Project (FYP)** focuses on developing an **AI-powered robotic assistant** that enhances **human interaction through voice communication, real-time video processing, and physical actions**.  

Between **November 2024 and March 2025**, the system underwent a significant evolution. Initially, the robot was controlled via a **Telegram bot**, allowing users to send commands remotely through a chat interface. However, in its latest iteration, the system now uses **WebSocket communication**, enabling real-time interactions between the **PC-based Python server and the robot's Python client**.

This transition has **greatly improved** response time, system stability, and expanded the range of **possible interactions**.

---

## **🛠️ System Evolution: November 2024 vs. March 2025**
| **Feature** | **November 2024 (Telegram Bot Control)** | **March 2025 (WebSocket Real-Time Communication)** |
|------------|-----------------------------------|-----------------------------------|
| **Control Method** | Users controlled the robot via **Telegram chat commands** | Users interact via **Flask-based web interface or speech** |
| **Speech Processing** | Whisper AI for STT, Azure Speech Services for TTS | Whisper AI for STT, Azure Speech Services for TTS |
| **AI Chatbot** | GPT-3.5 via OpenAI API for simple conversations | **LangChain-based chatbot** with **better context retention** |
| **Video Streaming** | Not available | **Real-time WebSocket video transmission from robot to PC** |
| **Motion Control** | Simple Telegram commands for pre-set movements | WebSocket-controlled **adaptive gesture interaction** |
| **Cloud Dependency** | Heavy reliance on Telegram servers & OpenAI API | Shift towards **local processing for improved privacy** |

---

## **🔹 Technical Implementation**
### **1️⃣ Phase 1: Telegram Bot-Based Control (November 2024)**
- Users could **send commands** via **Telegram**, and the robot would respond.
- **Predefined movement commands** (e.g., `/wave`, `/move_forward`).
- AI chatbot responses powered by **GPT-3.5 via OpenAI API**.
- **Limitations:** limited interaction capabilities, **no real-time vision processing**.
{{< youtube "5yfJXgtYdSA" >}}


### **2️⃣ Phase 2: WebSocket-Based Real-Time Control (March 2025)**
- Implemented **PC-based Flask server** for **direct interaction with the robot**.
- **WebSocket replaced Telegram API**, allowing **instant, bidirectional communication**.
- Users can now:
  - **Send text or voice commands** via a Flask-based web UI.
  - **Receive real-time responses** from the AI chatbot.
  - **Control the robot’s movements dynamically**.
  - **Stream live video from the robot’s camera** for vision-based interactions.
- **Improvements:** **better motion control**, **real-time vision processing**.
{{< youtube "lH_ZV7MhqK0" >}}
{{< youtube "0d2QBd-BcjE" >}}
---

## **🔧 System Architecture**
### **🏗️ Hardware Components**
- **TonyPi Robot** (Raspberry Pi-powered, motion-controlled)
- **Bluetooth Microphone & Speaker** for voice input/output
- **Webcam Module** for real-time vision analysis
- **PC Server** for AI processing, chatbot responses & WebSocket handling

### **🔌 Software Stack**
| **Component** | **November 2024 (Telegram-based)** | **March 2025 (WebSocket-based)** |
|--------------|---------------------------|---------------------------|
| **Speech Processing** | Whisper AI, Azure Speech | Whisper AI, Azure Speech (optimized) |
| **AI Chatbot** | OpenAI GPT-3.5 | LangChain-based GPT AI |
| **Backend Server** | Telegram Bot API | Flask + WebSocket |
| **Video Processing** | Not available | WebSocket-based real-time streaming |
| **Motion Control** | Predefined commands via Telegram | Dynamic, adaptive motion execution |
| **Cloud Integration** | Fully cloud-reliant (OpenAI, Telegram) | Shift towards **local AI processing** |

---

## **⚠️ Challenges & Solutions**
### **1️⃣ Transitioning from Telegram to WebSocket**
- **Challenge:** Migrating from a **chat-based control system** to **real-time communication**.
- **Solution:** Implemented **Flask & WebSocket** for direct robot-PC interaction.

### **2️⃣ Improving Response Time**
- **Challenge:** Telegram API caused **delays of ~2-3 seconds**.
- **Solution:** WebSocket ensures **instant data transmission (<1 second latency)**.

### **3️⃣ Adding Vision-Based Capabilities**
- **Challenge:** The Telegram bot **lacked live video processing**.
- **Solution:** Introduced **real-time camera streaming & AI-powered object recognition**.

### **4️⃣ Reducing Cloud Dependency**
- **Challenge:** Heavy reliance on OpenAI & Telegram API.
- **Solution:** Implemented **local AI processing for improved privacy & lower costs**.

---

## **🚀 Next Steps**
As the project progresses, our **main goals** include:
✅ **Further improving chatbot memory retention & real-world context awareness**.  
✅ **Enhancing gesture-based interactions for more expressive robotic responses**.  
✅ **Expanding object recognition capabilities using local AI models**.  
✅ **Exploring fully autonomous AI interactions without external cloud dependency**.  

---

## **🎬 Conclusion**
The evolution from **Telegram-based interaction (November 2024)** to a **WebSocket-powered real-time system (March 2025)** represents a major **improvement in efficiency, scalability, and user experience**.  

By shifting from **chat-based delayed control** to **real-time voice, vision, and motion-based AI interactions**, this project moves closer to creating a **fully autonomous, AI-driven companion robot**.

---

## **🔗 Related Technologies**
- **Programming Languages:** Python (Flask, OpenCV, WebSocket, LangChain)
- **AI Services:** OpenAI Whisper, GPT, Azure Speech & Vision
- **Cloud & Backend:** Flask API, Azure, WebSocket, GitHub for version control
- **Hardware:** Raspberry Pi (TonyPi), Camera Module, Bluetooth Mic & Speaker

---
