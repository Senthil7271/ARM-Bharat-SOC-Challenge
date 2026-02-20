<p align="center">
  <img src="assets/processor-animation.svg" width="600"/>
</p>

<p align="center">
  <img src="assets/title-animation.svg" width="900"/>
</p>

A fully offline, ARM-optimized speech-to-speech (S2S) translation system designed for mobile devices.  
The system performs real-time Speech-to-Text (STT), semantic translation, and Text-to-Speech (TTS) entirely on-device without any cloud dependency.

---

## 🚀 Features

- 🎤 Speech-to-Text using Whisper-Tiny
- 🌍 Semantic Translation using MarianMT
- 🔊 Text-to-Speech using Piper Neural TTS
- ⚡ Chunk-based streaming inference for reduced latency
- 🧠 INT8 quantized models for memory efficiency
- 🏎️ ARM NEON SIMD optimized inference
- 🔒 Fully offline execution (No cloud / No API calls)

---

## 🏗️ System Architecture


Microphone
↓
AudioRecord (16kHz PCM)
↓
Chunk Manager (1s window, 200ms overlap)
↓
Log-Mel Feature Extraction
↓
Whisper-Tiny (INT8, TFLite)
↓
MarianMT (INT8, ONNX Runtime)
↓
Piper TTS (INT8, ONNX)
↓
AudioTrack Playback
↓
Speaker


All processing runs locally on ARM CPU with NEON acceleration.

---

## 🧠 Models Used

| Component | Model | Optimization |
|------------|--------|--------------|
| STT | Whisper-Tiny | INT8 Quantized (TFLite) |
| Translation | MarianMT | INT8 Quantized (ONNX) |
| TTS | Piper | INT8 Quantized (ONNX) |

---

## ⚙️ Optimization Techniques

- INT8 Post-Training Quantization
- NEON SIMD Accelerated GEMM
- XNNPACK Backend (TFLite)
- ONNX Runtime Mobile (ARM CPU Execution Provider)
- Chunk-Based Streaming Inference
- Reduced Beam Width for STT
- Sequence Length Limiting for Translation

---

## 📱 Hardware Requirements

- ARMv8.2-A based smartphone
- NEON SIMD support
- Android 12+
- Minimum 6GB RAM recommended

---

## 🛠️ Software Stack

- Android Studio
- TensorFlow Lite
- ONNX Runtime Mobile
- Kotlin / Java
- ARM NEON optimized backend

---

## 📊 Performance Metrics

| Metric | Value |
|---------|--------|
| End-to-End Latency | ~1.3 seconds |
| Memory Reduction (FP32 → INT8) | ~67% |
| Average CPU Usage | ~60% |
| Max Device Temperature | ~41°C |
| Cloud Dependency | None |

---

## 🔒 Offline Validation

- No INTERNET permission required
- All models stored locally in assets
- Verified in airplane mode
- No external API calls



## 🧪 How to Run

1. Clone the repository:


git clone https://github.com/Senthil7271/ARM-Bharat-SOC-Challenge.git


2. Open in Android Studio
3. Build and run on ARM-based device
4. Grant microphone permission
5. Start speaking 🎤

---

## 🎯 Key Contributions

- Fully offline transformer-based speech-to-speech pipeline
- ARM NEON optimized execution
- Mobile-efficient INT8 deployment
- Real-time chunk-based streaming implementation

---

## 📌 Future Improvements

- SME2 optimization support
- NPU acceleration
- Dynamic quantization tuning
- Multi-language support expansion

---

## 📄 License

This project is for research and educational purposes.

---

## 👨‍💻 Author

Your Name  
Electronics Engineering (VLSI Design)  
ARM-Optimized Edge AI Research
