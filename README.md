### Automated Support Ticket Processing System

## 📌  Introduction

Managing support tickets efficiently is critical for customer satisfaction. This project automates the ticket intake, categorization, and notification process to ensure tickets  receive immediate attention and also  tracking unresolved tickets.

 💡 **Why This System?**
Support teams often face these challenges:
- ❌ Manually reviewing and prioritizing tickets is inefficient.
- ❌ Urgent issues get delayed due to lack of automation.
- ❌ Tracking unresolved tickets is difficult without structured reporting.
- ❌ Tickets can get lost or delayed especially high-prioriy ones.


**Handling support tickets manually** can be time-consuming and prone to delays. This project solves these challenges by automating:
- ✅ Ticket submission via Google Forms
- ✅ Categorization based on priority keywords
- ✅ Immediate email and Slack notifications for critical tickets
- ✅ End-of-day summary reports for unresolved tickets
With this workflow automation, urgent issues get immediate attention while unresolved tickets are flagged for follow-up.

## 🛠️ Tech Stack  

| Tool                     | Purpose                                      |  
|--------------------------|----------------------------------------------|  
| **Make.com**             | No-code automation platform                 |  
| **Google Forms**         | Captures ticket submissions                 |  
| **Google Sheets**        | Stores and tracks ticket data               |  
| **Text Parser (Make.com)** | Extracts keywords to determine priority     |  
| **Google Apps Script** (Optional) | Automates additional data processing if needed |  
| **Slack API (via Make.com)** | Sends real-time notifications to relevant channels |  
| **Email Notifications (via Make.com)** | Sends automated responses to customers |  

## ⚙️ How It Works
1️⃣ **Trigger:** Ticket Submission (Google Form)
A customer submits a Google Form when they have an issue.
The response is stored in Google Sheets automatically.

2️⃣ **Data Processing & Categorization**
A Text Parser scans the ticket description and determines priority:
- High Priority → Contains words like “urgent” or “critical.”
- Medium Priority → Contains words like “issue” or “bug.”
- Low Priority →contains word like                , typically indicating general inquirires.These are ofte questions already covered in the FAQ,
   making them suitable for self-service resolution.

3️⃣ **Automated Actions**
 
 - **High-Priority Tickets:** For high-priority tickets, a personalized email is sent to the customer immediately, assuring them that a ticket has been created and its already being looked into.

 **Email to Customer:**

"Hello {{First Name}}  {{Last Name}},

Thank you for reaching out to our support team. A ticket has been created for your request, and we’re already looking into it. We sincerely apologize for any inconvenience this may have caused.

To help us resolve your issue as quickly as possible, could you please provide the following details?

A brief description of the issue

Any error messages you’re seeing (if applicable)

Steps you’ve already tried to resolve it

Our team is on it, and we’ll keep you updated every step of the way. If you have any additional details to share, feel free to reply to this email.

We appreciate your patience and will do our best to resolve this as quickly as possible.

Best regards,"

**Slack Alert to Support Team:** Once the ticket has been created,details of the ticket is sent to high-priority slack channel.

- **Medium-Priority Tickets:** For medium-priority tickets a personalized email is sent to the customer immediately, assuring them that a ticket has been created and its already being looked into.


**Email to Customer:** 

"Hello {{First Name}}  {{Last Name}},

Thank you for reaching out to our support team. A ticket has been created for your request, and we’re already looking into it. We sincerely apologize for any inconvenience this may have caused.

To help us resolve your issue as quickly as possible, could you please provide the following details?

A brief description of the issue

Any error messages you’re seeing (if applicable)

Steps you’ve already tried to resolve it

Our team is on it, and we’ll keep you updated every step of the way. If you have any additional details to share, feel free to reply to this email.

We appreciate your patience and will do our best to resolve this as quickly as possible.

Best regards,"


**Slack Notification:** Once the ticket has been created,details of the ticket is sent to medium-priority slack channel.


**Low-Priority Tickets:**
When a low-priority ticket is detected, an automated email response is sent, providing a link to the FAQ or relevant help articles. This ensures users
receive quick assiatance while reducing the need for manual support intervention.


4️⃣ End-of-Day Report for Unresolved Tickets
⏰ At the end of the workday, the automation:

Filters all unresolved tickets from Google Sheets.

Sends a summary to Slack (e.g., “🚨 5 Unresolved Tickets Today”).





