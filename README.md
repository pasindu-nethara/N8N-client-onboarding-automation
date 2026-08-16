# Client Onboarding Automation
 
n8n workflow that automates client onboarding after a Typeform submission.
 
## What It Does
 
1. Client fills a Typeform (name, company, email, services).
2. Creates a client page in Notion with service checklist.
3. Creates a Google Drive folder with subfolders (Briefs, Deliverables, Reports).
4. Creates a private Slack channel and invites the team.
5. Sends a Slack summary with all links.
6. Uses Google Gemini (LLM Chain) to write a welcome email.
7. Sends the welcome email to the client via Gmail.
## Workflow Diagram
 
![Workflow]()
 
## Nodes Used
 
| Step | Node | Service |
|------|------|---------|
| Trigger | Typeform Trigger | Typeform |
| Data | Edit Fields | n8n |
| Notion Page | Create a database page | Notion |
| Services List | Split Out → Code → Append a block | Notion |
| Drive Folders | Create folder → Split Out → Create folder1 | Google Drive |
| Slack Channel | Code → Create a channel → Invite a user | Slack |
| Notify | Merge → Aggregate → Send a message | Slack |
| Email Draft | Basic LLM Chain + Gemini + Structured Output Parser | Google Gemini |
| Send Email | Send a message1 | Gmail |
 
## Setup
 
1. Import `Client_Onboarding_Automation.json` into n8n.
2. Connect credentials:
   - Typeform
   - Notion
   - Google Drive
   - Slack (OAuth2)
   - Google Gemini (PaLM API)
   - Gmail
3. Update the Notion database ID and Slack invite user ID.
4. Activate the workflow.
## Tech Stack
 
n8n, Typeform, Notion, Google Drive, Slack, Google Gemini, Gmail.
