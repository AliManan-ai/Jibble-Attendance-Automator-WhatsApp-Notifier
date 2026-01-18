# Jibble-Attendance-Automator-WhatsApp-Notifier
An automated n8n workflow that monitors Jibble attendance data in real-time and sends WhatsApp alerts for missed clock-ins, forgotten clock-outs, and irregular shift durations.
🚀 Jibble Attendance Automation System
This project is a robust n8n workflow designed to streamline HR operations by automating attendance tracking and notifications. It integrates the Jibble API, Google Sheets, and WhatsApp to ensure accurate attendance records and reduce manual follow-ups.

📋 Overview
Managing employee attendance manually is prone to errors and forgetfulness. This system runs on a schedule to perform three critical checks:

Absenteeism Check: Identifies employees who haven't clocked in by a specific time.

Clock-Out Reminder: Reminds employees who are still clocked in after office hours.

Anomaly Detection: Flags shifts that are suspiciously short (e.g., accidental double clicks resulting in <30 min shifts).

✨ Key Features
** automated WhatsApp Alerts:** Sends personalized messages directly to employees via WhatsApp using their registered phone numbers.

Dynamic Phonebook: Fetches employee contact details dynamically from a Google Sheet, allowing for easy updates without touching the code.

Smart "Fuzzy" Matching: Matches Jibble names to Google Sheet names even with slight formatting differences (e.g., "Ali Manan" vs "ali manan").

Timezone Aware: Hardcoded for Asia/Karachi (PKT) to ensure accurate reporting regardless of server location.

Error Handling: Includes debug logs and sticky notes within the workflow for easy maintenance.
🛠️ Tech Stack
Workflow Engine: n8n

Attendance Data: Jibble API

Database: Google Sheets (for Employee Name ↔ Phone Number mapping)

Notifications: WhatsApp (via WAWP/Custom API)

Language: JavaScript (ES6+ for data transformation nodes)

🚀 Installation & Setup
Import Workflow:

Download the jibble_auto_cleaned.json file from this repository.

Open your n8n instance, go to Workflows > Import from File, and select the JSON.

Configure Credentials:

Jibble API: Open the HTTP Request nodes (Nodes 1, 3, 4) and replace client_id and client_secret with your Jibble API credentials.

WhatsApp API: Open the final HTTP Request nodes (Nodes 6, 7, 8) and update the instance_id and access_token in the JSON Body.

Setup Google Sheet:

Create a Google Sheet with two columns: Name and Number (International format, e.g., 923001234567).

Connect your Google Drive account to n8n and select this file in the Download file nodes.
