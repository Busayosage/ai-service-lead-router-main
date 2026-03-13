# SilkyClean Riley Automation

This repository documents the working Make.com automation for SilkyClean.

## System Overview

Tally Form  
→ Airtable Lead  
→ Make Router  

Router Logic:

- If contact preference = Call → Vapi outbound call
- If contact preference = WhatsApp → WhatsApp confirmation message
- Slack sends internal notification for all leads

## Automation Modules

- Airtable Watch Records
- Router
- WhatsApp Business Cloud
- Slack Notification
- Vapi Create Call
- Airtable Update Record

## Purpose

This automation routes incoming cleaning leads to the appropriate communication channel and alerts the team.

## Notes

Sensitive credentials such as API keys and webhook URLs are not included in this repository.