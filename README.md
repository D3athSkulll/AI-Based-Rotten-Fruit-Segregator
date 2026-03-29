# AI-Based Rotten Fruit Detection and Segregation

An **AI + Embedded Systems project** focused on reducing food wastage by automatically detecting and segregating rotten fruits in real time.

Developed as part of the **Environmental Engineering Science (EES)** course at
**ABV-Indian Institute of Information Technology Management, Gwalior**

---

## Team

| Roll Number | Name             | Contribution                     |
| ----------- | ---------------- | -------------------------------- |
| 2023IMT-073 | Shivam Deolankar | Hardware Integration, Research   |
| 2023IMT-082 | Sumit Chintanwar | Software for Segregation         |
| 2023IMT-083 | Taksh Patel      | Model Training & Data Processing |
| 2023IMT-084 | Udit Shrivastava | Detection Model Development      |
| 2023IMT-087 | Yash Wani        | Hardware Development             |

---

## 🌍 Problem Statement

In real-world agricultural supply chains, a significant portion of fruits is lost due to **late or inaccurate detection of spoilage**. Manual sorting is:

* Slow and labor-intensive
* Prone to human error
* Difficult to scale

This approach answers the question :

> *Can we build a low-cost system that automatically identifies and separates rotten fruits in real time?*

This project is our attempt to answer that using **AI + Computer Vision + Embedded Systems**.

---

## 🚀 System Design

At a high level, the system:

1. **Captures an image of the fruit**
2. Uses a **deep learning model** to classify it as *fresh* or *rotten*
3. Sends the result to an **Arduino**
4. The Arduino controls a **servo motor** to physically segregate the fruit

---

## 🧠 Working Procedure

### Step 1: Image Processing & Prediction

An image is passed through a trained CNN model that learns features like:

* Color changes (dark spots, discoloration)
* Texture differences
* Shape/morphological irregularities

```
Input Image → Preprocessing → CNN Model → Prediction
```

---

### Step 2: Decision Logic

The system then evaluates:

* Is this actually a fruit?
* If yes → Is it rotten?

---

### Step 3: Hardware Action

Based on the prediction:

* 🟢 Fresh → Servo rotates towards *fresh bin*
* 🔴 Rotten → Servo rotates towards *rotten bin*

```
Prediction → Serial Communication → Arduino → Servo Motor → Segregation
```

---

## ⚙️ Tech Stack

This project combines multiple domains:

### 🧠 AI / Machine Learning

* TensorFlow
* Keras
* CNN-based classification (MobileNetV2-inspired)

### 👁️ Computer Vision

* OpenCV (real-time image capture and preprocessing)

### 🔌 Hardware Communication

* PySerial (Python ↔ Arduino communication)

### ⚡ Embedded Systems

* Arduino Uno / Pro Micro
* Servo Motor control

### 📊 Data & Visualization

* NumPy
* Pandas
* Matplotlib

---

## 📁 Project Structure

```
EES-Project/
│
├── motor/                 # Arduino code for controlling servo motor
├── FV.h5                  # Model for detecting whether object is a fruit
├── rotten.h5              # Model for classifying fruit as fresh/rotten
├── rottentest.py          # Main script (AI + hardware integration)
├── test.png               # Sample input image
├── ProjectReport.pdf      # Full project documentation
├── README.md              # You are here :)
```

---

## 🧪 Models Used

We used deep learning models trained on fruit datasets:

### 1. Fruit Detection Model (`FV.h5`)

* Determines whether the input is actually a fruit
* Helps avoid false triggers

### 2. Rotten Detection Model (`rotten.h5`)

* Classifies fruit into:

  * Fresh
  * Rotten

Both models are lightweight and designed to work in near real-time.

---

## ▶️ Running the Project

### 1. Clone the repository

```bash
git clone https://github.com/udit2303/EES-Project.git
cd EES-Project
```

---

### 2. Install dependencies

```bash
pip install tensorflow keras opencv-python numpy pandas matplotlib pyserial
```

---

### 3. Run the system

```bash
python rottentest.py
```

---

### 4. (Optional) Connect Hardware

To enable full functionality:

* Connect Arduino via USB
* Upload motor control code from `/motor`
* Ensure correct COM port is set in script

---

## 📊 Results & Observations

* The model achieved **~90%+ accuracy** on validation data
* Stable training and validation curves
* Real-time detection works smoothly with minimal delay
* Hardware response is quick and consistent

While not production-grade, the system demonstrates **strong feasibility for real-world use**.

---

## ⚠️ Challenges We Faced

This project was more than just training a model — it was about integration.

Some real challenges:

* 🔧 Hardware + software synchronization
* 📉 Limited dataset diversity
* ⏱️ Time and compute constraints
* 🔌 Debugging serial communication issues
* 🧠 Learning ML concepts from scratch

Each of these pushed us to iterate and improve the system step by step.

---

## 📚 What We Learned

This project was a complete hands-on experience. We learned:

* How to **train and evaluate ML models**
* How to use **computer vision in real-world problems**
* How to **connect AI with physical systems**
* Importance of **data quality and preprocessing**
* Debugging across **multiple domains (ML + hardware)**

