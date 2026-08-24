# Customer Support GPT — Prompt Library

## Available Prompts

| Trigger | Action | Output Format |
| :--- | :--- | :--- |
| /analyze | Analyzes the ticket | Issue Summary, Sentiment, Urgency, Missing Info, Next Action |
| /generate | Generates a response draft | Complete response draft with greeting, steps, closing |
| /improve | Improves an existing draft | Revised response + Change Log |
| /summarize | Creates an executive summary | 3-bullet summary: Issue, Action, Next Steps |
| /escalate | Drafts escalation summary | Target Team, Reason, Customer Context, Timeline |
| /tag | Suggests ticket tags | Category, Sub-category, Priority, Tags |
| /handoff | Creates handoff summary | Ticket Overview, Actions Done, Pending, Next Steps |

## Pairing Workflows

| Pair | Best Used When | Benefit |
| :--- | :--- | :--- |
| /analyze → /generate | You need a complete response | Ensures all issues are addressed |
| /analyze → /escalate | You need to escalate quickly | Provides full context to receiving team |
| /generate → /improve | You want a polished final response | Creates high-quality output |
| /summarize → /handoff | You're doing a team handoff | Clean, complete handoff summary |

## Usage Examples

### /analyze Example

Input:
/analyze
I can't log in to my dashboard. I've tried resetting my password twice but it's still not working.

Output:
- Issue Summary: Login failure, password reset not working
- Customer Sentiment: Frustrated
- Urgency Level: High
- Missing Information: Error message, device/browser details
- Recommended Next Action: Generate response with troubleshooting steps

### /escalate Example

Input:
/escalate
Customer name: Priya Sharma
Issue: Payment processing failure with 3 different cards

Output:
- Target Team: Billing Team
- Reason for Escalation: Payment processing failure requiring backend investigation
- Customer Context: Customer is frustrated, urgent
- Recommended Timeline: Within 2 hours
