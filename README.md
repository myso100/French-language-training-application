# 🦉 L'HIBOU — Dualingo Learning Web App

**L'HIBOU** is an interactive French-learning web application designed to help beginners master vocabulary and pronunciation through gamified quizzes, a visual learning path, and a lightweight Java backend.

🌐 **Live Demo:** _(Add your Railway URL here)_
📸 **Preview**

> _(Add a screenshot of your welcome.html or lesson.html here)_

---

## 📂 Project Structure

```text
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
