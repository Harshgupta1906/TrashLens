<div align="center">

<img src="https://img.shields.io/badge/TrashLens-Smart%20Waste%20AI-2ea44f?style=for-the-badge&logo=leaf&logoColor=white" alt="TrashLens"/>

# ♻️ TrashLens
### *AI-Powered Intelligent Waste Classification & Management System*

[![Live Demo](https://img.shields.io/badge/🌐%20Live%20Demo-trashlens.onrender.com-blue?style=for-the-badge)](https://trashlens.onrender.com)
[![GitHub](https://img.shields.io/badge/GitHub-Himanshu--279-181717?style=for-the-badge&logo=github)](https://github.com/Himanshu-279/TrashLens)
[![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Django](https://img.shields.io/badge/Django-4.x-092E20?style=for-the-badge&logo=django&logoColor=white)](https://djangoproject.com)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.10.1-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://tensorflow.org)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

<br/>

> **TrashLens** is a production-grade, end-to-end intelligent waste classification platform powered by **EfficientNetV2-L** (95.6% accuracy). It classifies waste into **12 fine-grained categories**, helps users locate nearby recycling facilities, and continuously improves itself through an admin-triggered retraining pipeline — all deployable both as a web app and a fully **offline Android application**.

<br/>

---

</div>

## 📑 Table of Contents

- [✨ Key Highlights](#-key-highlights)
- [🧠 Model & Architecture](#-model--architecture)
- [🚀 Features](#-features)
- [🏗️ System Architecture](#️-system-architecture)
- [🛠️ Tech Stack](#️-tech-stack)
<!--
  Professional README for TrashLens
  Purpose: concise, scannable, and ready for GitHub repository homepage.
  Edit placeholders (CONTACT_EMAIL) as needed.
-->

<div align="center">

![TrashLens](https://img.shields.io/badge/TrashLens-Smart%20Waste%20AI-2ea44f?style=for-the-badge&logo=leaf&logoColor=white)

# TrashLens
AI-powered waste classification and management platform — web + offline Android app.

[Live demo](https://trashlens.onrender.com) · [Source (Himanshu-279)](https://github.com/Himanshu-279/TrashLens)

</div>

---

## What is TrashLens
TrashLens classifies waste into 12 fine-grained categories using EfficientNetV2-L and helps users locate relevant recycling centers. It supports a production-ready Django web app, an offline Android client (TFLite), and an admin retraining pipeline for continuous improvement.

Key outcomes:
- High accuracy classifier (reported 95.6% on validation)
- Offline-capable Android app using TFLite
- Docker-ready deployment and Render integration

---

## Quick Links
- Demo: https://trashlens.onrender.com
- Repo: https://github.com/Himanshu-279/TrashLens
- License: MIT

---

## Features
- Image-based classification (12 classes)
- Recycling center lookup (Haversine distance, `centers.csv`)
- Admin dashboard + one-click retraining
- Offline Android app using TFLite
- Dockerized for consistent deployments

---

## Tech Stack
- Deep learning: TensorFlow / Keras (EfficientNetV2-L)
- Backend: Python 3.10, Django 4.x
- Mobile: Android (Java) + TensorFlow Lite
- DB & hosting: Supabase (Postgres), Cloudinary, Render
- Containerization: Docker

---

## Quick Start (local)
Prereqs: Python 3.10+, Git, (optional) Docker

1. Clone

```bash
git clone https://github.com/Himanshu-279/TrashLens.git
cd TrashLens
```

2. Virtualenv & install

```bash
python -m venv venv
# Windows
venv\\Scripts\\activate
pip install -r requirements.txt
```

3. Environment & run

Create a local `.env` file with the required variables (do NOT put secrets in the README). Example variables (leave values empty locally and fill on your machine or CI):

```
SUPABASE_URL=
SUPABASE_KEY=
CLOUDINARY_URL=
DJANGO_SECRET_KEY=
```

Then run:

```bash
python manage.py migrate
python manage.py runserver
# open http://127.0.0.1:8000
```

For Docker:

```bash
docker build -t trashlens .
# Use an env file (do NOT store secrets in the README)
docker run --env-file .env -p 8000:8000 trashlens
```

---

## Project layout
- `core/` — Django app: views, utils, templates
- `trashlens_project/` — Django settings and WSGI
- `centers.csv` — recycling facility data
- `Dockerfile`, `build.sh` — deployment helpers
- `requirements.txt` — Python deps

---

## Android app
The Android client uses a TFLite version of the model so classification works fully offline after the initial model download.

---

## Contributing
Please read [CONTRIBUTING.md](CONTRIBUTING.md) and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). Typical workflow:

```bash
git checkout -b feature/your-feature
# make changes
git commit -m "feat: short description"
git push origin feature/your-feature
```

---

## License
This project is licensed under the MIT License — see the `LICENSE` file.

---

## Contact
- Maintainer: Himanshu Verma · https://github.com/Himanshu-279
- Email: CONTACT_EMAIL (replace with your preferred contact)

If you want, I can fill in the contact email and add GitHub stat cards and project highlights.
├── trashlens_project/           # Project settings and routing
│   ├── settings.py              # Environment-driven Django settings
│   ├── urls.py                  # Root URL configuration
│   └── wsgi.py                  # WSGI entry point
├── .env.example                 # Template for local environment variables
├── .github/                     # Issue templates and PR template
├── centers.csv                  # Recycling-center data used by the map feature
├── Dockerfile                   # Container build definition
├── build.sh                     # Deployment helper script
├── manage.py                    # Django management entry point
├── requirements.txt             # Python dependencies
└── README.md                    # Project overview and setup guide
```

---

## ⚡ Quick Start (Local)

### Prerequisites
- Python 3.10+
- Git
- (Optional) Docker

### 1. Clone the Repository

```bash
git clone https://github.com/Himanshu-279/TrashLens.git
cd TrashLens
```

### 2. Create & Activate Virtual Environment

```bash
# Linux / macOS
python -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Set Environment Variables

Copy the example file and fill in your own values:

```bash
cp .env.example .env
```

The `.env` file is ignored by Git, so your API keys and secrets stay local. Update the values in the new file before running the app.

### 5. Apply Migrations

```bash
python manage.py migrate
```

### 6. Run the Server

```bash
python manage.py runserver
```

Open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser. 🎉

---

## 🤝 Contributing

Contributions are welcome. Please review [CONTRIBUTING.md](CONTRIBUTING.md) for setup instructions, coding expectations, and the pull-request workflow.

For community guidelines, see [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

---

## 🐳 Docker Setup

```bash
# Build the image
docker build -t trashlens .

# Run the container using an env file (keeps secrets out of README)
docker run --env-file .env -p 8000:8000 trashlens
```

Visit [http://localhost:8000](http://localhost:8000)

---

## 📱 Android Application

The TrashLens Android app uses a **TFLite version of EfficientNetV2-L** and supports **fully offline classification** after the initial model download.

```
First Launch:
  └── Model downloaded & saved to device storage

Every Subsequent Launch (even offline):
  └── TFLite Interpreter loads local model
  └── Camera / Gallery → Preprocess → Infer → Result
  └── Zero network requests for classification
```

> **Why offline?** API-dependent apps fail in low-connectivity zones — particularly relevant for rural India. TrashLens Android runs classification entirely on-device, making it reliable regardless of network availability.

**Download:** Available via the web app's homepage → *Download Android App* button.

---

## 🌍 Deployment on Render

This project is pre-configured for one-click deployment on [Render](https://render.com).

1. Fork this repository
2. Connect your GitHub account to Render
3. Create a **New Web Service** and select this repo
4. Set the following:

| Setting | Value |
|---|---|
| **Build Command** | `./build.sh` |
| **Start Command** | `gunicorn trashlens_project.wsgi:application` |
| **Environment** | Add your `.env` variables in Render's dashboard |

5. Click **Deploy** — Render handles the rest ✅

---

## 🔁 Admin Panel & Retraining

TrashLens includes a built-in Admin Panel that makes the system **self-improving**:

```
User submits feedback (correct / incorrect prediction)
         │
         ▼
Feedback stored in Supabase
         │
         ▼
Admin reviews dashboard (accuracy trends, error classes)
         │
         ▼
Admin clicks "Trigger Retraining"
         │
         ▼
System pulls misclassified samples from feedback DB
         │
         ▼
EfficientNetV2-L retrained on original + corrected data
         │
         ▼
Updated .keras model auto-deployed to web server
Android TFLite refreshes on next app launch ♻️
```

No manual ML engineering needed — just one button press.

---

## 📊 Results

### Per-Class Performance (EfficientNetV2-L · Validation Set · 3,103 images)

| Class | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|
| battery | 0.95 | 0.94 | 0.94 | 189 |
| biological | 0.92 | 0.93 | 0.92 | 197 |
| brown-glass | 0.94 | 0.92 | 0.93 | 121 |
| cardboard | 0.94 | 0.95 | 0.94 | 178 |
| clothes | 0.97 | 0.98 | **0.97** | 1067 |
| green-glass | 0.93 | 0.91 | 0.92 | 131 |
| metal | 0.93 | 0.92 | 0.92 | 154 |
| paper | 0.94 | 0.95 | 0.94 | 214 |
| plastic | 0.92 | 0.91 | 0.92 | 173 |
| shoes | 0.96 | 0.97 | 0.96 | 402 |
| trash | 0.92 | 0.91 | 0.91 | 141 |
| white-glass | 0.94 | 0.93 | 0.93 | 136 |
| **Macro Avg** | **0.95** | **0.95** | **0.95** | **3103** |

---

## 🤝 Contributing

Contributions are warmly welcome! Here's how to get started:

```bash
# 1. Fork the repository
# 2. Create your feature branch
git checkout -b feature/your-feature-name

# 3. Make your changes and commit
git commit -m "feat: add your feature description"

# 4. Push to your branch
git push origin feature/your-feature-name

# 5. Open a Pull Request on GitHub
```

Please follow conventional commits and make sure your code is clean and documented.

---

## 📬 Contact

<div align="center">

**Himanshu Verma**  
B.Tech CSE · School of Management Sciences, Lucknow · AKTU 2026

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Himanshu%20Verma-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/himanshu-verma-1711)
[![GitHub](https://img.shields.io/badge/GitHub-Himanshu--279-181717?style=for-the-badge&logo=github)](https://github.com/Himanshu-279)

</div>

---

<div align="center">

Made with ❤️ for a cleaner planet 🌍

⭐ **Star this repo if you found it helpful!**

</div>
