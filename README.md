# power-platform-automation-portfolio
Power Automate, Power Apps, Microsoft 365, ITSM and workflow automation portfolio.

# Freshservice P1 Incident to Microsoft Teams Automation

## Overview
This automation improves communication for urgent IT incidents by automatically creating or reusing a Microsoft Teams group chat when a Freshservice ticket is marked as Urgent/P1.

## Business Problem
Urgent incidents require fast coordination. Manual chat creation can delay updates and cause important stakeholders to be missed.

## Solution Flow
Freshservice Ticket Updated (Urgent/P1)
→ Sends notification to a shared mailbox
→ Power Automate detects the email
→ Checks SharePoint for an existing incident chat
→ Creates or reuses the Microsoft Teams group chat
→ Posts incident updates to the correct chat

## Tools Used
- Freshservice Automator
- Microsoft Power Automate
- Microsoft Teams
- SharePoint List
- Outlook Shared Mailbox

## Key Features
- Automated P1 incident notification
- Teams chat creation or reuse
- SharePoint mapping of ticket subject and Chat ID
- Follow-up updates posted to the same Teams chat
- Prevents duplicate chats for the same incident

## Skills Demonstrated
ITSM automation, workflow design, Power Automate expressions, Teams integration, SharePoint data management, troubleshooting, and documentation.

## Note
All names, email addresses, ticket numbers, and company-specific data are anonymized for this public portfolio.
