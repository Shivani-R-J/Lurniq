# Lurniq 2.0 - Adaptive Collaborative Learning Platform

Lurniq 2.0 is an intelligent, dynamic learning platform designed to personalize educational content based on your unique learning style (VARK). It features AI-powered content generation, interactive study environments, and real-time collaboration.

**Try out the live platform here:** [https://lurniq.onrender.com/](https://lurniq.onrender.com/)

## Core Features

### VARK Adaptive Learning Engine
* **Dynamic Prediction:** Utilizes machine learning (Random Forest / Heuristics for cold start, and TensorFlow DNNs for complex modeling) to categorize users into Visual, Aural, Read/Write, or Kinesthetic learning styles based on interactive quizzes.
* **Smart Content Mapping:** Instantly transforms passive learning into interactive drag-and-drop activities (via `@dnd-kit`), fill-in-the-blank modules, and visual aids based on your VARK profile.

### Study Pods (Real-Time Collaboration)
* **Embedded Video Calling:** Integrated with the **Jitsi Meet API** to provide secure, room-based video sessions tied to unique Pod IDs, without heavy WebRTC overhead.
* **Interactive Whiteboard:** Features an embedded collaborative canvas using **WBO (Web Whiteboard)**, allowing real-time, low-latency drawing synchronized across all pod members.
* **Pod Battles:** Multiplayer gamified quizzes with dynamic real-time leaderboards.

### Concept Lens (AI Mindmapping)
* **Blazing Fast Inferences:** Powered by the **Groq API** to instantaneously generate comprehensive learning models, summaries, and quizzes.
* **Dynamic Flowcharts:** Translates AI outputs into beautiful, interactive concept diagrams using **Mermaid.js**.

### Document & Video Parsing
* **Smart Uploads:** Users can upload course PDFs, which are deeply parsed and summarized by the backend using **PyMuPDF**.
* **YouTube Integration:** Provide any YouTube video link; the platform uses the **youtube-transcript-api** to extract captions and generate custom learning materials instantly.

## Tech Stack

### Frontend (User Interface)
* **Framework:** React 19 + Vite
* **Styling:** Tailwind CSS, Lucide React, React Icons
* **Drag-and-Drop:** `@dnd-kit/core`
* **Diagramming:** Mermaid.js
* **Routing:** React Router DOM v7

### Backend (API & AI Processing)
* **Framework:** Python 3 / Flask
* **Database:** MongoDB (`pymongo`)
* **Authentication:** JWT (`flask-jwt-extended`) & bcrypt
* **AI Provider:** Groq
* **Machine Learning:** Scikit-Learn, Pandas, NumPy (TensorFlow available for advanced prediction)
* **Document Parsing:** PyMuPDF, `youtube-transcript-api`

## Local Setup & Installation

### 1. Clone & Frontend Setup
```bash
git clone https://github.com/your-username/lurniq-2.0.git
cd lurniq-2.0

# Install frontend dependencies
npm install

# Start the Vite development server
npm run dev
```

### 2. Backend Setup
Open a new terminal and navigate to the backend folder:
```bash
cd backend

# Create a virtual environment
python -m venv venv

# Activate the virtual environment (Windows)
venv\Scripts\activate
# For Mac/Linux: source venv/bin/activate

# Install Python requirements
pip install -r requirements.txt

# Create your .env file in the /backend folder
# Provide your GROQ_API_KEY, MONGO_URI, and JWT_SECRET_KEY

# Run the Flask server
python app.py
```

## Environment Variables (.env)
You will need to create a `.env` file in the `backend` directory containing the following:
```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET_KEY=your_secure_jwt_secret
GROQ_API_KEY=your_groq_api_key
```

## Contributing
Feel free to fork the repository, open issues, and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.
