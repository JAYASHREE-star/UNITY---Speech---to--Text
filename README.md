# 🎤 Unity - Speech to Text Recognition System

This Unity project enables **real-time voice-to-text transcription**, allowing users to speak through a microphone and see their words appear as text on screen. It is perfect for accessibility, voice-controlled applications, in-game chat systems, and educational tools.

## 🚀 Key Features

- 🎙️ Real-time speech recognition
- 📄 Transcribes spoken words to on-screen text
- 🖥️ Works with Unity’s built-in microphone support
- 🔁 Optional integration with Google Cloud or Windows Dictation APIs
- 🔧 Modular and easy to extend or embed in other Unity projects

## 🛠️ Technologies Used

- **Unity Engine** (Recommended: 2019.4+ or later)
- **C#** scripting
- Unity Microphone API / Windows DictationRecognizer
- Optional: Google Cloud Speech-to-Text (for advanced usage)

## 📂 Project Structure

```
/UnitySpeechToText
│
├── Assets/
│   ├── Scripts/
│   │   └── SpeechToText.cs         # Main logic for recording and recognition
│   ├── UI/
│   │   └── TranscriptDisplay.cs    # Displays transcribed text
│   ├── Prefabs/
│   ├── Audio/
│   └── Scenes/
│       └── MainScene.unity         # Main test scene
└── README.md
```

## 🧪 How to Run

1. Clone or download the repository.
2. Open the project with **Unity Hub**.
3. Open `MainScene.unity` inside `Assets/Scenes`.
4. Press the **Play** button in Unity Editor.
5. Click the **Start Listening** button in the UI.
6. Speak into your microphone—your words will appear on screen.

## 💡 Supported Options

| Mode                    | Description                             | Dependency              |
|-------------------------|-----------------------------------------|--------------------------|
| Unity Microphone API    | Basic recording, manual transcription   | Built-in                 |
| Windows Dictation API   | Native speech-to-text on Windows        | UnityEngine.Windows.Speech |
| Google Cloud Speech API | Accurate, multilingual support          | Requires Google setup    |

## 🔒 Permissions

- ✅ Requires microphone access
- ❌ No data is stored or sent externally (unless using cloud APIs)

## 🚧 Future Enhancements

- Multilingual support
- Hotword detection (e.g., “Hey Unity”)
- Voice command trigger system
- Transcript saving as .txt/.pdf
- Mobile platform integration (iOS/Android)

## 🙌 Credits

- Unity Documentation  
- Microsoft Speech SDK  
- Google Cloud Speech-to-Text (if used)

## 📃 License

MIT License 
