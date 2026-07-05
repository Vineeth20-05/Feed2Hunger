<div align="center">

# 🍱 Feed2Hunger

### Intelligent Food Redistribution & NGO Matching Platform

<p>
  <img src="https://img.shields.io/badge/BACKEND-DJANGO-092E20?style=for-the-badge&logo=django">
  <img src="https://img.shields.io/badge/DATABASE-POSTGRESQL-4169E1?style=for-the-badge&logo=postgresql">
  <img src="https://img.shields.io/badge/API-REST-009688?style=for-the-badge">
  <img src="https://img.shields.io/badge/MAPS-GOOGLE_MAPS-4285F4?style=for-the-badge&logo=googlemaps">
</p>

Feed2Hunger is an intelligent food redistribution platform that connects surplus food donors with suitable NGOs through structured donation workflows and distance- and capacity-aware matching.

The platform combines secure authentication, REST APIs, location intelligence, and data-driven matching logic to support efficient food allocation decisions.

</div>

---

## 📌 Overview

Large quantities of usable surplus food are wasted while NGOs and community organizations continue to face difficulties accessing food resources.

Feed2Hunger addresses this coordination gap by creating a centralized platform connecting:

- 🍽️ Food donors
- 🏢 NGOs
- 📦 Available food donations
- 📍 Location and distance information
- 📊 NGO capacity information
- 🔄 Donation workflows

Instead of relying only on manual NGO selection, the platform considers **distance, capacity, and availability** to identify suitable recipients.

---

## ✨ Key Features

### 🍽️ Food Donation Management

Donors can register available food and provide relevant information such as:

- Food details
- Available quantity
- Pickup location
- Availability information
- Donation status

The system manages donations through a structured workflow from registration to NGO assignment.

### 🏢 NGO Management

The platform maintains NGO information including:

- Organization details
- Location
- Receiving capacity
- Availability
- Donation assignments

This information is used during the matching process.

### 📍 Distance-Aware NGO Matching

Feed2Hunger integrates the Google Maps API to evaluate geographic distance between donors and available NGOs.

```text
New Food Donation
        │
        ▼
Retrieve Donor Location
        │
        ▼
Find Available NGOs
        │
        ▼
Evaluate Distance
        │
        ▼
Evaluate Capacity
        │
        ▼
Select Suitable NGO
        │
        ▼
Create Donation Assignment
```

### 🧠 Intelligent Allocation

The matching workflow evaluates practical redistribution factors including:

- Donor-to-NGO distance
- NGO receiving capacity
- Food quantity
- NGO availability
- Relevant workflow data

This provides a more structured allocation process than manual recipient selection.

### 🔐 Authentication & Access Control

The application includes secure authentication and controlled access to donor, NGO, and donation management workflows.

---

## 🏗️ System Architecture

```text
                    User
              Donor / NGO
                    │
                    ▼
              Web Interface
                    │
                    ▼
             Django Backend
                    │
          ┌─────────┼─────────┐
          │         │         │
          ▼         ▼         ▼
      REST APIs  Matching   Google Maps
                    Logic       API
          │         │         │
          └─────────┼─────────┘
                    │
                    ▼
               PostgreSQL
```

---

## 🔄 Donation Workflow

```text
Donor Registers Food
          │
          ▼
Donation Data Validation
          │
          ▼
Eligible NGO Identification
          │
          ▼
Distance Evaluation
          │
          ▼
Capacity Evaluation
          │
          ▼
NGO Selection
          │
          ▼
Donation Assignment
          │
          ▼
Workflow Status Update
```

---

## 🛠️ Technology Stack

| Category | Technologies |
|---|---|
| **Language** | Python |
| **Backend** | Django |
| **API Architecture** | REST APIs |
| **Database** | PostgreSQL |
| **Intelligent Logic** | Data-Driven Matching, Machine Learning |
| **Location Services** | Google Maps API |
| **Development Tools** | Git, GitHub |

---

## 📁 Project Structure

> Update folder names if your repository structure is different.

```text
Feed2Hunger/
│
├── manage.py
├── core/                  # Django configuration
├── donors/                # Donor workflows
├── ngos/                  # NGO management
├── donations/             # Donation workflows
├── matching/              # NGO matching logic
├── templates/             # HTML templates
├── static/                # CSS, JavaScript and assets
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Vineeth20-05/Feed2Hunger
cd Feed2Hunger
```

### 2. Create a Virtual Environment

```bash
python -m venv env
```

Activate it:

**Windows**

```bash
env\Scripts\activate
```

**Linux / macOS**

```bash
source env/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file:

```env
DJANGO_SECRET_KEY=your_secret_key

DB_NAME=your_database_name
DB_USER=your_database_user
DB_PASSWORD=your_database_password
DB_HOST=localhost
DB_PORT=5432

GOOGLE_MAPS_API_KEY=your_google_maps_api_key
```

> ⚠️ Never commit API keys, passwords, or `.env` files to version control.

### 5. Run Migrations

```bash
python manage.py migrate
```

### 6. Start the Application

```bash
python manage.py runserver
```

---

## 📸 Application Preview

Add screenshots of the main workflows:

- Home Page
- Donor Dashboard
- Food Donation Form
- NGO Dashboard
- Matching Results
- Map View
- Donation Status

Example:

```html
<p align="center">
  <img src="docs/screenshots/dashboard.png"
       width="850"
       alt="Feed2Hunger Dashboard">
</p>
```

---

## 💡 Engineering Highlights

Feed2Hunger demonstrates:

- Django backend development
- REST API design
- PostgreSQL database integration
- Authentication and access control
- Multi-entity workflow management
- Google Maps API integration
- Distance-aware matching
- Capacity-aware allocation
- Data-driven selection logic
- Real-world workflow modeling

---

## 🚀 Future Enhancements

- Real-time donor and NGO notifications
- Route optimization
- Food expiry-aware prioritization
- Surplus food prediction
- NGO demand forecasting
- Live donation tracking
- Analytics dashboard
- Mobile application support
- Cloud deployment
- Docker containerization
- Automated CI/CD

---

## 🌍 Project Goal

Feed2Hunger is designed to demonstrate how intelligent software systems can improve coordination between food donors and NGOs.

The platform aims to support better redistribution decisions through structured workflows, location intelligence, and capacity-aware matching.

---

## 👨‍💻 Author

### Vineeth M Gowda

**GitHub:** `https://github.com/Vineeth20-05`  
**LinkedIn:** `https://www.linkedin.com/in/vineeth-m-gowda-2512402a2/`

---

⭐ If you find Feed2Hunger interesting, consider starring the repository.

**Built to connect surplus food with communities that need it. 🍱🌍**
