# 🦉 L'HIBOU — French Learning Web App

**L'HIBOU** is an interactive French-learning web application designed to help beginners master vocabulary and pronunciation through gamified quizzes, a visual learning path, and a lightweight Java backend.

🌐 **Live Demo:** _(Add your Railway URL here)_
📸 **Preview**

<img width="1919" height="969" alt="Screenshot 2025-12-15 143926" src="https://github.com/user-attachments/assets/6f04f20a-0569-4b3b-92fd-f85e78ef914f" />


---

## 📂 Project Structure

```
.
├── Dockerfile
├── start.sh                     # Startup script for Railway
├── README.md
├── webservice/
    ├── pom.xml                  # Maven configuration
    ├── src/
    │   ├── main/
    │   │   ├── java/org/global/academy/
    │   │   │   ├── Server.java          # Main Spark Server
    │   │   │   └── (Data Classes: LoginResponse, UserProgress...)
    │   │   └── resources/public/
    │   │       ├── index.html           # Hero Landing Page
    │   │       ├── login.html           # Auth Screen
    │   │       ├── setup.html           # Proficiency Wizard
    │   │       ├── welcome.html         # Learning Path Dashboard
    │   │       ├── lesson.html          # Interactive Quiz Game
    │   │       └── icons/*.svg
    └── target/ (compiled binaries)
```
🚀 Running the Project Locally
1️⃣ Build With Maven

```
cd webservice
mvn clean package
```

This generates: target/french-learning-1.0-SNAPSHOT-jar-with-dependencies.jar

2️⃣ Run the Server

```
java -jar target/french-learning-1.0-SNAPSHOT-jar-with-dependencies.jar

```
Your app will be available at: 👉 http://localhost:8080

☁️ Deployment (Railway)
This project is fully deployable on Railway.app, using: ✔ Java 17 ✔ Dockerfile ✔ start.sh entrypoint

To redeploy:

Push changes to GitHub.

Railway automatically rebuilds & redeploys your Docker image.

If you want manual deploy:

```
railway up
```

🎮 Learning System
The Lesson Engine loads data dynamically from the server.

Features:

📝 Smart Quizzes: Fetches questions via GET /lesson/{id}.

🗣️ Phonics Engine: Uses browser SpeechSynthesis to pronounce French consonants.

🛤️ Zig-Zag Path: Visual progress tracker (welcome.html).

✨ Instant Feedback: Green (Correct) / Red (Wrong) animations.

Lesson JSON Example:

```
{
  "question": "Which one of these is 'one'?",
  "options": [
    { "id": 1, "text": "l'homme", "icon": "👨🏾", "isCorrect": false },
    { "id": 2, "text": "un", "icon": "1️⃣", "isCorrect": true }
  ]
}
```
🔐 Authentication Flow
Login endpoint: POST /login

Response:
```
{
  "token": "token-123",
  "username": "alice"
}
```

Security:

Token is stored in localStorage.setItem("token", token).

File,Description
index.html,"Hero landing page with ""Get Started"" animations."
login.html,Bootstrap-styled login form.
setup.html,Onboarding wizard to select language proficiency.
welcome.html,"Main Dashboard with the ""Zig-Zag"" unit map & sounds."
lesson.html,The core game interface for taking quizzes.

🛠 Tech Stack
Backend
Java 17

Spark Java (Microframework)

Gson (JSON Parsing)

Frontend
HTML5 & CSS3

Bootstrap 5 (Responsive Grid)

JavaScript (ES6+)

Web Speech API (Text-to-Speech)

Deployment
Railway (Docker)

🌸 Philosophy
L'HIBOU aims to make learning French: ✨ Gamified ✨ Visual ✨ Interactive Learning a language should feel like a game, where you earn hearts and unlock paths, rather than just reading a textbook.

📄 License
This project is created for educational use.

💖 Author
Created by Global Academy Students 👨‍💻 During the CS Data Science & AI Curriculum
