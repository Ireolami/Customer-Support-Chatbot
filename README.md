# AI Scheduling & Logging Assistant (n8n)

A conversational AI agent built in n8n that chats with users, books
meetings, and keeps records, all from a single chat message.

## What it does

Send the agent a message like *"Book a call with Tunde on Friday at 2pm
and log it"* and it will:

1. Understand the request using GPT (OpenAI Chat Model)
2. Remember conversation context across turns (Simple Memory)
3. Create the event in **Google Calendar**
4. Append or update a record in **Google Sheets**
5. Run custom logic where needed via the **Code Tool**
6. Reply in the chat with a confirmation

## Architecture
Chat Trigger → AI Agent
├─ Model:  OpenAI Chat Model
├─ Memory: Simple Memory (per-session context)
└─ Tools:  Code Tool · Google Sheets (appendOrUpdate)
· Google Calendar (create event)

The agent decides autonomously which tool to call based on the user's
intent. No hardcoded paths.

## Stack

n8n · OpenAI API · Google Calendar API · Google Sheets API

## Setup

1. Import the workflow JSON into n8n
2. Add credentials: OpenAI API key, Google Calendar OAuth2, Google Sheets OAuth2
3. Point the Sheets node at your logging spreadsheet
4. Activate the workflow and open the chat URL

## Example use cases

- Personal scheduling assistant via chat
- Appointment booking for a small business
- Meeting logger that keeps a Sheet as the source of truth
