Freshservice P1 Incident → Microsoft Teams Group Chat Automation

A Power Automate and Freshservice solution that helps IT teams coordinate urgent incidents faster by creating or reusing a dedicated Microsoft Teams group chat.

Project Description

This solution automates the communication workflow for Urgent / Priority 1 (P1) Freshservice tickets. When an urgent ticket is updated, Freshservice sends a notification to an IT shared mailbox. Power Automate detects the message, checks whether a Teams chat already exists for that incident, and then creates a new chat or reuses the existing one.

The solution also stores the ticket subject and Teams Chat ID in a SharePoint list. This allows follow-up updates to be posted in the same conversation instead of creating duplicate chats.

Business Problem

During a P1 incident, people need to coordinate quickly. Creating a group chat manually can delay the response, make it difficult to find the right conversation, and lead to duplicate chats or missed updates.

This automation provides a repeatable process for incident communication and a record of the Teams chat associated with each incident.

Objectives

Automatically identify Freshservice tickets marked Urgent / P1.

Notify the relevant IT support members through a Microsoft Teams group chat.

Use the Freshservice ticket subject as the Teams chat name.

Reuse an existing incident chat when a matching ticket update is received.

Store the ticket subject and Chat ID in SharePoint for tracking and future updates.

Reduce manual coordination and duplicate incident chats.

Solution Architecture

Freshservice Ticket Updated (Priority: Urgent / P1)
        ↓
Freshservice Automator sends notification email
        ↓
Outlook Shared Mailbox
        ↓
Power Automate flow triggers on the new email
        ↓
SharePoint list checks for an existing ticket subject / Chat ID
        ↓
Create a new Microsoft Teams chat OR reuse the saved chat
        ↓
Post incident details and follow-up updates to the Teams chat

Workflow Screenshots

Flow 1 — Initial P1 Incident Notification



Flow 2 — Check Existing Chat and Create a New Chat When Needed



Flow 3 — Post Follow-Up Incident Updates



Technologies Used

Platform / service

Purpose in the solution

Freshservice Automator

Detects ticket updates and sends P1 notification emails.

Microsoft Power Automate

Orchestrates the workflow, conditions, variables, and error-aware routing.

Outlook shared mailbox

Provides the email trigger point between Freshservice and Power Automate.

Microsoft Teams

Hosts the dedicated group chat for P1 incident collaboration.

SharePoint List

Stores the ticket subject and Teams Chat ID mapping.

Power Automate Design

Trigger

When a new email arrives in a shared mailbox (V2)

The shared mailbox receives an alert sent by Freshservice Automator when ticket priority becomes Urgent.

Core Logic

Read the Freshservice email and extract the ticket subject and incident details.

Query the SharePoint incident-chat mapping list for the ticket subject.

If a matching item exists, retrieve the saved Teams Chat ID.

If no item exists:

Build the Teams chat member list.

Create a Microsoft Teams group chat.

Save the ticket subject and new Chat ID in SharePoint.

Post the initial P1 notification to the chat.

Post subsequent incident updates to the existing chat.

Key Implementation Details

Duplicate-chat prevention: SharePoint is used as a lightweight mapping database between the ticket subject and the Teams Chat ID.

Chat membership: Microsoft Teams requires individual email addresses for group-chat members. Static, approved IT support members were used for this implementation.

Message continuity: Later updates use the stored Chat ID, so the incident conversation remains in one chat thread.

Shared mailbox trigger: The workflow is triggered from a shared mailbox instead of a personal mailbox to support operational continuity.

Scope and Constraints

Freshservice watchers were not available in the configured notification placeholders, so they could not be dynamically added to the Teams chat through the email-trigger design.

Group chat creation requires individual members; it cannot use a Teams group name as the membership source.

This public documentation uses anonymized examples. No production email addresses, ticket numbers, company names, credentials, internal URLs, or customer data are included.

Outcome

The completed workflow reduces the manual work required to start and maintain a P1 incident collaboration channel. It demonstrates practical skills in ITSM automation, Power Automate workflow design, Microsoft 365 integration, SharePoint data handling, and Teams-based incident communication.

Skills Demonstrated

Power Automate cloud flows

Freshservice Automator and ITSM process design

Microsoft Teams chat automation

Outlook shared mailbox triggers

SharePoint Lists and item lookup

Conditions, variables, Compose actions, and dynamic content

Duplicate prevention and workflow troubleshooting

Operational documentation and incident communication

Portfolio note: This project has been sanitized for public viewing. The workflow design and screenshots demonstrate the approach without exposing confidential implementation data.
