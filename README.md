# Student Attendance System

## Overview

The **Student Attendance System** is a Python-based application designed to simplify the process of student attendance using face recognition technology. This project combines the power of machine learning with an interactive PyQt GUI to offer a user-friendly and efficient solution for managing attendance records.

---

## Features

### 1. **Face Recognition System**
- Built using **HOG (Histogram of Oriented Gradients)** and **ResNet** models from the `face_recognition` library.
- Achieves an **accuracy of 90%** in predicting and recognizing student faces.
- Matches recognized faces against a database to mark attendance.

---

### 2. **PyQt5 GUI with Multi-Page Navigation**
The GUI provides an intuitive interface with the following key panels:

#### **Login Page**
- Secure login with **username** and **password**. (for 1st time usename: op password: op)
- Access to:
  - **Data Management Panel**
  - **Student Management Panel**

#### **Data Management Panel**
- Add new users (usename name and password)
- Add new student (name,batch,roll number,year,and 3 photos to save it in training folder)
- Update existing user and student information.
- Encode faces and store them in the database for recognition.

#### **Student Management Panel**
- Input fields for:
  - **Subject Name**
  - **Date & Time**
  - **Year** and **Batch**
- Fetches the list of students (names, roll numbers, and batch) based on the selected criteria.
- Starts the **Face Recognition System** to:
  - Recognize faces in real time.
  - Mark recognized students as **Present**.
  - Automatically mark unrecognized or absent students as **Absent** upon closing attendance.
- Save attendance records for future use.

---

## How It Works

### Face Encoding Process (`encode.py`)
1. All images of students are stored in the **`training`** folder.
   - Each student's images are stored in a separate subfolder named after the student (e.g., `training/John_Doe/`).
2. The `encode.py` script:
   - Reads all images from the `training` folder.
   - Encodes each face using the `face_recognition` library.
   - Saves the encodings along with their respective names into an **`output.pkl`** file.
3. The encoded data in the `output.pkl` file is used during face recognition to match and identify students.

### Attendance Process
1. In the **Student Management Panel**:
   - Select the **subject**, **date**, **time**, **year**, and **batch**.
   - Fetch the student data for the selected batch.
   - Press **Start Attendance** to open the face recognition system.
2. The system:
   - Recognizes faces in real time using the encodings from `output.pkl`.
   - Marks recognized students as **Present**.
   - Marks others as **Absent** when attendance is closed.
3. Save the attendance data.

---

## Installation

### Prerequisites
- Python 3.7 or above
- Required Python libraries: 
  - PyQt5
  - OpenCV
  - face_recognition
  - NumPy
  - Pandas

### Steps
1. Clone this repository:
   ```bash
   git clone https://github.com/Rahulsingh/Student-Attendance-System.git
   
2. Install the required libraries:
   ```bash
   pip install pyqt5 opencv-python face-recognition numpy pandas

3. Run the application::
   ```bash
   python main.py
   
### Usage
1. Login to the system.
2. Navigate to the appropriate panel:
    - Data Management Panel to manage user/student data and encode faces.
    - Student Management Panel to mark attendance.
       -Use the Face Recognition System to identify students and save attendance records.

### Future Improvements
1. Enhance the face recognition model for higher accuracy.
2. Integrate real-time database synchronization for cloud-based attendance management.
3. Add analytics and reporting features for attendance trends.

### Contributing
Contributions are welcome! Please fork the repository and submit a pull request for review.
### License
This project is licensed under the MIT License. See the LICENSE file for details.


