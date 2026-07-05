WhatsApp AI Appointment Booking with n8n An automated, AI-powered WhatsApp appointment booking workflow built with n8n. This workflow acts as a virtual assistant that handles customer inquiries in multiple languages (Darija, Arabic, French, English), responds in professional French, checks availability, and manages appointments directly in Google Calendar.

🚀 Features WhatsApp Integration: Triggered by incoming text messages via WhatsApp Cloud API.

AI-Powered Agent: Uses LangChain and OpenRouter (gpt-4o-mini) to process natural language and extract booking details (Name, Service, Date, Time, Duration).

Smart Memory: Utilizes Window Buffer Memory to remember conversation context per user (using their WhatsApp number as the session key).

Multi-language Support: Understands Moroccan Darija, Arabic, French, and English, but strictly replies in professional French.

Google Calendar Automation:

Checks availability before booking.

Creates new calendar events after explicit user confirmation.

Retrieves, updates, and deletes existing appointments.

Timezone Aware: Automatically handles relative dates (e.g., "tomorrow at 3 PM") and converts them to absolute dates in the Africa/Casablanca timezone.

🛠️ Tech Stack n8n (Workflow Automation)

WhatsApp Cloud API (Messaging Interface)

OpenRouter / OpenAI (LLM Provider)

Google Calendar API (Scheduling & Event Management)

LangChain (Agent & Memory management within n8n)

📋 Prerequisites To run this workflow, you will need:

An active n8n instance.

WhatsApp Cloud API setup (Meta Developer account with a configured phone number).

An OpenRouter account and API key.

Google Calendar API credentials (OAuth2 or Service Account) configured in n8n.

⚙️ Setup & Installation Clone this repository or download the workflow .json file.

Open your n8n workspace and click on Add Workflow.

Select Import from File and upload the workflow file, or simply copy-paste the JSON content directly into the n8n editor.

Configure your credentials:

Add your WhatsApp Cloud API credentials to the WhatsApp Trigger and Send message nodes.

Add your OpenRouter API key to the OpenRouter Chat Model node.

Authenticate your Google Account in all Google Calendar tool nodes.

Save and activate the workflow.

🧠 How it Works Trigger & Filter: A message is received via WhatsApp. The Filter Text Only node ensures only text messages are processed.

AI Agent: The LangChain agent receives the message. It accesses the conversation history via Window Buffer Memory.

Tool Execution: Depending on the user's request, the agent decides whether to use Google Calendar tools to check slots, book, update, or cancel an appointment.

Reply: Once the agent formulates the response in French, the Send message node pushes it back to the user via WhatsApp.

⚠️ Notes Privacy & Security: This repository contains an anonymized version of the workflow. All personal credentials, webhook IDs, and sensitive phone numbers have been removed.

Customization: You can modify the system prompt inside the AI Agent node to change the business context, language rules, or timezone settings. Currently, it's strictly set to Africa/Casablanca.

Created and maintained by [talatiyassine131]
