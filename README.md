To implement Speech-to-Text in Unity, you typically integrate third-party APIs or native platform support. Here's a basic guide using Unity + C# + Google Speech API (or Windows/macOS native support as alternatives).

---

✅ 1. Using Google Cloud Speech-to-Text API
🔧 Prerequisites:
Unity (2020+)

Google Cloud account

Enable Speech-to-Text API

Create a Service Account, and download the JSON key

---

🗂️ Setup:
Install Google.Cloud.Speech.V1 via NuGet or gRPC Unity SDK.

Place the service key JSON inside your Unity project (e.g., Assets/StreamingAssets/key.json).

Set environment variable in Unity:

Environment.SetEnvironmentVariable("GOOGLE_APPLICATION_CREDENTIALS", Application.streamingAssetsPath + "/key.json");
🧠 Sample Code:
csharp
Copy
Edit
using UnityEngine;
using System;
using Google.Cloud.Speech.V1;
using System.IO;

public class SpeechToText : MonoBehaviour
{
    void Start()
    {
        ConvertSpeechToText();
    }

    void ConvertSpeechToText()
    {
        var speech = SpeechClient.Create();
        var response = speech.Recognize(new RecognitionConfig()
        {
            Encoding = RecognitionConfig.Types.AudioEncoding.Linear16,
            SampleRateHertz = 16000,
            LanguageCode = "en",
        }, RecognitionAudio.FromFile("Assets/Audio/sample.wav")); // Provide recorded audio path

        foreach (var result in response.Results)
        {
            foreach (var alt in result.Alternatives)
            {
                Debug.Log($"Transcript: {alt.Transcript}");
            }
        }
    }
}

----

✅ 2. Platform-Specific Options
🗣️ Windows (via System.Speech.Recognition)
Works in .NET Framework on Windows:

using System.Speech.Recognition;

SpeechRecognitionEngine recognizer = new SpeechRecognitionEngine();
recognizer.LoadGrammar(new DictationGrammar());
recognizer.SetInputToDefaultAudioDevice();
recognizer.SpeechRecognized += (s, e) => {
    Debug.Log("Recognized: " + e.Result.Text);
};
recognizer.RecognizeAsync(RecognizeMode.Multiple);

---

🎙️ Android & iOS (via Plugin)
Use plugins like:

Android Speech Plugin

[iOS SiriKit (via native bridge)]

🔌 Recommended Plugins (Unity Asset Store)
Speech Recognizer Plugin (Android/iOS)

Azure Cognitive Services for Unity

RT-Voice or SALSA LipSync (for voice input + animation)

----

📝 Notes
Unity Microphone API (Microphone.Start) can be used to record audio before sending to APIs.

Consider user permission handling for mobile.

Handle latency and network issues gracefully.
