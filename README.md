# AI-Powered Customer Support Automation

An AI-powered customer support automation system built with **n8n, Google Gemini, Google Sheets, and Gmail**. It processes incoming customer enquiries, classifies them by intent, retrieves relevant information, generates responses, and records interactions automatically.

The project also includes a dedicated error-handling workflow to manage execution failures.

## Overview

The system receives customer messages through an n8n webhook and uses Google Gemini to classify each enquiry into one of four categories:

- **FAQ:** General questions answered using information retrieved from a Google Sheets knowledge base.
- **ORDER:** Order-related enquiries handled by retrieving order information from Google Sheets.
- **COMPLAINT:** Customer complaints acknowledged with an AI-generated response.
- **HUMAN:** Generates a human-support handoff message when an enquiry requires assistance from a human support representative..

After processing, the system records the interaction and sends the generated response through Gmail.

## Workflow Architecture

1. **Webhook Reception:** Receives incoming customer enquiries through an HTTP POST request.
2. **AI Classification:** Google Gemini analyses the message and assigns it to FAQ, ORDER, COMPLAINT, or HUMAN.
3. **Intent Routing:** An n8n Switch node directs the enquiry to the appropriate processing branch.
4. **Information Retrieval:** Google Sheets provides FAQ information or order details where required.
5. **Response Generation:** Google Gemini generates a response based on the relevant information and branch-specific instructions.
6. **Customer Communication:** Gmail handles response delivery.
7. **Interaction Logging:** Google Sheets stores customer details, enquiry categories, generated responses, and timestamps.
8. **Error Handling:** A dedicated error-handler workflow manages failed executions separately from the main processing workflow.

## Key Features

- Automated customer enquiry processing.
- AI-powered intent classification using Google Gemini.
- Four distinct customer support routes.
- FAQ retrieval from Google Sheets.
- Order information lookup.
- AI-generated complaint acknowledgements.
- Human-support handoff messaging.
- Automated email communication.
- Customer interaction logging.
- Dedicated error-handling workflow.

## Technologies Used

- **n8n:** Workflow automation and orchestration.
- **Google Gemini API:** Intent classification and response generation.
- **Google Sheets:** FAQ knowledge base, order records, and interaction logs.
- **Gmail:** Email communication.
- **JavaScript:** Data processing and AI response parsing.
- **REST API / HTTP:** API communication.
- **JSON:** Structured data exchange and workflow configuration.

## Repository Structure

- `AI Powered Customer Support.json` - Main customer support automation workflow.
- `Error handler.json` - Dedicated error-handling workflow.
- `screenshots/` - Workflow screenshots and implementation visuals.


## Setup and Configuration

1. Install or access an n8n instance.
2. Import the main customer support workflow JSON.
3. Import the error-handler workflow JSON.
4. Configure Google Gemini API credentials.
5. Connect your Google Sheets account and configure the required FAQ, order, and interaction-log sheets.
6. Configure Gmail credentials and the appropriate email recipient settings.
7. Update the workflow's configuration and connect the error handler through n8n's error-workflow settings where applicable.
8. Activate the workflows and test the webhook using Postman or another HTTP client.

**Note:** API keys and account credentials are not included in the exported workflow. Users must configure their own credentials before running the system.

## Project Purpose

This project demonstrates how AI and workflow automation can be combined to build a structured customer support system.

It showcases practical experience with API integration, AI-powered decision-making, conditional workflow routing, data retrieval, automated communication, and error handling.

The system is designed to reduce repetitive customer support tasks while maintaining structured records of customer interactions.

<img width="991" height="380" alt="Screenshot 1" src="https://github.com/user-attachments/assets/b0536923-167c-4e13-8181-5888333dc676" />
<img width="967" height="342" alt="Screenshot 2" src="https://github.com/user-attachments/assets/20330ef7-268f-47ad-a475-23b8a329d14d" />
<img width="585" height="728" alt="Screenshot 3" src="https://github.com/user-attachments/assets/da887654-d019-4b30-b025-cb35210bf4d4" />
