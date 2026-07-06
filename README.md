# 📷 Real-Time Face Recognition System (C++ / OpenCV / TVM)

## 🧠 Overview

This project is a real-time face detection and recognition system implemented in C++.

It processes live video streams and performs:
- face detection
- facial landmark alignment
- feature extraction (face embeddings)
- identity matching using cosine similarity

The system is optimized for CPU real-time performance using TVM.

---

## ⚙️ System Pipeline

The recognition pipeline follows a 4-stage process:

> Detection → Alignment → Embedding Extraction → Matching

---

## 🔍 Face Detection

- RetinaFace (TVM optimized)
- Fast-MTCNN (optional alternative)

Outputs:
- bounding box (x, y, w, h)
- 5 facial landmarks

Purpose:
> Locate and localize faces in real-time video input

---

## 🧬 Face Recognition

- MobileFaceNet / ArcFace backbone
- 112×112 aligned face input
- 128-dimensional embedding vector output

Each face is represented as a numerical identity vector in embedding space.

---

## 📊 Matching Strategy

Identity verification is performed using cosine similarity:

- High similarity → same identity
- Low similarity → different identity

---

## ⚡ Performance Optimization

- TVM compiler used for inference optimization
- CPU real-time execution (no GPU required)
- ~20–50 FPS depending on configuration

---

## 🧱 Tech Stack

- C++
- OpenCV
- Apache TVM
- RetinaFace
- ArcFace / MobileFaceNet

---

## 🚀 Key Features

- real-time webcam face detection
- facial landmark alignment
- face verification via embeddings
- CPU-optimized inference pipeline
- modular detection/recognition architecture

---

## 🧠 Design Principles

- separation of detection and recognition stages
- lightweight inference pipeline
- embedding-based identity representation
- CPU-first optimization strategy

---

## ▶️ Build & Run

```bash
mkdir build
cd build
cmake ..
make -j4
./FaceRecognitionCpp
