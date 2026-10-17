<div align="center">

# 🌾 KisanChowk

### Direct Farm-to-Market Platform

**Your harvest, your market.**

*Built for HackShift by Team FINNOVATE*

</div>

---

## Table of Contents

- [Overview](#overview)
- [The Problem](#the-problem)
- [Our Solution](#our-solution)
- [How It Works](#how-it-works)
- [Key Features](#key-features)
- [Technical Approach](#technical-approach)
- [Security](#security)
- [Feasibility and Rollout](#feasibility-and-rollout)
- [Expected Impact](#expected-impact)
- [Comparison with Existing Systems](#comparison-with-existing-systems)
- [Research and Data Sources](#research-and-data-sources)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Roadmap](#roadmap)
- [Team](#team)

---

## Overview

**KisanChowk** is a web and mobile platform that connects farmers and Farmer Producer Organisations (FPOs) directly with retailers, wholesalers and consumers. It combines AI-driven price, quality and demand insights with direct negotiation, advance orders, delivery tracking and WhatsApp updates, all in one connected selling journey.

## The Problem

Multiple intermediaries between farm and buyer hurt both ends of the supply chain:

| Challenge | Impact |
|---|---|
| **Too many intermediaries** | Middlemen reduce farmers' earnings and raise the final price for buyers. |
| **Limited direct market access** | Farmers have little access to retailers, wholesalers and consumers. |
| **Uncertain prices and demand** | Farmers face uncertainty in crop prices and buyer demand. |
| **Transport delays and crop losses** | Selling also involves transport delays and produce losses. |

## Our Solution

1. **Direct market access.** Connect farmers/FPOs directly with retailers, wholesalers and consumers.
2. **AI guidance for selling decisions.** Fair price analysis, crop quality analysis, market trends and demand forecasts.
3. **One connected selling journey.** Direct negotiation, advance orders with crop photos, delivery tracking and WhatsApp updates.

```
Current route:       Farmer ── Intermediaries ── Buyer

KisanChowk:          Farmer / FPO ──── Negotiate ──── Buyer
                     AI guidance • advance orders • delivery tracking
```

## How It Works

```
Farmers / FPOs
      │
Crop listing + photos
      │
AI price, quality and demand insights
      │
Direct buyer negotiation
      │
Advance orders
      │
Delivery tracking + WhatsApp updates
```

**Farmer flow:** Login (OTP / biometrics) → Upload crop and photos → AI price and visible quality check → Publish listing

**Buyer flow:** Login (secure OTP / JWT) → Browse marketplace → Negotiate and place order → Order confirmation and payment

**Fulfilment:** Pickup and delivery tracking → Delivery, feedback and complaints

## Key Features

- **AI price band:** suggests a fair price range from mandi data.
- **Photo-based quality check:** flags visible crop defects from uploaded photos.
- **Demand forecasting:** forecasts from pilot order history.
- **Direct negotiation:** farmers and buyers agree on prices without middlemen.
- **Advance orders:** buyers order ahead with crop photos for reference.
- **Delivery tracking:** pickup-to-delivery status for every order.
- **WhatsApp / SMS updates:** keeps users informed even with patchy connectivity.
- **Feedback and complaints:** built-in support for transparent order resolution.
- **Local language and assisted onboarding:** designed for FPO-led adoption.

## Technical Approach

### Architecture

- **Frontend:** React interfaces connect farmers and buyers (lightweight PWA).
- **Backend:** Node.js / Express handles listings and orders.
- **AI services:** Python / FastAPI serves price and quality models.
- **Database:** PostgreSQL stores users, crops and transactions.
- **Integrations:** Weather, maps and messaging APIs support orders.
- **Deployment:** Docker services on AWS.

### Components

| Component | Responsibility |
|---|---|
| **AI Engine** | Fair price, crop quality and market trends |
| **Marketplace** | Direct negotiation, orders and complaints |
| **Deployment** | Containerised services on AWS |

### Methods

| Feature | Proposed Method | How It Works |
|---|---|---|
| Pricing | Quantile gradient boosting | Mandi data suggests a price band |
| Crop quality | MobileNetV3-Small (CNN) | Photos flag visible crop defects |
| Demand | Gradient boosting | Forecasts from pilot order history |
| SMS OTP | CSPRNG + HMAC-SHA-256 | Random code, expiry and retry limits |
| Biometrics | WebAuthn + ES256 | Device checks face / fingerprint |
| Data security | RS256-signed JWT + TLS | Role access and secure connections |

### Technology Stack

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

## Security

- OTP login with optional biometrics (WebAuthn)
- RS256-signed JWT with role-based access control
- HTTPS/TLS for all connections
- Secure payments
- Secure image uploads
- Audit logs
- Data protection through encryption, role-based access and audit logging

## Feasibility and Rollout

### Risks and mitigation

| Risk | Mitigation |
|---|---|
| Trust and adoption | FPO partners, local language support, assisted onboarding |
| AI data limitations | Validate AI against market data and expert checks |
| Connectivity gaps | Lightweight PWA with SMS / WhatsApp updates |

### Why it is feasible

- Built on established technology: existing AI/ML libraries, maps and weather APIs.
- Works on standard smartphones with OTP login and FPO onboarding.
- No specialised hardware; start with initial cloud services and scale as usage grows.

### Pilot to scale

Start with **selected crops in one region**, onboard FPOs and buyers, then **expand by crop and region**.

### Economic viability

- **Validate demand:** repeat orders and successful deliveries
- **Track operating cost per order:** cloud, messaging and support
- **Test sustainability:** order completion cost vs. expected revenue

## Expected Impact

- Greater control over selling for farmers / FPOs
- Clearer prices and produce information for buyers
- Better selling decisions with AI and weather guidance
- More transparent orders and complaint support
- Direct sourcing and advance orders for retailers

| Area | Benefit | How we measure it |
|---|---|---|
| **Farmer returns** | Direct price negotiation; more buyers and selling control | Net earnings per kg after costs |
| **Consumer value** | Visible prices and crop photos; advance orders | Delivered prices vs. local produce |
| **Smart and trusted** | AI selling guidance; tracking and complaint support | AI error, delivery success and repeat orders |

> Expected benefits only. Pilot results will establish the actual scale of impact.

## Comparison with Existing Systems

| Capability | **KisanChowk (Proposed)** | e-NAM | DeHaat | AgroStar | KisanSabha |
|---|---|---|---|---|---|
| Market access | Retail + wholesale | Mandi network | Institutional buyers | Global retail | Direct buyer links |
| Pricing | AI guidance + negotiation | Auctions | Mandi rates | Unclear* | Rates + buyer contact |
| Crop / weather advice | Planned | Unclear* | Crop + weather | Farm advice | Unclear* |
| Produce grading | Photo AI (planned) | Assaying | Unclear* | Unclear* | Unclear* |
| Order / logistics support | Tracking + WhatsApp | Logistics + lot status | Produce transport | Global supply chain | Transport matching |

\*Unclear = not specified in the sources we reviewed. It does not mean the feature is absent.

**Our distinction: one connected selling journey.** Use price and crop-photo insights to negotiate, arrange advance orders and track delivery within the same farmer-facing workflow. We also reviewed ONDC, Kisanbandi and Vithai.

## Research and Data Sources

1. **AGMARKNET / OGD:** daily mandi prices for model inputs
2. **e-NAM guidelines:** FPO registration, auctions and logistics
3. **RBI Bulletin (2019):** supply-chain margins and farmer shares
4. **IMD Agromet advisories:** weather-based crop guidance
5. **SFAC guidelines:** FPO development and post-harvest SOPs
6. **Fu et al. (2022):** deep learning for fruit freshness grading
7. **PLOS ONE (2022):** brinjal price forecasting with RF, ARIMA, SVR
8. **PIB:** official evidence on post-harvest crop losses

> Proposed features and impact require prototype and pilot validation.

## Getting Started

> Update the commands below to match your actual folder names and scripts.

### Prerequisites

- Node.js (LTS)
- Python 3.10+
- PostgreSQL
- Docker (optional, for containerised setup)

### Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

# Frontend
cd frontend
npm install
npm run dev

# Backend (Node.js / Express)
cd ../backend
npm install
npm start

# AI services (FastAPI)
cd ../ai-service
pip install -r requirements.txt
uvicorn main:app --reload
```

### Environment variables

Create a `.env` file in each service and set values such as:

```env
DATABASE_URL=
JWT_PRIVATE_KEY=
JWT_PUBLIC_KEY=
SMS_API_KEY=
MAPS_API_KEY=
WEATHER_API_KEY=
WHATSAPP_API_KEY=
```

### Run with Docker

```bash
docker compose up --build
```

## Project Structure

```
.
├── frontend/       # React web / PWA client
├── backend/        # Node.js / Express API (listings, orders, auth)
├── ai-service/     # FastAPI price, quality and demand models
├── docs/           # Design notes and prototype links
└── docker-compose.yml
```

## Roadmap

- [ ] Farmer and buyer onboarding with OTP login
- [ ] Crop listing with photo upload
- [ ] AI price band from mandi data
- [ ] Photo-based quality check
- [ ] Negotiation and advance orders
- [ ] Delivery tracking with WhatsApp / SMS updates
- [ ] Demand forecasting from pilot order history
- [ ] Pilot with selected crops in one region
- [ ] Expand by crop and region

## Team

**Team FINNOVATE**

- Krishna Agarwal
- Vaishnavi
- Surbhi Khandewal
- Amrita Choudhary

---

<div align="center">

**KisanChowk: Your harvest, your market.**

</div>
