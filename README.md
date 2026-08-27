# Speaking-Practice-Web
# 🎤 MS HÂN CLASS – Speaking Lab

Website luyện Speaking dành cho học sinh của **Ms Hân**, hỗ trợ các bé luyện phản xạ trả lời câu hỏi, ghi âm, nộp bài và theo dõi kết quả.

## 🌟 V1 – Tính năng

### 👧 Student

* 🎯 Luyện Speaking với câu hỏi ngẫu nhiên
* 🎤 Ghi âm câu trả lời trực tiếp bằng microphone
* ▶️ Nghe lại bài nói
* 🔊 Điều chỉnh âm lượng
* ⏩ Điều chỉnh tốc độ phát: 0.75× / 1× / 1.25×
* 🔄 Đổi câu hỏi
* 📤 Nộp bài
* 📊 Xem điểm Speaking
* 💡 Xem feedback
* 📝 Xem các bài Assignment

### 👩🏻‍🏫 Teacher

* Xem số lượng bài nộp
* Chấm điểm học sinh
* Nhập nhận xét
* Lưu điểm vào Firebase
* Theo dõi kết quả bài Speaking

---

## 🎨 Giao diện

**Style:** Modern Dark UI

**Main colors:**

* Midnight Blue
* Dark Navy
* Purple
* Cyan

**Font:** Inter / System UI

Thiết kế responsive, có thể sử dụng trên:

* 💻 Laptop
* 🖥️ Desktop
* 📱 Tablet
* 📱 Mobile

---

## ☁️ Database – Firebase

Website sử dụng **Firebase Realtime Database** để lưu dữ liệu.

### Database structure

```text
submissions
│
├── submissionId
│   ├── student
│   ├── question
│   ├── questionIndex
│   ├── score
│   ├── pronunciation
│   ├── fluency
│   ├── submittedAt
│   └── hasRecording

teacherScores
│
├── scoreId
│   ├── student
│   ├── score
│   ├── feedback
│   └── createdAt
```

### Firebase project

Project ID:

```text
student-mangenent
```

Database:

```text
Firebase Realtime Database
```

> ⚠️ Firebase Security Rules cần được cấu hình trước khi đưa website cho học sinh sử dụng chính thức. Không nên để học sinh có quyền tự sửa điểm hoặc dữ liệu của người khác.

---

## 📁 Project structure

V1 hiện tại có thể bắt đầu đơn giản với:

```text
MS-HAN-CLASS/
│
├── index.html
├── README.md
│
└── assets/
    ├── images/
    └── icons/
```

Trong `index.html` có:

* HTML
* CSS
* JavaScript
* Firebase configuration

Sau này có thể tách thành:

```text
src/
├── css/
├── js/
│   ├── firebase.js
│   ├── student.js
│   ├── teacher.js
│   ├── recording.js
│   └── questions.js
└── assets/
```

---

# 🚀 Cách chạy website

## Cách 1 – Mở trực tiếp

Có thể mở:

```text
index.html
```

Tuy nhiên, tính năng microphone có thể yêu cầu website chạy trên HTTPS hoặc localhost.

---

## Cách 2 – GitHub + Vercel

### Bước 1

Tạo một repository trên GitHub.

Ví dụ:

```text
ms-han-class-speaking
```

### Bước 2

Upload:

```text
index.html
README.md
```

### Bước 3

Đăng nhập Vercel và import repository GitHub.

### Bước 4

Deploy.

Sau mỗi lần cập nhật code và push lên GitHub, Vercel có thể tự động deploy phiên bản mới.

---

# 🎤 Recording

Website sử dụng trình duyệt để truy cập microphone.

Khi học sinh bấm:

```text
🎤 Start Recording
```

trình duyệt sẽ yêu cầu quyền microphone.

Sau khi ghi âm:

```text
⏹️ Stop
      ↓
▶ Play
      ↓
📤 Submit
```

### Lưu ý

V1 hiện lưu thông tin bài nộp vào Firebase.

File audio thực tế nên được đưa vào **Firebase Storage** ở phiên bản tiếp theo.

---

# 🤖 AI Speaking – V2

Các tính năng AI dự kiến:

### Speech-to-Text

Chuyển:

```text
🎤 Student voice
        ↓
Speech-to-Text
        ↓
"I usually go to school by bus."
```

### Pronunciation Analysis

Phân tích:

* Pronunciation
* Fluency
* Pauses
* Speaking speed
* Mispronounced words
* Volume

### Automatic Feedback

Ví dụ:

```text
⭐ Good job!

Pronunciation: 82/100
Fluency: 86/100

You should practise:

usually
school
```

Sau đó học sinh có thể:

```text
🔊 Listen
🎤 Record Again
```

---

# 📝 Assignment System – Future

Giáo viên có thể tạo:

```text
Speaking Homework #01

Questions:
10

Time:
30 seconds / question

Deadline:
30/08/2026
```

Học sinh:

```text
Assignment
      ↓
Start
      ↓
Answer
      ↓
Submit
      ↓
Teacher receives submission
```

---

# 🧪 Mock Test – Future

Chế độ thi thử:

```text
MOCK SPEAKING TEST

Preparation: 5 seconds

Answer: 30 seconds

Retry: ❌

Random questions: ✅

Auto score: ✅
```

Điểm cuối bài:

```text
Speaking Score
━━━━━━━━━━━━━━
      84

Pronunciation   82
Fluency         86
Vocabulary      85
Grammar         83
```

---

# 🔐 Security

Trước khi sử dụng chính thức, cần thiết lập Firebase Security Rules để:

* Học sinh chỉ xem dữ liệu của mình
* Học sinh không thể sửa điểm
* Học sinh không thể xóa bài của người khác
* Giáo viên có quyền chấm điểm
* Chỉ giáo viên có quyền quản lý Assignment

Authentication nên được thêm ở phiên bản tiếp theo.

---

# 📌 Roadmap

## V1 – Current

* [x] Speaking Practice
* [x] Random Questions
* [x] Voice Recording
* [x] Playback
* [x] Volume Control
* [x] Speed Control
* [x] Submit
* [x] Firebase Realtime Database
* [x] Teacher Scoring
* [x] Teacher Feedback
* [x] Assignment UI

## V1.5

* [ ] Student Login
* [ ] Teacher Login
* [ ] Firebase Authentication
* [ ] Firebase Storage
* [ ] Real audio submission
* [ ] Student profiles
* [ ] Better score history
* [ ] Teacher student management

## V2

* [ ] Speech-to-Text
* [ ] AI pronunciation scoring
* [ ] Fluency analysis
* [ ] Automatic feedback
* [ ] Mispronounced-word detection
* [ ] Individual pronunciation practice

## V3

* [ ] Full Speaking Mock Test
* [ ] Automatic reports
* [ ] Parent report
* [ ] Student ranking / achievements
* [ ] Listening practice
* [ ] Reading practice
* [ ] Writing practice

---

# 👩🏻‍🏫 Project

**MS HÂN CLASS**

> Listen • Speak • Improve 🎤

Designed for English learners practising Speaking with **Ms Hân**.
