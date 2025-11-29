# 🌐 Translator App [EnglishToTelugu]

A simple Android application that uses **Google ML Kit Translation API** to translate text from **English → Telugu**.

---

## ✨ Features
- Input text in English  
- Translate instantly to Telugu  
- Automatic model download  
- Error handling for model download and translation failures  

---

## 📂 Project Structure
com.example.translatorapp
 
├── MainActivity.java              
├── res    
├── layout/activity_main.xml   # UI layout    
├── values/strings.xml         # App strings    
├── values/styles.xml          # App themes


---

## 🛠️ Tech Stack
- **Language:** Java  
- **Framework:** Android SDK  
- **Library:** Google ML Kit Translation (`com.google.mlkit:translate`)  
- **UI:** XML layouts  

---

## 🚀 How It Works
1. **Initialize Translator**
   ```
   TranslatorOptions options = new TranslatorOptions.Builder()
       .setSourceLanguage(TranslateLanguage.ENGLISH)
       .setTargetLanguage(TranslateLanguage.TELUGU)
       .build();
   translator = Translation.getClient(options);
2. **Download Model (Wi-Fi required also downloads at first time)**
```
DownloadConditions conditions = new DownloadConditions.Builder()
    .requireWifi()
    .build();
translator.downloadModelIfNeeded(conditions)
    .addOnSuccessListener(unused -> {
        // Model ready for translation
    })
    .addOnFailureListener(e -> {
        // Handle download failure
    });
```
3. **Translate Text**
```translator.translate(inputText)
    .addOnSuccessListener(translatedText -> outputTextView.setText(translatedText))
    .addOnFailureListener(e -> outputTextView.setText("Translation failed: " + e.getMessage()));
```

 


## 📦 APK
The latest APK is available in the Release section.



## 📸 Screenshots
![Results Screen](images/result.png) 


## ⚡ Future Enhancements
- Support for multiple languages  
- Voice input & speech translation   
- Save translated history 



## 🧑‍💻 Author
Developed by **Poorna** 
 
Developed and explored **Android Studio**, and submitted this project as the course-end project for the Mobile Application Lab gained insights in app development.

---


