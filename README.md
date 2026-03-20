# GigGuard

## Problem Statement

India's grocery delivery workers (Zepto, Blinkit, etc.) face significant income loss during external disruptions such as heavy rain, extreme heat, pollution spikes, and local curfews. These workers operate on a weekly earning cycle and lack a financial safety net when uncontrollable events reduce their working hours.

---

## Persona-Based Scenarios

### Scenario 1: Weather Disruption
Rahul, a Blinkit delivery partner in Mumbai, works 6 days a week. During a heavy rainstorm (200mm in 2 hours), he cannot make deliveries for 3 days. His weekly income drops by 40%, resulting in a loss of ₹2,000.

### Scenario 2: Social Unrest
Priya, a Zepto delivery partner in Delhi, works in a zone that gets suddenly closed due to local strikes. She cannot access pickup/drop locations for 5 days, losing her entire weekly income of ₹3,500.

### Scenario 3: Pollution Impact
Amit, working in Bengaluru, cannot deliver during severe pollution days when AQI exceeds 400. His delivery hours are reduced by 60%, causing significant income loss.

---

## Application Workflow

1. Worker Registration: Sign up via mobile app with location and delivery zone  
2. Coverage Setup: Select weekly premium based on risk factors  
3. Real-Time Monitoring: Track weather, social events, and disruptions  
4. Claim Trigger: Automated detection of disruptions  
5. Payout Processing: Instant compensation  
6. Dashboard: Coverage status and claim history  

---

## Weekly Premium Model

Base Premium: ₹120/week

### Risk Adjustments
- High-risk zones: +₹30/week  
- Moderate-risk zones: +₹15/week  
- Low-risk zones: -₹10/week  

### Dynamic Pricing Factors
- 7-day weather forecast  
- Historical disruption data  
- Seasonal risks  
- Traffic patterns  

Example: Worker in Mumbai (high-risk) with 30% rain probability → ₹150/week

---

## Parametric Triggers

### Weather-Based
- Rainfall > 20mm in 24 hours  
- Temperature > 40°C for 3 consecutive days  
- AQI > 300 for 2+ consecutive days  
- Wind speed > 60 km/h  

### Social Disruptions
- Local curfew announcements  
- Strikes or protests  
- Platform outages  
- Traffic restrictions  

---

## Technical Implementation

All triggers are monitored via real-time APIs:
- Weather services  
- Government data sources  
- Delivery platform status  

---

## Platform Choice: Mobile Application

### Rationale
- Workers are mobile-first users  
- Requires real-time tracking  
- Enables instant alerts and claims  
- Supports GPS-based validation  

### Features
- Real-time disruption alerts  
- Quick claim submission  
- Weekly dashboard  
- Payout history  
- Policy management  

---

## AI/ML Integration

### 1. Dynamic Premium Calculation
Model: Random Forest + Linear Regression  

Features:
- Historical weather patterns  
- Delivery routes  
- Seasonal risk factors  
- Platform activity  

---

### 2. Fraud Detection System

Components:
- GPS pattern analysis  
- Activity validation  
- Duplicate prevention  
- Anomaly detection  

Models:
- Isolation Forest  
- Clustering algorithms  
- Time-series analysis  

---

### 3. Predictive Risk Modeling

Models:
- LSTM for weather prediction  
- Classification models for disruptions  
- Regression models for income loss  

Data Sources:
- Historical weather data  
- Social media signals  
- Government APIs  
- Platform data  

---

## Adversarial Defense & Anti-Spoofing Strategy

### Overview

The system replaces GPS-only verification with a multi-layered behavioral validation framework. A dynamic Trust Score determines claim legitimacy.

---

### 1. Differentiation: Real Worker vs Spoofer

Trust Score Model:

Trust Score =  
  w1 * GPS Consistency +  
  w2 * Motion Data +  
  w3 * Network Signals +  
  w4 * App Activity +  
  w5 * Zone Correlation  

Claims are auto-approved only if the Trust Score exceeds a threshold.

---

### Genuine Worker Indicators
- Continuous and natural movement patterns  
- Route consistency with delivery zones  
- Active app usage  
- Network instability matching real weather  

---

### Fraud Indicators
- GPS teleportation or unrealistic jumps  
- Static location during working hours  
- Identical patterns across multiple users  
- No delivery platform interaction  
- Stable network during extreme weather  

---

### 2. Data Signals Beyond GPS

#### Device-Level Signals
- Accelerometer and gyroscope data  
- App foreground activity  
- Battery usage patterns  
- Root/jailbreak detection  

---

#### Network Signals
- IP and GPS location consistency  
- Latency and packet loss patterns  
- Sudden IP changes  

---

#### Environmental Correlation
- Matching API weather data with device/network behavior  
- Detect inconsistencies between reported conditions and actual signals  

---

#### Behavioral Patterns
- Historical delivery routes  
- Typical working hours  
- Delivery activity logs  

---

### Fraud Ring Detection

The system detects coordinated attacks using:
- DBSCAN clustering  
- Graph-based anomaly detection  

Patterns analyzed:
- Identical GPS traces  
- Synchronized claim timing  
- Shared network signatures  

---

### 3. UX Balance

#### High Trust
- Instant claim approval (<5 seconds)

#### Medium Risk
- Soft verification (user confirmation prompt)  
- Partial payout (50–70%)  
- Remaining payout after validation  

#### High Risk
- Claim temporarily held  
- User notified clearly  
- No immediate rejection  

---

### Fail-Safe Mechanisms
- Historical trust weighting  
- Crowd-based validation  
- Manual review fallback  

---

### Key Insight

The system verifies behavioral consistency instead of relying solely on GPS accuracy.

---

## Tech Stack

### Frontend
- React Native  
- Redux Toolkit  

### Backend
- Node.js with Express  
- MongoDB  
- Socket.io  

### AI/ML
- Python (Scikit-learn, TensorFlow)  
- Flask APIs  
- AWS Lambda  

---

### APIs
- OpenWeatherMap  
- Google Maps  
- Government APIs  
- Razorpay  

---

### DevOps
- Git and GitHub  
- GitHub Actions  
- Jest  
- Sentry  
- Swagger  

---

## Development Plan

### Phase 1: Foundation
- Documentation and repo setup  
- UI/UX design  
- API integration planning  
- Initial ML architecture  

### Phase 2: Core Features
- Mobile app development  
- Premium calculation  
- Claim system  
- Initial ML deployment  

### Phase 3: Automation
- Real-time monitoring  
- Automated triggers  
- Fraud detection  
- Payment integration  

### Phase 4: Advanced Features
- Improved ML models  
- Analytics dashboard  
- Performance optimization  

### Phase 5: Final Integration
- Full system integration  
- Testing  
- Demo and pitch preparation  

---

## Success Metrics

- Coverage accuracy: 90%+  
- Claim processing time: <5 seconds  
- Fraud detection rate: >95%  
- User adoption: 80%+  
- Premium accuracy deviation: <10%  

---

## Risk Mitigation

### Technical Risks
- API limitations → mock data fallback  
- ML performance → fallback systems  
- Device compatibility testing  

### Business Risks
- Low adoption → improved UX  
- Premium mispricing → continuous retraining  
- Fraud → continuous monitoring  

---
