# 🤖 WhatsApp AI Customer Support & Appointment Booking Bot

![n8n](https://img.shields.io/badge/Built%20With-n8n-orange)
![OpenAI](https://img.shields.io/badge/AI-OpenAI-green)
![WhatsApp](https://img.shields.io/badge/API-WhatsApp%20Cloud-blue)
![Automation](https://img.shields.io/badge/Automation-Workflow-purple)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

An **AI-powered WhatsApp customer support automation** built with **n8n + OpenAI**.

This bot works as a **24/7 virtual assistant** that can:

- Answer product questions
- Book consultation appointments
- Manage calendar availability
- Handle voice messages
- Send automated email notifications
- Escalate issues to human support

Perfect for **businesses, clinics, beauty brands, consultants, and WhatsApp-based services.**

---

# 📑 Table of Contents

- Overview
- Features
- Demo Workflow
- Tech Stack
- System Architecture
- Installation
- Setup Guide
- Example Conversations
- Use Cases
- Future Improvements
- License

---

# 📌 Overview

This project creates a **fully automated AI customer support system on WhatsApp** using **n8n workflows**.

The AI assistant:

- Communicates like a human support agent
- Handles both **text and voice messages**
- Books appointments automatically
- Stores booking records
- Sends notifications to the business

Everything runs through **workflow automation** without needing a custom backend.

---

# 🚀 Features

## 🧠 AI Customer Support

The assistant can answer questions about:

- Hair oil benefits
- Hair oil usage
- Perfume information
- Product recommendations
- Pricing guidance

It responds naturally like a **human support agent**.

---

## 📅 Appointment Booking

Customers can book consultations directly via WhatsApp.

Automated process:

1. Ask consultation type
2. Ask preferred date
3. Ask preferred time
4. Check availability in Google Calendar
5. Confirm booking
6. Create calendar event
7. Save record in Google Sheets
8. Notify company via email
9. Optionally email the customer

---

## 🎤 Voice Message Support

Customers can interact using voice messages.

Workflow:

```

Voice Message
↓
Download Audio
↓
Transcribe (OpenAI)
↓
AI Response
↓
Generate Voice Reply
↓
Send Voice Message

```

---

## ❌ Appointment Cancellation

Customers can cancel appointments by providing:

- Date
- Time

The system will:

1. Find the event in Google Calendar
2. Confirm cancellation
3. Delete the event
4. Notify the customer

---

## 🧑‍💼 Human Support Escalation

If the user reports:

- Order issues
- Product reactions
- Complex requests

The AI:

1. Collects name
2. Confirms phone number
3. Collects issue details
4. Creates a support ticket

---

# 🛠 Tech Stack

| Tool | Purpose |
|-----|------|
| **n8n** | Workflow automation |
| **OpenAI** | AI assistant + voice transcription |
| **WhatsApp Cloud API** | Messaging platform |
| **Google Calendar** | Appointment scheduling |
| **Google Sheets** | Booking database |
| **Gmail API** | Email notifications |

---

# 🏗 System Architecture
            +----------------------+
            |  WhatsApp Cloud API  |
            +----------+-----------+
                       |
                       |
               WhatsApp Trigger
                       |
                       |
            +----------+-----------+
            |  Route Message Type  |
            +----------+-----------+
                       |                +----------------------+
                |  WhatsApp Cloud API  |
                +----------+-----------+
                           |
                           |
                   WhatsApp Trigger
                           |
                           |
                +----------+-----------+
                |  Route Message Type  |
                +----------+-----------+
                           |
        +------------------+------------------+
        |                                     |
   Text Message                         Voice Message
        |                                     |
        |                               Download Audio
        |                                     |
     AI Agent                           Transcribe Audio
        |                                     |
        |                               AI Voice Agent
        |                                     |
   Send Text Reply                      Generate Voice
                                              |
                                              |
                                       Send Voice Reply
    +------------------+------------------+
    |                                     |

# ⚙️ Installation

## 1️⃣ Install n8n

### Using Docker

```bash
docker run -it --rm \
-p 5678:5678 \
-e N8N_BASIC_AUTH_ACTIVE=true \
n8nio/n8n
````

### Using npm

```bash
npm install n8n -g
n8n start
```

---

# 📥 Import the Workflow

1. Open **n8n dashboard**
2. Click **Import Workflow**
3. Upload the workflow JSON file
4. Activate the workflow

---

# 🔑 Configure Credentials

You must connect these services inside n8n:

* WhatsApp Cloud API
* OpenAI API
* Google Calendar OAuth
* Google Sheets OAuth
* Gmail OAuth

---

# 🔗 WhatsApp Webhook Setup

Configure the **Meta WhatsApp Cloud API webhook** to use the **n8n webhook URL** generated by the WhatsApp Trigger node.

---

# 💬 Example Conversations

### Product Question

Customer:

```
How do I use your hair oil?
```

Bot:

```
Apply a small amount of oil to your scalp and massage gently for 5–10 minutes.

Leave it for at least 1 hour or overnight before washing.

Using it 2–3 times per week gives the best results.

Would you like a quick hair consultation?
```

---

### Appointment Booking

Customer:

```
I want to book a consultation
```

Bot:

```
Sure! Is this appointment for hair consultation or product guidance?
```

---

# 📊 Automation Capabilities

This system automatically:

* Responds to customer questions
* Books appointments
* Checks calendar availability
* Stores data in Google Sheets
* Sends email notifications
* Handles voice interactions
* Escalates support requests

---

# 🎯 Use Cases

This project is ideal for:

* Beauty brands
* Hair clinics
* Medical consultations
* Salons
* Service businesses
* WhatsApp-first startups
* AI customer support automation

---

# 🔮 Future Improvements

Potential upgrades:

* WhatsApp payments
* CRM integration
* Customer analytics dashboard
* Order tracking automation
* Multilingual support
* AI product recommendation engine

---

# 📄 License

MIT License

---

