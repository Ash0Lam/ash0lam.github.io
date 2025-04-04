---
title: "[FYP] Multilingual Intelligent Robot Project - Final Version and Feature Summary"
description: "Final version of the AI robot project featuring multilingual interface, real-time conversation flow, and WhatsApp-styled UI implementation."
date: 2025-03-26 00:00:00+0800
draft: false
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
    - Multilingual
categories:
    - School Project
    - IT
    - AI & Automation
---

# 🤖 Multilingual Intelligent Robot Project - Final Version and Feature Summary

This is the final update for our AI robot project, where we've implemented several significant enhancements and completed the system's fundamental architecture. This article details the major improvements since our last demonstration, focusing on the completely redesigned user interface, multilingual support, and real-time conversation flow functionality.

---

## 🆕 Overview of Key New Features

Compared to our previous demonstration, we've made substantial improvements in the following areas:

1. **All-New WhatsApp-Style Interface** - Transformed the original Bootstrap interface into a more intuitive, engaging chat-style design
2. **Multilingual Support System** - Complete English-Chinese bilingual support with automatic language detection and one-click switching
3. **Real-Time Voice Conversation Flow** - New "Phone Mode" supporting continuous, uninterrupted dialogue without manual triggering
4. **Enhanced Camera Vision Analysis** - Improved environmental understanding and object recognition capabilities
5. **Testing Tools Panel** - Built-in testing functionality for development and diagnostics

---

## ✨ UI Transformation: From Standard Bootstrap to WhatsApp Style

The project initially used a standard Bootstrap interface that, while functional, lacked the intuitiveness of modern messaging applications. In the final version, we completely redesigned the user interface, adopting a WhatsApp-inspired design language.

### 🎨 Design Comparison

**Original Design vs. Final Design:**

| Design Element | Old Version | New Version |
|---------------|------------|------------|
| Color Scheme | Default Bootstrap blue theme | WhatsApp-style green-focused palette |
| Message Bubbles | Rectangular text boxes | Rounded message bubbles with clear sender/receiver distinction |
| Layout | Form-oriented | Conversation-oriented, focused on message flow |
| Component Design | Standard buttons and forms | Custom chat elements and interactive components |

```css
:root {
    --chat-primary: #128C7E;  /* WhatsApp signature green */
    --chat-light: #DCF8C6;    /* Sent message background */
    --chat-dark: #075E54;     /* Header bar background */
    --chat-received: #f0f0f0; /* Received message background */
}

.message-content {
    padding: 10px 15px;
    border-radius: 10px;
    box-shadow: 0 1px 2px rgba(0,0,0,0.1);
    position: relative;
    word-break: break-word;
}

.sent {
    margin-left: auto;
    background-color: var(--chat-light);
}

.received {
    margin-right: auto;
    background-color: var(--chat-received);
}
```

### 📱 Responsive Design and User Experience Optimization

The new interface has been optimized for both desktop and mobile devices, ensuring a consistent experience across different screen sizes. We paid particular attention to:

- Auto-expanding message input area
- Accessibility of real-time voice input buttons
- Camera window display and hide transitions
- Automatic scrolling to the latest messages

---

## 🌐 Multilingual Support System Implementation

### 🔄 Google Translate Integration

One of the most significant new features is the multilingual support system implemented through Google Translate. Users can now seamlessly switch between English, Traditional Chinese, and Simplified Chinese with a simple dropdown interface.

```html
<!-- Google Translate Element -->
<div id="google_translate_element"></div>
<script type="text/javascript">
function googleTranslateElementInit() {
  new google.translate.TranslateElement({
    pageLanguage: 'zh-HK',
    includedLanguages: 'en,zh-TW,zh-CN', // Limited language options
    layout: google.translate.TranslateElement.InlineLayout.SIMPLE
  }, 'google_translate_element');
}
</script>
<script type="text/javascript" src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>
```

### 🌍 Key Benefits of Google Translate Integration

The Google Translate integration offers several advantages:

- **Simplified Implementation**: Leverages Google's established translation infrastructure
- **Multiple Language Support**: Easy to extend beyond just English and Chinese
- **Automatic Language Detection**: Detects user's preferred language
- **Universal Translation**: Translates all UI elements automatically without manual tagging
- **Maintenance Efficiency**: Updates to translation quality happen automatically via Google's service

### 🔍 Practical Application

By implementing Google Translate, we've eliminated the need for:
- Manual tagging of UI elements with language-specific classes
- Custom language switching logic
- Local storage of language preferences

This approach significantly reduced development time while providing a more robust translation system that can easily be extended to additional languages in the future.

The translate widget is strategically positioned in the interface to ensure accessibility without interfering with the primary chat functionality, maintaining the clean WhatsApp-inspired design.

---

## 📞 Real-Time Voice Conversation Flow: Phone Mode

### 🎙️ Continuous Dialogue Experience

The new "Phone Mode" radically changes how users interact with the robot. Instead of pressing the microphone button each time to initiate a conversation, users can now talk continuously as they would in a real phone call.

```javascript
function startPhoneMode() {
    isPhoneModeActive = true;
    phoneModeContainer.classList.add('active');
    startTimer();
    socket.emit('start_phone_mode');
    
    // UI update
    phoneButton.classList.add('phone-mode-active');
}
```

### ⏱️ Voice Activity Detection and Automatic Capture

The system can now intelligently detect voice activity, interpreting silent periods as natural pauses in conversation:

```python
def _recording_worker(self):
    # ... Initialize recording device ...
    
    silence_count = 0
    has_detected_speech = False
    max_silence_frames = int(self.rate / self.chunk * 5)  # End after 5 seconds of silence
    
    while self.is_recording:
        data = stream.read(self.chunk)
        
        if self.vad.is_speech(data, self.rate):
            silence_count = 0
            has_detected_speech = True
            self.frames.append(data)
        else:
            silence_count += 1
            
        # If 5 seconds of silence after detecting speech, end recording and process
        if has_detected_speech and silence_count > max_silence_frames:
            break
```

### 🔄 Continuous Dialogue Processing Flow

Conversation processing in Phone Mode follows a closed loop:

1. Voice detection → Recording starts
2. Speech recognition processing (using Whisper or Azure)
3. Semantic understanding and AI response generation
4. Text-to-speech response
5. Continue listening for the next voice input

---

## 👁️ Enhanced Vision Analysis

### 🖼️ Real-Time Environmental Understanding

We've improved the camera analysis functionality to:

- More precisely identify objects and people
- Describe scenes more naturally in both Cantonese and English
- Automatically execute appropriate actions based on recognition results (such as waving when a person is seen)

### 📊 Integrated Testing Tools

To improve development and testing efficiency, we've added a dedicated testing panel that allows individual testing of audio recognition and visual analysis features.

```html
<div id="test-panel" class="sidebar-card mb-3">
    <div class="sidebar-header">
        <h5 class="mb-0 fs-6">
            <i class="fas fa-flask me-2"></i>
            <span class="lang-zh">測試工具</span>
            <span class="lang-en">Testing Tools</span>
        </h5>
    </div>
    <div class="p-3">
        <!-- Audio testing area -->
        <h6 class="mb-3">
            <i class="fas fa-headphones me-2"></i>
            <span class="lang-zh">語音識別測試</span>
            <span class="lang-en">Voice Recognition Test</span>
        </h6>
        <!-- Image testing area -->
        <div class="mt-4 border-top pt-3">
            <h6 class="mb-3">
                <i class="fas fa-image me-2"></i>
                <span class="lang-zh">圖片視覺分析測試</span>
                <span class="lang-en">Image Analysis Test</span>
            </h6>
        </div>
    </div>
</div>
```

---

## 💻 Technical Improvements and Architectural Optimization

### 🔧 Whisper Speech Recognition Options

Users can now choose between using a local Whisper model or Azure cloud service for speech recognition, each with its own advantages:

- **Local Whisper**: Low latency, no need to connect to cloud services
- **Azure Speech Services**: Higher accuracy, especially for Cantonese recognition

### 🌐 WebSocket Communication Optimization

The WebSocket communication layer has been restructured to more effectively handle multiple event types:

```python
@socketio.on('robot_vad_audio')
def handle_robot_vad_audio(data):
    """Handle speech detected by robot VAD"""
    if not phone_mode_active:
        return
    
    try:
        # Receive audio data from robot
        audio_data = data.get('audio_data')
        if not audio_data:
            return
        
        # Notify frontend that speech was detected
        emit('phone_mode_speech_detected', broadcast=True)
        
        # ... Process speech and generate response ...
    except Exception as e:
        logging.error(f"Error processing phone mode speech: {e}")
```
---

## **Final Showcase**


{{< video "https://drive.google.com/file/d/1WlXS9QX2EHoyak3nE5Yp2ec18uR86-3m/preview" >}}

---

## 🏁 Project Conclusion and Future Outlook

### 📝 Completed Features List

✅ **Multi-modal Control**: Text, buttons, voice, and visual analysis
✅ **Bilingual User Interface**: Complete English and Chinese support
✅ **Real-time Conversation Flow**: Continuous interaction in phone mode
✅ **WhatsApp-style UI**: Modern, intuitive chat interface
✅ **Extended Action Library**: Basic movements, martial arts, and performance actions
✅ **Cloud/Local Hybrid Computing**: Flexible processing mode selection

### 🛑 Project Status: Completed

This version marks the official completion of the project. All planned core functionality has been implemented, and the system has achieved its intended design goals. **No new features will be added, and non-critical bugs will not be fixed.**

### 🔮 Potential Future Development Directions

Although the project is officially concluded, if there's an opportunity to expand in the future, some potential areas for improvement include:

- Further optimization of local speech recognition models
- Expansion of multilingual support (adding more languages)
- Improvement of motion control algorithms for more complex actions
- Strengthening security mechanisms, especially for remote control functionality

---

## 🙏 Acknowledgments

Finally, heartfelt thanks to everyone who participated in and supported this project. Special appreciation goes to our supervisors for their guidance, and to all those whose efforts helped bring this project to life.

---

## 📌 Personal Reflection on the FYP Experience
Throughout this project, I encountered many challenges not only in technical implementation but also in team dynamics and institutional processes.

As someone who relied heavily on self-learning, experimentation, and AI-assisted development (e.g., GPT and Claude), I realized that current academic structures may not fully recognize individual contributions in group projects—especially when group members' effort levels vary greatly.

This experience taught me the value of visibility, communication, and the ability to stand up for one's work, even when the system seems indifferent.

In the future, I hope institutions can explore fairer assessment methods, such as peer-coded contributions, development logs, or clearer responsibility tracking.

Despite these frustrations, I’m grateful for what this project taught me—not just about code, but about resilience and self-worth.

---

*This article is published as the final documentation for the [VTC IT114115 AY24/25 2A-A05 Group] robot project. For any questions or to learn more details, please contact us through [Ash Lam](https://ash0lam.github.io/).*