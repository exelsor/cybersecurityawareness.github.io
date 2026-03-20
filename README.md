# Cybersecurity Awareness Week 2026

Live Demo
https://exelsor.github.io/cybersecurityawareness.github.io/

---

## Overview

This web-based event registration platform was built to collect participants data for the  cybersecurity awareness week.

The platform allows users to:

* Register for the event
* Submit personal and survey data
* Learn about Exelsor Projects Limited

The system connects directly to Google Sheets for real-time data collection.

---

## Why This Project Was Built

Many individuals and small organizations lack awareness of cybersecurity risks.

This project solves three problems:

* Data collection for event participants
  Organizers need structured participant data for planning and follow-up

* Low-cost deployment
  No server required. Uses Google Apps Script and GitHub Pages

---

## Features

* Clean and responsive UI
* Mobile-first design
* Real-time form submission
* Google Sheets integration
* About page for organization profile
* Social media integration

---

## Project Structure

```
cybersecurityawareness.github.io/
│
├── index.html        # Main landing page and registration form
├── about.html        # About Exelsor Projects Limited
├── assets/
│   ├── logo.png
│   ├── cybersecurity-bg.jpg
│   └── favicon.ico
│
└── README.md
```

---

## Frontend Structure

Built with:

* HTML5
* CSS3
* Vanilla JavaScript
* Font Awesome (icons)
* Google Fonts

Key Sections:

* Header
  Fixed navigation with logo and CTA button

* Hero Section
  Background image with overlay and event messaging

* Registration Form
  Collects user data and sends to backend

* Footer
  Social media links and branding

---

## Backend Structure

The backend uses Google Apps Script.

### Flow

1. User submits form
2. JavaScript sends POST request
3. Google Apps Script receives data
4. Data is stored in Google Sheets

### Apps Script Code

```
function doPost(e) {

  var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Sheet1");

  sheet.appendRow([
    new Date(),
    e.parameter.fullname,
    e.parameter.email,
    e.parameter.phone,
    e.parameter.gender,
    e.parameter.age,
    e.parameter.role,
    e.parameter.organization,
    e.parameter.training,
    e.parameter.concern,
    e.parameter.linkSafety,
    e.parameter.scamVictim,
    e.parameter.source,
    e.parameter.consent
  ]);

  return ContentService
    .createTextOutput(JSON.stringify({result:"success"}))
    .setMimeType(ContentService.MimeType.JSON);
}
```

---

## Deployment

Frontend

* Hosted on GitHub Pages

Backend

* Deployed as Google Apps Script Web App
* Access set to "Anyone"

---

## How to Use

1. Open the live link
2. Fill the registration form
3. Submit
4. Data is saved automatically in Google Sheets

---

## Future Improvements

* Email confirmation after registration
* Admin dashboard for analytics
* Data validation and spam protection
* Export reports

---

## Developer

Name: Calistus

Organization: Exelsor Projects Limited

---

## License

This project is open for learning and educational purposes.
