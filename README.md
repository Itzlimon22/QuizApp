Quiz Master
Overview
Quiz Master is a dynamic and interactive web application designed for students and enthusiasts to test their knowledge in various academic subjects and admission test categories. The application features customizable quizzes, real-time feedback, and a leaderboard to track progress and compete with others.

Features
Customizable Quizzes: Select from a range of academic subjects (Physics, Chemistry, Biology, Math, ICT) and admission test types (Engineering, Medical, Varsity). You can choose a specific subject, a chapter, or even a random set of questions from all available topics.

Timed Quizzes: Challenge yourself with a time limit to simulate exam conditions.

Negative Marking: Practice for real exams with an optional negative marking system.

Dashboard: Track your performance with a personalized dashboard showing your last score, total quizzes completed, and a breakdown of your accuracy by subject.

Leaderboard: Compete with other users and see your rank on the public leaderboard.

Personalized Certificate: Generate and download a PDF certificate of completion for your last quiz.

Shareable Results: Create a shareable image of your quiz results to share with friends and on social media.

Theming: Customize the app's look and feel with different themes.

Technology Stack
Frontend: Pure HTML, CSS, and JavaScript.

Styling: Tailwind CSS for a utility-first approach to responsive design.

Interactivity: Vanilla JavaScript for all dynamic functionality.

Libraries:

firebasejs for user authentication and real-time data storage via Firestore.

html2canvas and jspdf for generating shareable images and PDF certificates.

canvas-confetti for celebratory effects on high scores.

Data: All quiz questions are stored directly within the index.html file for simplicity and to avoid the need for a separate backend.

Getting Started
Prerequisites
A modern web browser (like Chrome, Firefox, or Edge).

Running the App
Since the app is a single HTML file, you can run it in a couple of ways:

Open Directly: Simply open the index.html file in your web browser. All functionality will work, but data will not be saved or shared with other users.

Using a Local Web Server (Recommended): To ensure all features, especially the Firebase functionalities, work correctly, it is recommended to serve the file from a local web server. You can use a simple server like Python's http.server:

Navigate to the directory containing index.html.

Run the following command in your terminal:

python -m http.server

Open your web browser and go to http://localhost:8000.

Firebase Integration
The application uses Firebase for user data persistence and the public leaderboard. You do not need to set this up yourself, as it's handled by the environment. The following variables are automatically provided:

__app_id

__firebase_config

__initial_auth_token

These are used to initialize Firebase and authenticate the user, allowing for a seamless experience.

Contributing
If you'd like to add more questions or features, you can directly edit the index.html file.

To add more questions, expand the quizData object with new subjects, chapters, or questions.

To add a new feature, follow the existing JavaScript patterns for UI rendering and state management.

License
This project is open source and available for personal and educational use.
