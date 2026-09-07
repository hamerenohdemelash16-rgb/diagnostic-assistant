# Community Health Triage Assistant

A tool that helps people check their symptoms and get guidance on 
whether they should manage things at home or see a doctor.

## What it does

You pick the symptoms you're feeling from a checklist (respiratory and 
skin symptoms), and it gives you a guidance level: Low, Moderate, or 
High, along with advice on what to do next.

## What happened while building it

While building the logic that checks for urgent "red flag" symptoms 
(like difficulty breathing), I hit this error: 
`Uncaught ReferenceError: hasRedFlag is not defined`. It happened because 
I was trying to use a variable in an `if` statement before actually 
creating it anywhere in the code. I fixed it by first declaring 
`let hasRedFlag = false`, then writing a loop that checks every selected 
symptom — if any of them is marked as a red flag, it sets `hasRedFlag` 
to `true`. Only after that loop finishes does the code check the result.

## How it works

- Certain symptoms (like difficulty breathing or chest pain) are marked 
  as "red flags" — if any of these are selected, the result is 
  immediately High, no matter what else is picked
- If there's no red flag, the app adds up a weight number for each 
  selected symptom into a total score, and uses that total to decide 
  Low, Moderate, or High

## Tech used

- Vanilla HTML/CSS/JavaScript
- No external APIs or libraries — the logic runs entirely in the browser

## Why this isn't real photo-based diagnosis

The original idea for this kind of project involved analyzing photos of 
skin conditions using computer vision. That requires training data and a 
real machine learning model, which wasn't realistic for me to build. 
Instead, this version uses a symptom checklist with weighted scoring and 
red-flag rules, which is simpler but still gives useful, explainable 
guidance.

## What's working / what's not built yet

Working: symptom selection, red-flag override logic, weighted scoring, 
and a guidance result with advice.

Not built yet: actual photo-based symptom analysis, more symptom 
categories beyond respiratory and skin, and multi-language support.