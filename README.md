# Face Authentication (Face Verification) – Task 2

## 📌 Overview
---
# 🔐 Face Authentication System

This project builds a **Face Authentication system** using Python and FastAPI.
Its purpose is to determine whether two given face images belong to the **same individual**.

The system carries out the following steps:

* Detects faces in images
* Extracts facial features (embeddings)
* Measures similarity between faces
* Provides a final verification result

---

## 🚀 Key Features

* Accepts two input face images
* Detects faces in both inputs
* Generates embeddings using InsightFace (ArcFace model)
* Calculates similarity using cosine similarity
* Returns:

  * Verification result (**same person / different person**)
  * Similarity score
  * Bounding boxes of detected faces

---

## 🧠 Technology Stack

* Python
* FastAPI
* InsightFace (pretrained model)
* OpenCV
* NumPy
* Scikit-learn

---

## 📂 Project Structure

```
face-auth/
│
├── train.py          # Model initialization/setup
├── test.py           # Prediction & verification logic
├── app.py            # FastAPI backend service
├── requirements.txt
├── README.md
```

---

## ⚙️ Installation

Install dependencies using:

```bash
pip install -r requirements.txt
---

## ▶️ Running the Application

### Step 1: Start FastAPI Server

```bash
uvicorn app:app --reload
```

### Step 2: Open API Documentation

```
http://127.0.0.1:8000/docs
```

### Step 3: Test the API

* Use the `/verify/` endpoint
* Upload two face images
* View the verification result

---

## 📥 Sample API Response

```json
{
  "verification_result": "same person",
  "similarity_score": 0.78,
  "face1_bbox": [120, 80, 300, 350],
  "face2_bbox": [100, 60, 280, 330]
}
```

---

## 📌 Working Process

1. **Face Detection**

   * Identifies faces in both images using InsightFace

2. **Feature Extraction**

   * Converts detected faces into numerical embeddings

3. **Similarity Measurement**

   * Computes cosine similarity between embeddings

4. **Final Decision**

   * If similarity > 0.5 → same person
   * Otherwise → different person

---

## 📁 File Overview

### train.py

* Loads and initializes the pretrained InsightFace model
* Serves as the model setup stage

### test.py

* Handles:

  * Model loading
  * Face embedding extraction
  * Verification logic

### app.py

* Implements FastAPI endpoints
* Accepts image inputs
* Returns prediction results

---

## 📊 Model Details

* Model: InsightFace (buffalo_l)
* Based on ArcFace embeddings
* Pretrained (no additional training required)

---

## 🧪 Additional Notes

* Only the first detected face is considered
* Similarity threshold is set to **0.5** (adjustable)
* Runs on CPU (GPU support optional)

---

## 🎯 Submission Checklist

* [x] train.py
* [x] test.py
* [x] FastAPI implementation
* [x] requirements.txt
* [x] README.md
* [x] Sample images (optional)

---

## 💡 Future Enhancements

* Support for multiple faces
* Improved face alignment
* Integration with a database (face login system)
* Liveness detection (anti-spoofing)
* GPU acceleration
---
## 👤 Author

Batthini Anugna
