# Community Engagement Workflow Automations

This document provides concrete instructions for setting up powerful automations to streamline your community management workflows using Trello, Google Workspace, and Discord.

## Google Sheets Dashboard Automations

### 1. Automatic Data Import from Trello

**Setup Instructions:**

1. Install the Trello Add-on for Google Sheets:
   - In your Community Dashboard Sheet, go to Extensions > Add-ons > Get add-ons
   - Search for "Trello" and install the official add-on

2. Create an import configuration:
   ```
   =IMPORTTRELLOCARD("Board ID", "List Name", "Optional Card Filter")
   ```

3. Set up recurring imports for key metrics:
   - In your sheet, go to Extensions > Trello > Schedule Refresh
   - Set daily imports of active cards from your experiment boards
   - Set weekly imports of completed cards for reporting

### 2. Conditional Formatting for Metric Monitoring

**Setup Instructions:**

1. Set up health indicators in your Executive Summary tab:
   - Select your KPI cells
   - Choose Format > Conditional Formatting
   - Create rules for:
     * Green (>=100% of target): Background #b7e1cd
     * Yellow (80-99% of target): Background #fce8b2
     * Red (<80% of target): Background #f4c7c3

2. Create trend indicators:
   - Select % change columns
   - Set conditional formatting:
     * Positive change: ▲ in green (#0f9d58)
     * Negative change: ▼ in red (#db4437)
     * No change: ◆ in gray (#7e7e7e)

### 3. Automated Weekly Report Generation

**Setup Instructions:**

1. Create a report template in Google Docs

2. Set up Apps Script automation:
   - In your Google Sheet, go to Extensions > Apps Script
   - Create a new script named "weeklyReportGenerator"
   - Paste this code:

```javascript
function generateWeeklyReport() {
  // Get the template
  var templateDoc = DocumentApp.openById('YOUR_TEMPLATE_DOC_ID');
  
  // Create a new doc for this week's report
  var newDoc = DocumentApp.create('PM Mentality Weekly Report - ' + new Date().toDateString());
  
  // Copy template content to new doc
  var body = newDoc.getBody();
  body.appendParagraph(templateDoc.getBody().getText());
  
  // Get data from the dashboard
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName('Executive Summary');
  var data = sheet.getRange('A1:F10').getValues();
  
  // Replace placeholders with actual data
  // [Implementation details would follow...]
  
  // Email the report to team
  var emailTo = "team@example.com";
  var subject = "Weekly PM Mentality Community Report";
  var emailBody = "This week's community report is attached.";
  var pdfReport = newDoc.getAs('application/pdf');
  
  GmailApp.sendEmail(emailTo, subject, emailBody, {
    attachments: [pdfReport]
  });
}
```

3. Set a time-based trigger:
   - In Apps Script, click Triggers > Add Trigger
   - Choose weekly execution on Friday afternoons

## Trello Workflow Automations

### 1. New Member Onboarding Automation

**Setup Instructions:**

1. In your Member Journey Trello board, click "Automation" > "Create Button"

2. Create a "New Cohort" button:
   - Name: "Create New Member Cohort"
   - Icon: 👋
   
3. Set the button actions:
   - Create a card in "New Member Cohort" list
   - Add a standardized checklist:
     * Send welcome messages
     * Create introduction thread
     * Schedule group orientation
     * First-week check-in
     * Add to resource access group

4. Set up a "When card is created in New Member Cohort" trigger:
   - Automatically assign to Community Engagement Specialist
   - Set due date for 1 week from creation
   - Add yellow "Onboarding" label

### 2. Experiment Pipeline Automation

**Setup Instructions:**

1. Create status change rules:
   - When card moves to "Currently Running":
     * Add "Start Date" to custom field with current date
     * Add standard "Monitoring" checklist
     * Send notification to team channel

2. Create measurement reminder:
   - When card has been in "Currently Running" for 7 days:
     * Add comment "Time for mid-experiment check-in"
     * Add yellow "Review Needed" label
     * Notify card owner

3. Create results documentation workflow:
   - When card moves to "Analysis Phase":
     * Add "Results Documentation" checklist:
       * Record final metrics
       * Document key findings
       * Identify next steps
       * Update experiment log in Google Sheet

4. Integration with dashboard:
   - When "Results" custom field is updated:
     * Run Zapier workflow to update Google Sheet
     * Create card in "This Week's Focus" on Community Management board to implement findings

### 3. Feedback Collection Automation

**Setup Instructions:**

1. Create recurring feedback cards:
   - Use Butler command:
     ```
     every Monday at 9:00 AM create card "Weekly Feedback Review" in list "Feedback Collection" with description "Gather and analyze this week's community feedback"
     ```

2. Set up issue escalation workflows:
   - When label "Critical Issue" is added to a card:
     * Move to top of "Blockers & Concerns" list
     * Add all board members as watchers
     * Send notification to leadership channel
     * Create calendar event for review within 24 hours

3. Configure feedback closure tracking:
   - When a card moves to "Insights & Actions":