# Voice Biometrics – Identity Verification

A web application for real-time speaker identity verification using voice biometrics.  
The system allows registration of voice samples and subsequent comparison of the most recent sample with all others stored in the database.

---

## Key Features

* **Voice Registration:**  
  Record voice directly through the browser microphone and generate a unique voice fingerprint (embedding).

* **Record Storage:**  
  Each voice recording is stored as a separate `.json` file named according to the registration date and time.

* **Recording List:**  
  The application automatically displays a list of all registered voice samples.

* **1:N Comparison:**  
  Ability to compare the latest registered voice against all others in the database and display similarity scores for each pair.

---

## Architecture and Technologies

The project is built on a modern three-tier architecture, where each layer has a clearly defined role.

| Layer | Technology | Role |
|------|-----------|------|
| **Frontend** | **Angular** | Displays the user interface, records audio from the microphone, and communicates with the backend. |
| **Backend** | **C# (.NET Core Web API)** | Handles requests, manages files, converts audio formats (using **FFmpeg**), and acts as a manager that delegates AI processing to Python. |
| **AI Core** | **Python** | Performs specialized AI analysis. Uses the **SpeechBrain** library to generate and compare voice embeddings. |

---

## How to Run the Project

Follow the steps below to successfully run the project and ensure all prerequisites are installed.

---

### Prerequisites

Make sure the following tools are installed on your system:

* [Node.js and npm](https://nodejs.org/) (for Angular)
* [Angular CLI](https://angular.io/cli) (`npm install -g @angular/cli`)
* [.NET SDK](https://dotnet.microsoft.com/download) (version 6.0 or newer)
* [Python](https://www.python.org/downloads/) (version 3.8+)
* [FFmpeg](https://ffmpeg.org/download.html)  
  *(On macOS: `brew install ffmpeg`)*

---

### 1. Clone the Repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd <PROJECT_FOLDER_NAME>
```

---

### 2. Python Environment Setup

Create a virtual environment and install all required AI dependencies.

```bash
# From the main project directory 'code'
python3 -m venv test_venv
source test_venv/bin/activate
pip install -r voice_recognition/requirements.txt
```

---

### 3. Run the Backend (C#)

```bash
# Navigate to the C# project directory
cd VoiceBiometricsApi

# (Optional but recommended) Trust the development HTTPS certificate
dotnet dev-certs https --trust

# Start the backend server
dotnet run
```

The backend will run on the address specified in  
`Properties/launchSettings.json` (e.g. `https://localhost:7194`).  
**Keep this terminal running.**

---

### 4. Run the Frontend (Angular)

Open a **new terminal** and start the frontend application.

```bash
# Navigate to the Angular project directory
cd voice-app

# Install dependencies (only required on first run)
npm install

# Start the frontend
ng serve
```

The application will automatically open in your browser at:  
`http://localhost:4200`

---

### 5. First-Time Usage

* **HTTPS Certificate Trust:**  
  If the frontend cannot communicate with the backend, open a new browser tab and go directly to the backend URL (e.g. `https://localhost:7194`).  
  Your browser will display a security warning. Click **Advanced** → **Proceed to localhost** to trust the certificate.

* **Microphone Permission:**  
  When clicking the record button for the first time, the browser will request permission to access the microphone.  
  You must allow it for the application to function properly.
