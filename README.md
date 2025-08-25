 AI Agent for Semantic Sentiment Analysis in n8n

 Overview

This project is an AI agent workflow built in [n8n](https://n8n.io/) designed to perform semantic sentiment analysis on incoming customer support emails. The AI analyzes the primary emotion (anger, confusion, delight, neutral) and sentiment summary (positive, negative, neutral). If a negative sentiment spike is detected, the system triggers real-time alerts via email and Slack, and logs data in Google Sheets.

 Features

- Gmail Trigger:
-Automatically detects new incoming emails for analysis.
- AI Model Integration:
-  Uses Google Gemini AI for advanced sentiment and emotion detection.
- Spike Detection:
-Flags negative sentiment spikes for immediate action.
- Notifications:
  - Sends alert emails to support staff.
  - Posts notifications in Slack channels.
- Logging:
- Appends detailed analysis data including timestamp, sender email, emotion, sentiment summary, and spike detection to Google Sheets.
- Automated Apology Email:
- Sends initial apology replies to customers when a negative sentiment is detected.
- Asia/Kolkata Timezone:
- All timestamps are recorded and displayed in IST.

---

Workflow Structure

1. Gmail Trigger:
2. Watches for new emails in the specified Gmail account.
3. Message a model (Google Gemini AI):
4.  Processes the email text to detect emotion and sentiment.
5. Append Row in Google Sheets:
6.  Logs structured analysis results with timestamps.
7. Conditional Check (If Node):
8. Checks if a negative sentiment spike occurred.
9. Send Alert Email:
10.  Notifies the support team of negative sentiment spikes.
11. Send Slack Message:
12. Posts notifications to the team’s Slack channel.
13. **Send Apology Email:**
14. Automatically replies to the customer with an apology message after detecting negative sentiment.

---

 Setup Instructions

Prerequisites

- n8n instance (cloud-hosted or self-hosted)
- Gmail account with OAuth2 credentials configured in n8n
- Google Cloud account with Gemini (PaLM API) enabled and credentials set up
- Google Sheets account with API access and configured in n8n
- Slack workspace with OAuth2 app and credentials integrated in n8n

# Installation

1. Import the workflow JSON into your n8n instance.
2. Configure the credentials for Gmail, Google Gemini, Google Sheets, and Slack.
3. Update the Google Sheets document URL in the "Append row in sheet" node.
4. Set your Slack channel ID in the Slack notification node.
5. Adjust email addresses in the email nodes for alerts and automated replies.
6. Activate the workflow and test by sending emails with varying emotional content.

---

## How to Test

Send test emails with different sentiments:

- **Anger:** Express frustration or dissatisfaction.
- **Neutral:** Ask for information without emotional content.
- **Confusion:** Express uncertainty or conflicting information.

The AI agent will process these emails, identify the sentiment, log results, send alerts, and reply with apology emails for negative sentiments.

---

## Example Data Logged

| Timestamp          | Sender Email            | Emotion  | Sentiment Summary | Spike Detected |
|--------------------|------------------------|----------|-------------------|----------------|
| 04:21 PM–08/25/2025| customer@example.com    | anger    | negative          | true           |

---

## Screenshots


<img width="758" height="379" alt="image" src="https://github.com/user-attachments/assets/6f5f2c6e-d6c1-47ac-aad8-f42a0901cd3a" />

---



## License

This project is licensed under the MIT License.

---

## Contact

Your Name  
Email: okeymanoj@example.com  
GitHub: [manoj kumar T](https://github.com/techtribe01)

---

*Thank you for checking out this AI sentiment analysis project made with n8n!*
