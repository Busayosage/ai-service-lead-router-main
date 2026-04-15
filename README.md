# AI Service Lead Router – Multi-channel Customer Engagement Automation

## Short Overview
This project automates the routing of incoming service leads to the correct communication channel based on customer preference. It combines Make.com scenario orchestration with Airtable, Vapi voice assistants, WhatsApp Business API and Slack to ensure each lead is engaged quickly and consistently.

## Business Problem
Service businesses receive leads through web forms or other channels and need to respond promptly. Without an automated workflow, leads may be delayed, misrouted or handled inconsistently, leading to poor customer experience and lost opportunities. A flexible system is needed to manage lead contact preferences and trigger the appropriate follow‑up actions.

## Solution / Project Purpose
The AI Service Lead Router implements a Make.com automation scenario that listens for new leads in Airtable, determines their preferred contact method and routes them accordingly. It can initiate an AI voice call via Vapi, send a WhatsApp message or notify the internal team through Slack. Router filters and fallback logic ensure leads are always handled in the right channel.

## Key Features
- Centralised lead management using Airtable.
- Automated trigger when a new lead is created or updated.
- Decision router to select the appropriate communication path.
- **Vapi Voice Agent Call:** initiates a voice call when the lead prefers to speak.
- **WhatsApp Confirmation:** sends a templated WhatsApp message to confirm details when messaging is preferred.
- **Slack Team Notification:** posts lead information to a Slack channel for internal follow‑up.
- Router filters and fallback logic to handle exceptions and ensure delivery.

## Tools and Technologies
- **Make.com:** scenario orchestration platform.
- **Airtable:** lead database and trigger source.
- **Vapi:** AI voice assistant for outbound calls.
- **WhatsApp Business API:** for sending customer messages.
- **Slack:** for internal notifications.

## Workflow / Method
1. **Lead capture:** A new record is created in the Airtable `Lead Contact` table.
2. **Trigger:** A Make.com trigger monitors the Airtable base and starts the scenario when a lead is captured.
3. **Router decision:** The router module checks the lead’s preferred contact method and directs the flow.
4. **Voice call:** If the preference is `Call`, the Vapi module places an outbound call to the lead.
5. **WhatsApp message:** If the preference is `WhatsApp`, a templated confirmation message is sent via WhatsApp Business Cloud.
6. **Slack notification:** If the preference indicates a human follow‑up, the scenario posts a message to a Slack channel with the lead details.
7. **Filters & fallback:** Additional filters handle fallback routes and ensure no lead is left unattended.

### Workflow Diagrams and Modules
#### Overall Router Flow
<p align="center">
  <img src="01-router-flow.png" width="700"/>
</p>

#### Vapi Voice Module
<p align="center">
  <img src="02-vapi-module.png" width="600"/>
</p>

#### WhatsApp Route
<p align="center">
  <img src="03-whatsapp-route.png" width="600"/>
</p>

#### Slack Route
<p align="center">
  <img src="04-slack-route.png" width="600"/>
</p>

#### Airtable Trigger
<p align="center">
  <img src="05-airtable-trigger.png" width="600"/>
</p>

#### Router Filters & Decision Logic
<p align="center">
  <img src="06-router-filters.png" width="600"/>
</p>

## Key Insights or Outcomes
Automating lead routing eliminates manual triage and ensures that each lead is contacted through their preferred channel. The combination of voice, messaging and team notifications improves response times and customer satisfaction. By using router logic and filters, businesses can customise fallback behaviour and ensure leads are never missed.

## Business or Practical Impact
This workflow reduces operational overhead and speeds up customer engagement. It provides a consistent experience across multiple communication channels and allows teams to focus on delivering service rather than managing contact logistics. The modular design can be extended to include additional channels or business logic as needed.

## Project Structure
```
ai-service-lead-router/
├── 01-router-flow.png
├── 02-vapi-module.png
├── 03-whatsapp-route.png
├── 04-slack-route.png
├── 05-airtable-trigger.png
├── 06-router-filters.png
├── Scenerio-notes.md      # Additional scenario notes
├── vapi-call-body.json    # Example request body for Vapi call
└── README.md
```

## How to Run or View
1. This repository contains documentation and example assets for a Make.com scenario. To run the automation you will need accounts for Make.com, Airtable, Vapi, WhatsApp Business Cloud and Slack.
2. Set up an Airtable base with a `Lead Contact` table and fields for customer details and contact preference.
3. Import or recreate the scenario in Make.com using the modules illustrated above.
4. Configure connections to your Airtable base, Vapi, WhatsApp Business API and Slack channel.
5. Test the scenario by creating sample leads in Airtable and observing the automated call, message or notification.

## Future Improvements
- Extend the router to support additional channels such as SMS or email.
- Add error handling and logging modules for improved monitoring.
- Integrate with a CRM system to enrich lead data and track outcomes.
- Build a dashboard to visualise lead status and automation performance.
