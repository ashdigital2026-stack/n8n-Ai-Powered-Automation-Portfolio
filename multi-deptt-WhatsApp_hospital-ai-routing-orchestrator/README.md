# 🏥 Production-Grade Enterprise HMS AI Agentic Orchestrator (n8n + WhatsApp)

> **A multi-department, token-optimized AI Agent Orchestrator built on n8n for enterprise Hospital Management Systems (HMS). Operating via a single WhatsApp endpoint, it routes patients across multi-specialty clinical departments, manages real-time doctor availability, automates lab workflows, and handles bookings at ultralow API execution cost ($1 per 100 bookings).**

---

### 🎥 Demonstration & Walkthrough
* 📺 **YouTube Video Walkthrough:** [Watch Enterprise HMS System Demo](https://www.youtube.com/watch?v=wX4CrO3cBFc)
* 📁 **Parent Router Workflow:** `parent_workflow.json`
* 🖼️ **Parent System Architecture:** `parent_workflow_screenshot.png`

---

### 💡 The Problem
Large multi-specialty clinics and hospitals manage thousands of multi-department patient interactions daily across clinical bookings, lab tests, doctor availability updates, and payment confirmations. Traditional WhatsApp bots are either rigid decision trees or unoptimized LLM flows that consume thousands of unnecessary tokens, leading to high API costs, slow response times, and frequent scheduling overlaps.

### ⚙️ The Solution
An enterprise-grade **Router-Worker Multi-Agent Architecture** running on n8n. A lightweight parent orchestrator intercepts all incoming WhatsApp messages, presents an interactive exchange menu, and dynamically routes patients to isolated, specialized micro-workflows (Appointments, Rescheduling, Cancellations, Lab Inquiries, Admin). The entire system is engineered for extreme token efficiency, privacy compliance (no cross-session medical history retention), and low-cost model execution.

---

### 💰 Cost Efficiency & Performance Engineering
* **Ultra-Low Execution Cost:** Process ~100 complete bookings for **$1** or 1,000 bookings for **~$10** using optimized prompt structures and efficient model selection.
* **Token Preservation Architecture:** Isolates department contexts so heavy medical prompts are only invoked when a user enters that specific sub-workflow.
* **Hybrid Voice/Text Native Handling:** Gracefully ingests voice notes and text inputs while responding in crisp, formatted text messages (supporting English & Roman Urdu).

---

### 🌟 Key System Modules & Features

#### 1. Interactive Central Exchange (Parent Router)
Single WhatsApp number routing system displaying an interactive service menu on initial contact:
1. 🗓️ New Appointment Booking
2. 🔄 Reschedule Appointment
3. ❌ Cancel Appointment
4. 🧪 Lab Test Info
5. 🔬 Book Appointment for Procedure / Lab Test
6. 💬 General Query

#### 2. Dynamic Doctor Availability & Admin Management
* **Single-Message Non-Availability Updates:** Busy doctors can send a single WhatsApp message (e.g., *"Not available tomorrow"* or *"Not available on Monday"*). The AI automatically identifies the doctor's department and updates the availability database.
* **Auto-Reset Logic:** Automatically purges non-availability statuses daily after 6:00 PM to ensure accurate availability lookup for upcoming days.

#### 3. Multi-Specialty Clinical Appointment Management
* **Smart Triage & Specialist Matching:** Inquires about patient symptoms, suggests appropriate departments (Cardiology, Neurology, Gastroenterology, Gynecology, etc.), and matches them with available specialists along with fee structures.
* **Duplicate Prevention & Conflict Check:** Performs live phone number lookups to prevent duplicate bookings while dynamically checking Google Calendar slots to show only open appointment windows.
* **Full Lifecycle Sync:** Handles bookings, modifications, and cancellations across department-specific **Google Calendars** and **Google Sheets**, sending daily automated reminders to scheduled patients.

#### 4. Automated Laboratory & Diagnostic Suite
* **Procedure vs. Walk-In Intelligence:** Automatically differentiates between walk-in blood tests and high-preparation procedures (e.g., Endoscopy requiring advance booking).
* **One-Click Desk Automation:**
  * **Payment Receipt:** Desk staff click *"Paid"* in Google Sheets $\rightarrow$ System sends instant payment receipt with Reference ID via WhatsApp.
  * **Sample Collection:** Desk staff click *"Yes"* $\rightarrow$ Patient receives real-time sample collection confirmation.
  * **PDF Report Delivery:** Desk staff set status to *"Ready"* $\rightarrow$ System automatically attaches and sends the test report PDF to the patient on WhatsApp.

---

### 🛠️ Tech Stack & Integrations
* **Orchestration:** n8n (Parent Router + Specialized Sub-Workflows)
* **Messaging Channel:** WhatsApp Cloud API
* **AI Engine & STT:** OpenAI (Whisper STT / Optimized Chat Models)
* **Databases & Schedulers:** Google Calendar API, Google Sheets API, Custom Webhooks

---

### 📁 Modular Workflow Files & Architecture Diagrams

| Module | Workflow JSON File | Architecture Diagram |
| :--- | :--- | :--- |
| **Parent Orchestrator** | `parent_workflow.json` | `parent_workflow_screenshot.png` |
| **New Appointment Booking** | `new_apt_booking_workflow.json` | `new_apt_screenshot.png` |
| **Rescheduling System** | `Rescheduling_123_workflow.json` | `resheduling_screenshot.png` |
| **Cancellation System** | `Cancelling_123_workflow.json` | `cancelling_screenshot.png` |
| **Lab Diagnostics & Booking** | `Lab_456_workflow.json` | `lab_test_apt_screenshot.png` / `laboratory_info_screenshot.png` |
| **AI Receptionist Agents** | `Receptionist_123_workflow.json` / `Receptionist_456_workflow.json` | `Receptionist_123_screenshot.png` |

---

### 📷 System Architecture Overview
![Parent Router Architecture](./parent_workflow_screenshot.png)
