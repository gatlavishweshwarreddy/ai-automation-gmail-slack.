# AI Automation: Gmail → Slack Summary

This project automates email summaries from Gmail into Slack using n8n.

## Features
- Fully automated workflow triggered by a **Trigger node** 
- Automatically reads emails from Gmail (limit of 50 items per execution)
- Summarizes content using AI
- Posts summary into Slack channel
- Supports emoji and username in Slack notifications

## Tech Stack
- n8n
- Gmail API
- Slack API
- AI integration (for summarization)
- Small JavaScript for filtering and processing
- Aggregate node for combining email data
- Trigger node for event-driven automation

## Demo
[Watch 24-second demo]((https://bit.ly/4sDNlEf))

## How to Run
1. **Import the workflow JSON** into your n8n instance.  
2. **Connect Gmail credentials** in the Gmail node:  
   - Set a **limit of 50 items** to optimize performance.  
   - Configure filters if needed using **JavaScript expressions** in the Filter node  
3. **Connect Slack credentials** in the Slack node:  
   - Use **notification text** with expressions and optional emoji/username.  
   - Use a **header block** for “Email Summary” to avoid parsing errors.  
4. **Set up the Trigger node**  for automated execution.  
5. **Check the Aggregate node configuration**:  
   - Ensure email subject and body are aggregated before passing to AI prompt.  
6. **Configure the AI node prompt** to summarize emails concisely.  
7. **Activate the workflow**.  
8. Optional: Test by sending sample emails to verify summaries appear correctly in Slack.  

## Technical Details / Notes
- Workflow starts with a **Trigger node**  to automate execution.  
- Gmail node is configured with a **limit of 50 items** to optimize performance.  
- Used **small JavaScript expressions in n8n filters** to process emails.  
- Extracted **email subject and body  using the Aggregate node** for AI summarization.  
- Integrated **AI prompt** to generate concise Slack summaries.  
- Solved Slack parsing issues:
  - Initial errors occurred when using both `blocks` and `notification text` (e.g., “Parameter could not be parsed” and “Unexpected token” at position 114).  
  - Fixed by using a **normal header text** (`Email Summary`) and **expressions in notification text**.  
- Demonstrates **real-world debugging, problem-solving, and workflow automation skills**.
