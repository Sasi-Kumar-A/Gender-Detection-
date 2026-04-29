# 🎤 Voice Gender Detection

A machine learning web application that detects gender (Male/Female) from voice input — either by uploading an audio file or recording directly in the browser.

Built with **Flask**, **Librosa**, **Scikit-learn**, and a sleek animated glassmorphism UI.

---

## 🚀 Demo

> Upload a `.wav` or `.mp3` file — or record your voice live — and get an instant gender prediction.

---

## 📸 Screenshots

<img width="1915" height="913" alt="Gender Detection" src="https://github.com/user-attachments/assets/8e098e7e-bb47-4730-b04f-b45ce0bd6f74" />


---

## 🧠 How It Works

1. **Audio is captured** via file upload or live browser recording.
2. **Features are extracted** from the audio using `librosa`:
   - **MFCCs** (20 coefficients) — captures the tonal quality of the voice
   - **Chroma STFT** (12 features) — captures pitch-related information
   - **Zero Crossing Rate** — measures how often the signal changes sign
   - **Spectral Centroid** — captures the "brightness" of sound
3. **Features are scaled** using a pre-fitted `StandardScaler`.
4. **A trained ML classifier** predicts: `Male (0)` or `Female (1)`.

---

## 🗂️ Project Structure

```
gender-detection/
│
├── app.py                  # Flask backend — routing, feature extraction, prediction
├── templates/
│   └── index.html          # Frontend UI — file upload + live recording + waveform
├── static/
│   └── last_audio.wav      # Saved audio for playback after prediction
├── gender_model.pkl        # Trained ML model
├── scaler.pkl              # Fitted StandardScaler
└── requirements.txt        # Python dependencies
```

---

## 🏋️ Model Training

The model was trained on a small custom dataset:

| Class  | Samples |
|--------|---------|
| Male   | 11      |
| Female | 11      |

> **Note:** This is a minimal proof-of-concept dataset. For production-level accuracy, training on a larger and more diverse dataset (e.g., [Common Voice](https://commonvoice.mozilla.org/)) is strongly recommended.

**Features used for training (35 total):**
- 20 MFCCs
- 12 Chroma features
- 1 Zero Crossing Rate
- 1 Spectral Centroid
- 1 Spectral Rolloff *(if included)*

---

## 🛠️ Tech Stack

| Layer      | Technology                          |
|------------|--------------------------------------|
| Backend    | Python, Flask                        |
| ML         | Scikit-learn, Joblib                 |
| Audio DSP  | Librosa, SoundFile, PyDub            |
| Frontend   | HTML5, CSS3, Vanilla JavaScript      |
| UI Style   | Glassmorphism, CSS Animations        |
| Audio API  | Web MediaRecorder API (live record)  |

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/gender-detection.git
cd gender-detection
```

### 2. Create a Virtual Environment (recommended)

```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Requirements

```
flask
librosa
numpy
scikit-learn
joblib
soundfile
pydub
```

> Also make sure **FFmpeg** is installed on your system (required by PyDub):
> - **Ubuntu/Debian:** `sudo apt install ffmpeg`
> - **macOS:** `brew install ffmpeg`
> - **Windows:** [Download FFmpeg](https://ffmpeg.org/download.html) and add to PATH

### 5. Run the App

```bash
python app.py
```

Visit `http://127.0.0.1:5000` in your browser.

---

## 🎙️ Features

- 📁 **File Upload** — Supports `.wav` and `.mp3` formats
- 🎤 **Live Recording** — Record voice directly in the browser with one click
- 📊 **Real-time Waveform** — Animated audio waveform visualizer during recording
- 🔊 **Audio Playback** — Listen to your recorded/uploaded audio before and after prediction
- ✨ **Glassmorphism UI** — Animated gradient background with frosted-glass card design
- ⚡ **Instant Prediction** — Result displayed immediately after submission

---

## 📈 Future Improvements

- [ ] Train on a larger, more diverse dataset for better accuracy
- [ ] Add confidence scores to predictions
- [ ] Support real-time streaming gender detection
- [ ] Deploy to cloud (Render / Hugging Face Spaces / Railway)
- [ ] Add multi-language support
- [ ] Show feature importance / explainability chart

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👤 Author

**Sasi Kumar**
- GitHub: ([https://github.com/your-username](https://github.com/Sasi-Kumar-A))
- LinkedIn: [[your-linkedin](https://linkedin.com/in/your-profile)](https://www.linkedin.com/in/sasi-kumar-a--/)

---

> ⭐ If you found this project helpful, please give it a star!
