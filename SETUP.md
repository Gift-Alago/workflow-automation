## How to Set Up the [Support Ticket Workflow-Automation] in Make
### Overview
This workflow automates the process from a submitted Google Form through various actions like parsing, updating Google Sheets, sending emails via Gmail, and notifying on Slack. This is useful for managing ticket responses, categorizing them, and automating follow-ups.

**Before we dive into the setup, here’s what the complete workflow looks like in Make:**
 
 ![Google form](./assets/test-auto.png)

This gives you a sense of how the modules are connected — from Google Forms, through Sheets and routers, all the way to Gmail and Slack. We’ll break this down step by step below.

# Tools Used
- Google Forms
- Google Sheets
- Make (Integromat)
- Gmail
- Slack
- Text Parser

##   1. Trigger: Google Forms Submission
- Module: Google Forms → Watch Responses
- This starts the scenario when someone submits a response.

##  2. Log Response in Google Sheets
- Module: Google Sheets → Add Row
- The response data is stored here for record-keeping

 **Example:** Create a Google Sheet with required columns:

- First Name

- Last Name

- Contact

- Email

- Ticket subject

- Issue Description

- Priority

- Resolved

- Unresolved

- Date

## 3. Router
-  Module: Router
- Splits the flow based on conditions or logic (eg;the row number doesn't or does exist; that means if the ticket has been logged before if goes to the first route (add to row) if otherwise if goes to the next(update row) ).

## 4. Text Parser (Multiple Paths)
- Module: Text Parser (Custom Text / Keywords / Conditions)
- Used to extract specific information or categorize responses.

**Example:It detect keywords from the issue description, and determines the priority for each of the paths**
- High Priority → Contains words like "not working", "urgent", "site is down", or "can't access".
- Medium Priority → Contains words like "error", "broken", "glitch", or "not displaying correctly".
- Low Priority → Contains word like "how", "setup", "request", "feedback", or "question", typically indicating general inquiries.These are often questions already covered in the FAQ, making them suitable for self-service resolution.


 ## 5. Google Sheets Updates 
- Module: Google Sheets → Update Cell(s)
- Used to update a row that  exist already

  **Example:** if a customer creates a ticket and it probably hasn't been resolved and then they create another ticket for the same issue, the row will be updated instead of added to avoid duplicates

 ## 6. Gmail: Send Follow-up 
- Module: Gmail → Send Email
- After logging and parsing, this module sends an automated follow-up to the user.

 **Example:**
- Once a customer creates a ticket, an email is sent to them assuring them that they are being heard and the issue 
  is being addressed.

 ## 7. Slack Notification
- Module: Slack → Send Message
- Sends summary or  alert to a Slack channel for high priority tickets and unresolved tickets

 **Example:**
  - When a high priority ticket is detected the team gets an alert in the slack channel,to enable immediate approach as a 
  team.
  - After the days work, list of unresolved tickets are sent to another slack channel to notify team members so  they start the next day resolving those tickets as quickly as possible.

  ## How to Customize
- Text Parser: Adjust the conditions/keywords based on your use case.
- Router: You can add more branches if you want to handle different kinds of responses differently.
- Gmail/Slack: Customize the message templates and recipients.

  ## Run Settings
- Schedule:runs Every 15 minutes
- For unresolved ticket, runs after work hours eg; 5:00pm

  ## Tips
- Use variable names that match the form questions for clarity.
- Test each module one at a time to catch errors early.
- Label each module in Make to avoid confusion when troubleshooting.






