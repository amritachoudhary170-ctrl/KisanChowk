# 🌾 KisanChowk

### Direct Farm-to-Market Platform

**Your harvest, your market.**

---

## Table of Contents

- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Proposed Solution](#proposed-solution)
- [How It Works](#how-it-works)
- [Key Features](#key-features)
- [Technical Architecture](#technical-architecture)
- [AI and Machine Learning Approach](#ai-and-machine-learning-approach)
- [Security](#security)
- [Feasibility and Rollout](#feasibility-and-rollout)
- [Expected Impact](#expected-impact)
- [Evaluation Metrics](#evaluation-metrics)
- [Research and Data Sources](#research-and-data-sources)
- [Project Structure](#project-structure)
- [Roadmap](#roadmap)

---

## Overview

**KisanChowk** is a proposed digital agricultural platform designed to empower farmers through technology. It aims to combine agricultural decision support with a direct farm-to-market marketplace.

The platform focuses on five major areas: improving crop productivity, identifying potential plant diseases, providing access to agricultural market prices, supporting efficient irrigation, and connecting farmers directly with buyers.

By bringing these capabilities into one platform, KisanChowk aims to help farmers make informed farming and selling decisions while improving transparency and market accessibility.

## Problem Statement

Farmers face challenges throughout the agricultural lifecycle, from cultivation and crop management to selling their produce.

| Challenge | Problem |
|---|---|
| Crop productivity | Limited access to relevant agricultural information can make it difficult to identify suitable practices for improving crop productivity. |
| Plant diseases | Late identification of plant diseases can affect crop health, yield, and quality. |
| Market price uncertainty | Farmers may lack timely information about market prices across different markets. |
| Irrigation management | Inefficient irrigation can waste water and increase cultivation costs. |
| Market access | Dependence on intermediaries can reduce farmers' earnings and increase the final price paid by buyers. |
| Demand uncertainty | Farmers may struggle to anticipate buyer demand and plan their sales. |
| Transportation and losses | Delays in transporting agricultural produce can affect freshness, quality, and sale value. |

KisanChowk aims to address these challenges through accessible digital tools, data-driven insights, and direct buyer connectivity.

## Proposed Solution

KisanChowk proposes a unified platform that combines agricultural support and marketplace functionality.

1. **Agricultural decision support:** Provide relevant crop information to help farmers make informed cultivation decisions.
2. **Plant disease detection:** Explore image-based identification of visible crop diseases using machine learning.
3. **Market price insights:** Present available mandi prices and explore data-driven price guidance.
4. **Irrigation optimization:** Use relevant weather, crop, and soil information where available to support irrigation planning.
5. **Direct marketplace:** Connect farmers and Farmer Producer Organizations (FPOs) with retailers, wholesalers, and consumers.
6. **Order and delivery management:** Support negotiation, advance orders, delivery tracking, and order updates.

## How It Works

### Agricultural Support Flow

```text
Farmer
   |
   v
Enter Crop Information
   |
   v
Access Agricultural Information
   |
   +----> Plant Disease Image Analysis
   |
   +----> Market Price Information
   |
   +----> Irrigation Guidance
   |
   v
Make Informed Farming Decisions
```

### Marketplace Flow

```text
Farmer / FPO
     |
     v
Upload Crop Details and Photos
     |
     v
Publish Crop Listing
     |
     v
Buyer Discovers Available Produce
     |
     v
Direct Negotiation
     |
     v
Order Confirmation
     |
     v
Pickup and Delivery Tracking
```

These workflows describe the intended system. Their individual steps will become operational as the corresponding features are implemented.

## Key Features

### 1. Crop Productivity Support

- Provide crop-related agricultural information.
- Help farmers explore suitable cultivation practices.
- Support informed decisions about crop management.
- Explore the integration of relevant weather and agricultural advisory data.

### 2. Plant Disease Detection

- Allow farmers to upload images of leaves or affected plant parts.
- Explore image classification using computer vision and machine learning.
- Identify potential disease categories supported by the trained model.
- Provide relevant guidance for further assessment.

Image-based predictions will require validation and should not be treated as a definitive diagnosis without appropriate expert review.

### 3. Agricultural Market Price Insights

- Display available agricultural market prices.
- Support comparison of prices across available markets.
- Use historical mandi data to investigate price patterns.
- Explore AI-based price ranges to support selling decisions.

Price guidance will depend on data availability, crop type, location, market conditions, and model evaluation.

### 4. Irrigation Optimization

- Explore irrigation guidance based on available crop and weather information.
- Integrate weather data where suitable APIs are available.
- Incorporate soil moisture information if reliable measurements become available.
- Help farmers investigate opportunities to improve water-use efficiency.

Automated irrigation recommendations will require suitable input data and field validation.

### 5. Direct Farmer-to-Buyer Marketplace

- Enable farmers and FPOs to create crop listings.
- Include crop name, quantity, expected price, location, and photos.
- Allow buyers to discover available agricultural produce.
- Support direct communication and price negotiation.
- Explore advance orders and order confirmation.
- Provide order-status and delivery tracking.

### 6. Demand Insights

- Explore historical order data to identify demand patterns.
- Investigate demand forecasting for selected crops.
- Use validated insights to support future selling and procurement decisions.

Reliable forecasting will require sufficient, representative order data.

### 7. Notifications and Accessibility

- Explore SMS and WhatsApp order updates.
- Design a mobile-friendly interface for smartphone users.
- Plan local-language support and assisted onboarding.
- Keep the experience lightweight for users with limited connectivity.

## Technical Architecture

The following is the proposed architecture for implementation.

| Component | Proposed Technology | Responsibility |
|---|---|---|
| Frontend | React | Farmer and buyer interfaces |
| Backend | Node.js, Express | Listings, orders, and application APIs |
| AI services | Python, FastAPI | Serving trained machine learning models |
| Database | PostgreSQL | Users, crop listings, and transaction records |
| Image analysis | TensorFlow or compatible ML libraries | Plant disease and image classification experiments |
| External integrations | Weather, maps, and messaging APIs | Supporting information and notifications |
| Deployment | Docker, AWS | Containerization and cloud hosting |

The technology stack may be adjusted as development and testing progress.

## AI and Machine Learning Approach

### Crop Price Guidance

**Proposed method:** Quantile Gradient Boosting.

Potential inputs include historical mandi prices, crop type, market location, and available historical observations. The objective is to estimate a price range rather than present a single value as guaranteed.

### Plant Disease Detection

**Proposed method:** Image classification using a convolutional neural network (CNN).

A lightweight model such as MobileNetV3-Small may be evaluated using labeled crop disease images. Model performance must be measured on data that was not used for training.

### Demand Forecasting

**Proposed method:** Gradient boosting or another suitable forecasting approach.

Historical order records, when sufficient, may be used to investigate demand patterns for selected crops and regions.

### Irrigation Guidance

**Proposed approach:** Rule-based recommendations initially, with further modelling explored if suitable data is available.

Potential inputs include weather forecasts, crop requirements, and soil moisture measurements where available.

### Model Evaluation

Models will be evaluated using suitable metrics, such as:

- **Price prediction:** MAE and RMSE.
- **Disease classification:** Precision, recall, F1-score, and a confusion matrix.
- **Demand forecasting:** MAE or RMSE.
- **Irrigation guidance:** Water usage and recommendation performance during field evaluation.

No model accuracy or performance result should be reported until it has been measured experimentally.

## Security

Security requirements for implementation include:

- Secure authentication and session management.
- Role-based access for farmers, buyers, and administrators.
- Secure storage and handling of credentials and secrets.
- HTTPS/TLS for data transmission.
- Validation of uploaded images and user inputs.
- Protection of personal and transaction data.
- Appropriate logging and error handling.
- Rate limiting and abuse prevention for sensitive APIs.

OTP authentication, WebAuthn-based authentication, and signed JWTs may be evaluated as part of the implementation. Their final design will depend on the application's security requirements.

## Feasibility and Rollout

### Key Risks and Mitigation

| Risk | Proposed Mitigation |
|---|---|
| Limited or inconsistent agricultural data | Start with reliable sources and document data limitations. |
| Insufficient disease-image data | Evaluate labeled datasets and validate results on independent images. |
| Unreliable predictions | Measure model performance and communicate limitations. |
| Limited connectivity | Design a lightweight, mobile-friendly interface. |
| User trust and adoption | Work with local agricultural communities and FPOs where possible. |
| Logistics complexity | Begin with a limited geographic area and clearly defined delivery workflows. |
| Operating costs | Track hosting, messaging, support, and order-processing costs. |

### Pilot Strategy

1. Select a limited region and a small number of crops.
2. Validate data availability for market prices and agricultural insights.
3. Develop the core crop-listing and buyer-discovery workflow.
4. Test with representative farmers and buyers.
5. Evaluate usability, successful orders, and operating costs.
6. Expand to additional crops and regions based on pilot results.

## Expected Impact

KisanChowk aims to support:

- Better access to agricultural information.
- Earlier identification of potential plant diseases.
- Improved awareness of available market prices.
- More informed irrigation and water-management decisions.
- Better access to potential buyers.
- Greater transparency in crop listings and transactions.
- More informed selling and procurement decisions.

These are intended outcomes. Actual benefits will need to be established through prototype testing and field evaluation.

## Evaluation Metrics

| Area | Evaluation Metric |
|---|---|
| Farmer earnings | Net earnings per kilogram after relevant costs |
| Market access | Number of active buyers and successful transactions |
| Price guidance | MAE and RMSE against an appropriate price reference |
| Disease detection | Precision, recall, F1-score, and confusion matrix |
| Irrigation | Water consumption and field-level recommendation outcomes |
| Order fulfilment | Successful delivery rate and delivery time |
| User engagement | Repeat orders and active users |
| Economic viability | Operating cost per order and repeat usage |

## Research and Data Sources

Potential sources to investigate during development include:

1. **AGMARKNET / Open Government Data Platform:** Agricultural mandi price data.
2. **e-NAM:** Information about electronic agricultural markets and trading processes.
3. **India Meteorological Department (IMD):** Weather information and agrometeorological advisories.
4. **Small Farmers' Agribusiness Consortium (SFAC):** FPO-related resources and guidance.
5. **PlantVillage and relevant research datasets:** Potential starting points for plant disease image experiments, subject to licensing and suitability.
6. **Agricultural research publications:** Methods for price forecasting, plant disease classification, irrigation, and crop management.

Data availability, access conditions, licensing, and suitability must be checked before using a source in the application.

## Project Structure

```text
KisanChowk/
├── frontend/           # React web application
├── backend/            # Node.js and Express APIs
├── ai-service/         # Python and FastAPI ML services
├── docs/               # Technical documentation
├── .gitignore
└── README.md
```

Additional files and directories will be added as implementation progresses.

## Roadmap

- [ ] Establish the React frontend and application navigation.
- [ ] Develop farmer and buyer interfaces.
- [ ] Implement crop listings and buyer discovery.
- [ ] Develop backend APIs and database integration.
- [ ] Integrate agricultural market-price data.
- [ ] Explore and evaluate plant disease classification.
- [ ] Investigate irrigation guidance using available data.
- [ ] Explore crop price and demand prediction.
- [ ] Implement negotiation and order management.
- [ ] Add delivery status and notification workflows.
- [ ] Evaluate usability, reliability, and model performance.
- [ ] Conduct a limited pilot and assess outcomes.

---

**KisanChowk — Your harvest, your market.**
