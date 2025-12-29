AI Smart Tutor — Adaptive Quiz System
=====================================

Project Overview
----------------
Implementation of a rule-based adaptive tutoring system that dynamically adjusts quiz difficulty and learning recommendations based on individual student responses. 

The system analyzes correctness, skipped questions, and concept-level misunderstandings to generate personalized feedback and next-step recommendations.

This tutor is a proof-of-concept for adaptive learning systems used in modern education platforms.


System Architecture
-------------------
The system is implemented using:

- Google Forms for student input
- Google Sheets as a state store
- Google Apps Script as the decision engine

An onFormSubmit trigger evaluates responses in real time and generates a personalized mastery report for each student.


Adaptive Logic
--------------
Each quiz question is mapped to a concept and expected answer using a centralized configuration object.

Decision rules:

- If a question is skipped due to conditional branching, it is excluded from scoring.
- If an answer is correct, points are awarded.
- If an answer is incorrect, the associated concept is flagged for review.
- Mastery percentage is recalculated using only attempted questions.

This ensures fair scoring even when question paths vary between students.


Student Modeling & Mastery Calculation
--------------------------------------
The system independently calculates:

- Questions attempted
- Points earned
- Adjusted mastery percentage
- Missed concepts

This avoids relying on Google Forms’ default scoring, which does not account for conditional logic.


Personalized Feedback
---------------------
For each student, the system generates:

- A mastery summary card
- A "Next Steps" recommendation
- A targeted review tip tied to the first missed concept
- A detailed per-question breakdown

Recommendations adapt based on mastery level:

- High mastery → "Level Up"
- Lower mastery → "Review & Retry"


Limitations & Future Work
-------------------------
- The current implementation uses rule-based logic rather than machine learning.

Future versions could incorporate:

- Predictive difficulty modeling
- Reinforcement learning
- Longitudinal student performance tracking

The current structure intentionally mirrors early-stage adaptive systems before ML integration.

