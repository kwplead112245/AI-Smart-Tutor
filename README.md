# AI Smart Tutor — Adaptive Quiz System

**Rule-based intelligent tutoring system with real-time difficulty adaptation and personalized learning paths**

[![Python](https://img.shields.io/badge/Google_Apps_Script-4285F4?style=flat&logo=google&logoColor=white)](https://developers.google.com/apps-script)
[![Status](https://img.shields.io/badge/Status-Complete-success)](https://github.com/kwplead112245/AI-Smart-Tutor)

---

## Demo Videos

### System Overview & Adaptive Logic
https://github.com/user-attachments/assets/5665ca1f-30c9-4fdc-92d3-0d3bf2208718

### Personalized Feedback Generation
https://github.com/user-attachments/assets/4688652e-307a-468c-8916-2ad65eb6da47

---

## Project Overview

An intelligent adaptive learning system that dynamically personalizes quiz difficulty and generates targeted learning recommendations based on real-time analysis of student performance. The system implements conditional logic, concept-level diagnostics, and automated feedback generation—core components of modern EdTech platforms.

**Key Innovation:** Unlike traditional quiz systems that rely on simple scoring, this tutor implements branching logic with state-aware scoring that accounts for conditional question paths, ensuring fair and accurate mastery assessment regardless of individual learning trajectories.

---

## System Architecture

```
Student Input (Google Forms)
        ↓
Real-time Trigger (onFormSubmit)
        ↓
Decision Engine (Apps Script)
        ↓
State Store (Google Sheets)
        ↓
Personalized Report Generation
```

**Technology Stack:**
- **Google Forms**: Dynamic quiz interface with conditional branching
- **Google Sheets**: Centralized data store for responses and configurations
- **Google Apps Script**: Server-side JavaScript execution engine
- **Event-Driven Architecture**: Real-time processing via form submission triggers

---

## Adaptive Intelligence & Decision Logic

### Question-Concept Mapping
Each quiz item maps to underlying learning concepts using a centralized configuration object, enabling concept-level performance tracking beyond simple question scoring.

### Multi-Factor Decision Rules

The system evaluates student responses using compound logic:

1. **Conditional Path Handling**
   - Questions skipped due to branching logic are excluded from denominator
   - Prevents penalization for questions student never encountered
   - Ensures mastery calculation reflects actual attempted content

2. **Performance Scoring**
   - Correct answer → Points awarded + concept mastery confirmed
   - Incorrect answer → Concept flagged for targeted review
   - Skipped question → Excluded from mastery calculation

3. **Dynamic Mastery Recalculation**
   ```
   Adjusted Mastery = (Points Earned / Questions Attempted) × 100
   ```
   This approach handles variable question paths that traditional scoring cannot accommodate.

### Student Performance Modeling

The system independently calculates multi-dimensional performance metrics:

| Metric | Purpose |
|--------|---------|
| Questions Attempted | Normalizes scoring across different quiz paths |
| Points Earned | Raw performance measurement |
| Adjusted Mastery % | Path-normalized achievement score |
| Missed Concepts | Diagnostic data for personalized recommendations |

**Why Independent Calculation Matters:**  
Google Forms' native scoring cannot handle conditional logic. This system implements custom analytics to ensure accuracy and fairness.

---

## Personalized Feedback Engine

### Automated Report Generation

For each student submission, the system generates:

**1. Mastery Summary Card**
- Overall performance score
- Questions attempted vs. total possible
- Concept mastery breakdown

**2. Adaptive Next Steps**
Based on performance thresholds:
```
if (mastery >= 80%) → Recommendation: "Level Up - Advanced Content"
else if (mastery >= 60%) → Recommendation: "Review & Retry - Targeted Practice"
else → Recommendation: "Fundamentals Review - Core Concepts"
```

**3. Targeted Review Guidance**
- First missed concept identified
- Specific study recommendation tied to weakness
- Concept-specific resources or explanations

**4. Detailed Question Breakdown**
- Per-item analysis
- Correct/incorrect flagging
- Concept association for each question

---

## Technical Highlights

### Data Processing & Analytics
- Real-time event-driven processing
- Multi-dimensional performance metrics
- Conditional logic handling in scoring algorithms
- Automated report generation from structured data

### System Design Principles
- **Decoupled Architecture**: Separates input (Forms), logic (Apps Script), and storage (Sheets)
- **State Management**: Centralized configuration enables easy content updates
- **Fair Assessment**: Path-aware scoring accommodates personalized quiz flows
- **Scalability**: Event triggers handle concurrent submissions

### Skills Demonstrated
- Algorithm design for adaptive systems
- Data modeling and state management
- Automated analytics and reporting
- Event-driven programming
- Educational technology application
- User experience personalization

---

## Implementation Notes

### Rule-Based vs. Machine Learning

This system intentionally uses **rule-based logic** rather than ML, mirroring early-stage adaptive systems architecture:

**Current Approach (Rule-Based):**
- Deterministic, explainable decisions
- No training data required
- Immediate deployment
- Transparent logic for educational settings
