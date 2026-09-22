# AI WhatsApp Voice Note Transcriber & Router

Turn WhatsApp voice notes into structured business actions using AI and n8n.

This workflow receives WhatsApp voice notes, transcribes them, extracts tasks and decisions, identifies intent and sentiment, and routes the result to the right business system.

Built for teams where important work often arrives as an audio message.

## What this workflow does

```text
WhatsApp voice note
        ↓
Download audio
        ↓
AI transcription
        ↓
Task, decision, and intent extraction
        ↓
Smart routing
        ↓
Tasks, CRM updates, notifications, or human review
```

The workflow can:

- Detect incoming WhatsApp voice notes
- Download the audio file from WhatsApp
- Transcribe the message using an AI speech-to-text provider
- Detect language, including Arabic and English messages
- Extract tasks, decisions, deadlines, entities, and intent
- Analyse sentiment
- Create separate tasks when multiple action items are mentioned
- Route information to different business systems
- Flag complaints, ambiguous messages, and sensitive decisions for review
- Archive transcripts and structured business information

## Example

A manager sends:

> Ahmed, follow up with the supplier about the invoice. Also ask Sara to send the updated contract before tomorrow.

The workflow can extract:

```text
Intent: Task Assignment

Action Items:
- Ahmed → Follow up with the supplier about the invoice
- Sara → Send the updated contract
  Due: Tomorrow
```

Those action items can then become separate tasks in ClickUp, Asana, or another task-management system.

## Possible routing logic

| Message type | Possible destination |
| --- | --- |
| Task assignment | ClickUp, Asana, or another task manager |
| Client feedback | HubSpot, Zoho CRM, or another CRM |
| Complaint | Human review |
| Approval or decision | Decision archive |
| Internal update | Google Sheets, Notion, or an internal archive |
| Ambiguous message | Manager or team review |
| Urgent message | Slack, Teams, or WhatsApp notification |

The routing logic can be adjusted to match the way your business operates.

## Supported AI providers

The default transcription path uses OpenAI Whisper.

The workflow can also be adapted to providers such as:

- OpenAI Whisper
- Deepgram
- AssemblyAI
- Azure Speech

The analysis layer can use an LLM provider such as:

- OpenAI
- Claude
- Gemini
- Azure OpenAI

## Possible destinations

The extracted information can be sent to:

- ClickUp
- Asana
- HubSpot
- Zoho CRM
- Google Sheets
- Notion
- Slack
- Microsoft Teams
- Your own software through an API

The workflow separates transcription and analysis from the final destination, making it easier to replace or extend individual integrations.

## Requirements

You will need:

- An n8n instance
- A WhatsApp Business Cloud API account
- A Meta webhook configuration
- An AI transcription provider
- An LLM provider for analysis
- At least one destination system
- Credentials for the services you intend to use

Optional integrations include:

- Slack
- Microsoft Teams
- WhatsApp notifications
- Google Sheets
- Notion
- A custom API

## Importing the workflow

1. Open your n8n instance.
2. Select **Import from File**.
3. Choose the workflow JSON file from this repository.
4. Review the nodes and credentials before activating it.
5. Add your credentials for WhatsApp, transcription, analysis, and destinations.
6. Replace the placeholder IDs and configuration values.
7. Configure the webhook URL in Meta.
8. Send a test voice note.
9. Confirm that the transcript, extracted fields, routing, and review paths behave as expected.
10. Activate the workflow only after testing the complete path.

## Credential checklist

Before activating the workflow, review the following:

- WhatsApp Business access token
- WhatsApp phone number ID
- Meta webhook verification settings
- AI transcription credentials
- LLM credentials
- ClickUp or Asana credentials
- CRM credentials
- Google Sheets or archive credentials
- Slack or Teams credentials
- Destination IDs and workspace IDs
- Any remaining `<YOUR_...>` placeholders

Never commit real API keys, access tokens, webhook secrets, or customer data to the repository.

## Human review

Automated actions should not blindly run when a message is unclear or sensitive.

This workflow can route messages to human review when:

- Intent is ambiguous
- The message contains a complaint
- Sentiment is strongly negative
- Financial commitments are mentioned
- Important information is missing
- The AI is not confident enough to proceed safely

This gives your team a chance to review sensitive messages before an automated action is taken.

## Voice note archive

Processed messages can be archived with information such as:

- Sender
- Sender phone number
- Timestamp
- Transcript
- Detected language
- Intent
- Summary
- Action items
- Decisions
- Sentiment
- Review status
- Destination and routing result

This turns important WhatsApp communication into a searchable business record instead of leaving it buried inside a chat.

## Designed for real business communication

Voice notes are common in day-to-day business communication, especially across the Gulf region.

They are useful for people, but difficult for business systems to process.

This workflow helps turn:

```text
WhatsApp voice note
→ Manual listening
→ Manual transcription
→ Manual task creation
```

into:

```text
WhatsApp voice note
→ AI transcription
→ Structured information
→ Automated business action
```

## Important note

This workflow is a strong starting point, but every business has different:

- Routing rules
- Approval requirements
- Privacy obligations
- CRM fields
- Task structures
- Notification preferences
- Human-review thresholds

Test it with representative messages before using it with live customer or operational data.

## Need help adapting it?

If this workflow is close to what you need but does not fully match your process, tell us what should happen differently.

OptiFlix can help with:

- Custom routing logic
- Additional destinations
- CRM field mapping
- Arabic and English handling
- Approval and review flows
- Voice-note archives
- Error handling and monitoring
- WhatsApp automation systems
- Custom AI agents and business workflows

Learn more about the workflow on the OptiFlix marketplace:

[View the workflow on OptiFlix](https://www.optiflix.net/marketplace/ai-whatsapp-voice-note-transcriber-router)

For a broader discussion about your business process:

[Book a discovery call](https://www.optiflix.net/discovery-call)

Or contact us at [info@optiflix.net](mailto:info@optiflix.net).

---

Built by the OptiFlix Team.
