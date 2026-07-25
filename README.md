# 🎓 Attend-X (Face Recognition Attendance System)

A desktop-based **automated attendance management system** built with **Python, OpenCV, Tkinter, and MySQL**. The system uses **LBPH (Local Binary Pattern Histogram)** face recognition to identify students in real time through a webcam and automatically records attendance, with support for exporting reports in both **CSV** and **Excel** formats.

---

## 📸 Features

- 🔐 **Secure Login & Registration** — User authentication backed by MySQL
- 👨‍🎓 **Student Management** — Add, update, delete student records with photo capture
- 🤖 **Face Detection & Model Training** — Capture face samples and train the LBPH classifier
- 📷 **Real-Time Face Recognition** — Webcam-based recognition with confidence threshold
- ✅ **Automatic Attendance Marking** — Prevents duplicate attendance using a 2-minute cooldown
- 📊 **Attendance Reports** — Automatically generates formatted Excel attendance reports
- 📁 **CSV Import & Export** — Import, edit, and export attendance records
- 📋 **Student Excel Export** — Export the complete student database to Excel
- 👨‍💻 **Developers & About Pages** — Built-in About and Developers sections

---

# 🗂️ Project Structure

```text
Attend-X-Face-Recognition-Attendance-System/
│
├── run.py
├── login.py
├── main.py
├── student.py
├── train.py
├── face_recognition.py
├── attendance.py
├── generate_attendance_excel.py
├── export_students_excel.py
├── about.py
├── developers.py
│
├── haarcascade_frontalface_default.xml
│
├── data/
├── images/
│
├── requirements.txt
├── README.md
└── .gitignore
```

> **Note:** `classifier.xml` is **not included** in this repository. It is automatically generated after running `train.py`.

---

# ⚙️ Requirements

- Python **3.9.1** (Recommended)
- MySQL Server
- Webcam

---

# 📦 Python Dependencies

Install all dependencies using:

```bash
python -m pip install -r requirements.txt
```

| Package | Version |
|----------|---------|
| opencv-contrib-python | 4.13.0.92 |
| Pillow | 8.1.0 |
| numpy | 2.0.2 |
| mysql-connector-python | 9.4.0 |
| openpyxl | 3.1.5 |

---

# 🛠️ Installation

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/swastika-1/Attend-X-Face-Recognition-Attendance-System-.git
cd Attend-X-Face-Recognition-Attendance-System-
```

---

## 2️⃣ Create a Virtual Environment (Recommended)

### Windows

```bash
python -m venv face_env
face_env\Scripts\activate
```

### macOS/Linux

```bash
python3 -m venv face_env
source face_env/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
python -m pip install -r requirements.txt
```

---

## 4️⃣ Configure MySQL Database

Create the following database:

```sql
CREATE DATABASE face_recognizer;

USE face_recognizer;

CREATE TABLE student (
    studentID INT PRIMARY KEY AUTO_INCREMENT,
    student_name VARCHAR(100),
    Roll_no VARCHAR(50),
    dep VARCHAR(100),
    course VARCHAR(100),
    year VARCHAR(20),
    semester VARCHAR(20),
    section VARCHAR(20),
    gender VARCHAR(20),
    dob VARCHAR(30),
    email VARCHAR(100),
    Phone_no VARCHAR(20),
    address TEXT,
    teacher_name VARCHAR(100),
    Photo_Sample VARCHAR(200)
);

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(100)
);
```

---

## 5️⃣ Update Database Credentials

Update your MySQL credentials inside:

- `login.py`
- `face_recognition.py`
- `generate_attendance_excel.py`
- `export_students_excel.py`

---

## 6️⃣ Add Student Face Samples

Run the application:

```bash
python run.py
```

Open **Student Details**, enter the student information, and capture face samples.

---

## 7️⃣ Train the Face Recognition Model

After capturing student images, run:

```bash
python train.py
```

This generates the required **classifier.xml** model automatically.

---

## 8️⃣ Start the Application

```bash
python run.py
```

---

# 🚀 Usage Workflow

```text
Register / Login
        │
        ▼
Add Student Details
        │
        ▼
Capture Face Samples
        │
        ▼
Train the Model
(train.py)
        │
        ▼
classifier.xml Generated
        │
        ▼
Start Face Recognition
        │
        ▼
Attendance Automatically Recorded
        │
        ▼
Export Attendance Reports
```

---

# 📌 Notes

- Face recognition works only **after** the model has been trained.
- `classifier.xml` is **generated automatically** after running `train.py`.
- The `data/` folder stores captured face images.
- Attendance reports are generated in Excel format.
- Duplicate attendance is prevented using a **2-minute cooldown**.
- Make sure your webcam is connected before starting face recognition.

---

# 🛠️ Tech Stack

- **Python**
- **OpenCV**
- **Tkinter**
- **MySQL**
- **NumPy**
- **OpenPyXL**
- **Pillow**

---

# 👨‍💻 Developers

Developed as an academic project for learning computer vision and desktop application development.

See the **Developers** page inside the application for project contributors.

---

# 📄 License

This project is intended **for educational purposes only**.

---

## ⭐ If you found this project useful, consider giving it a star on GitHub!
