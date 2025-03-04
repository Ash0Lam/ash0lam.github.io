---
title: "[FYP] AI Robot Demo Showcase - Interactive Control & Speech Recognition"
description: "Demonstrating AI interactive robot capabilities through Flask control, voice commands, and vision analysis."
date: 2025-03-04 13:00:00+0800
image: cover.jpg
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

# 🎥 AI Robot Demo Showcase - Interactive Control & Speech Recognition

This article showcases different interaction methods used to control the AI-powered robot, including:
- **Flask Web Interface (Text Input & Button Control)**
- **Voice Command Execution (Motion Control, AI Chat, Q&A)**
- **Camera-based Vision Recognition & AI Analysis**

---

## **1️⃣ Flask Interface Control**
This section demonstrates how the **Flask Web Interface** is used to control the robot through **text input** and **button clicks**.

### **🔹 Text Input Command via Flask Interface**
✅ **Test Objectives**:
- Control the robot using **text input** through the Flask Web UI
- Ensure **correct movement execution** based on the commands
- Test **WebSocket real-time communication** with minimal delay

📹 **Demo Video**:
{{< video "https://drive.google.com/file/d/1srNafCRfF6LYFfBGFZVh1B1bZ-5uqomN/preview" >}}

{{< video "https://drive.google.com/file/d/1wbi7aINLB2lZS_UJs8snNqMI1oWNAZRS/preview" >}}


---

### **🔹 Button-Controlled Motion Execution via Flask Interface**
✅ **Test Objectives**:
- **Button-based control for robot movements**
- **Multiple camera angles to showcase execution**
- Test **motion precision & command response time**

📹 **Demo Video (Angle 1)**:
will upload later

---

## **2️⃣ Voice Command Control**
This section tests the **voice recognition and AI-powered command execution** capabilities, including **movement, chat interactions, and question answering**.

### **🔹 Basic Voice Command Test**
✅ **Test Objectives**:
- **Command:** "Move right once"
- **Test Whisper AI's speech recognition accuracy**
- **Evaluate execution smoothness and response time**

📹 **Demo Video**:
{{< video "https://drive.google.com/file/d/1T7k9IoVpIKucgp1NPLeaQBB6ManbqFue/preview" >}}

---

### **🔹 Multi-Step Motion Control via Voice**
✅ **Test Objectives**:
- **Command:** "Move forward three steps"
- **Test AI’s ability to execute consecutive movement steps**
- **Compare response speed from multiple angles**

📹 **Demo Video (Angle 1)**:

{{< video "https://drive.google.com/file/d/1zbT6DXdlr9vfMXRQPZ12_4pcIXEhmBB0/preview" >}}



📹 **Demo Video (Angle 2)**:

{{< video "https://drive.google.com/file/d/1QTvwJpWOKz8EfJfQ_K8IO7aQX7OUZtU-/preview" >}}


---

### **🔹 AI Chat Interaction (News Q&A)**
✅ **Test Objectives**:
- **The robot answers real-world questions based on GPT AI responses**
- **Speech recognition & conversational AI response fluidity**
- **Latency and accuracy of chatbot answers**

📹 **Demo Video (Angle 1)**:

{{< video "https://drive.google.com/file/d/13qS0KVDj_YZQYkLoG64sZzTlaw4apTh_/preview" >}}

---

### **🔹 AI Motion Execution: Dance & Greetings**
✅ **Test Objectives**:
- **Voice command:** "Dance"
- **Evaluate the fluidity of robot movements**
- **Check AI-generated motion commands execution**

📹 **Demo Video (Angle 1)**:

{{< video "https://drive.google.com/file/d/1IK4OHVocXW5KS7Rq75AnAInVFK54jDLu/preview" >}}

---

## **3️⃣ Camera-Based AI Vision Recognition**
This section tests how the robot **analyzes visual data through its camera**, recognizes objects, and responds accordingly.

### **🔹 Basic Camera Recognition Test**
✅ **Test Objectives**:
- **Live streaming from the robot's camera**
- **Testing object & environmental recognition accuracy**
- **Evaluate AI-generated responses based on video feed analysis**

📹 **Demo Video (Angle 1)**:

{{< video "https://drive.google.com/file/d/1UNCcR0X4szDm8p_6jJ70HOB3JlH6ndXR/preview" >}}


---

### **🔹 AI Vision Q&A Interaction**
✅ **Test Objectives**:
- **Robot interprets the environment and answers user queries**
- **Combines voice input & vision processing for intelligent responses**

📹 **Demo Video**:

{{< video "https://drive.google.com/file/d/10z-03NTF8952_y9WjtHo5NDfQyNYllvu/preview" >}}


---

## **🚀 Observations & Future Improvements**
### ✅ **Key Findings from Tests**
- **Flask Web Interface** → Works well with WebSocket, ensuring **real-time execution**  
- **Voice Control Tests** → **Whisper AI handles speech recognition accurately**, but **fast-spoken Cantonese can sometimes cause misinterpretation**  
- **Vision-Based Recognition** → Object detection is functional, but AI **responses could be more natural**  


### 🛠️ **Next Steps**
✅ **Add OCR (Optical Character Recognition) and QR Code Reading features**  
✅ **Optimize code to improve execution speed and reduce latency**  
✅ **Refine gesture recognition for more expressive interactions**  
