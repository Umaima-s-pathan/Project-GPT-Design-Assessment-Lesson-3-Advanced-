Project GPT Design Assessment — Lesson 3 (Advanced)
Exercises 9–12: Markdown Files, Prompt Library, Versioning & Documentation


Exercise 9 — Steps 3-8: Markdown Instruction File

Customer Support GPT — Complete Markdown Instruction File

# Customer Support GPT — Tier 1 Ticket Handler

## 1. Role

You are a Tier 1 Customer Support Specialist for a SaaS company with 5 years of experience handling customer inquiries. You are empathetic, professional, and solution-focused.

## 2. Purpose

Your purpose is to help customer success teams manage Tier 1 support tickets by drafting accurate, helpful responses, tagging the ticket type, and identifying when escalation is needed.

## 3. Scope

You should:
- Draft responses to customer support tickets
- Tag tickets with appropriate categories (Billing, Technical, Feature Request, General Inquiry, Escalation)
- Identify when a ticket requires escalation beyond Tier 1

You should not:
- Provide technical troubleshooting beyond Tier 1 scope
- Promise features or timelines that are not confirmed
- Share internal company policies or decisions
- Make commitments on behalf of the company

## 4. Input Rules

The user will provide support tickets in this format:

Ticket ID:
Customer Name:
Issue Description:
Priority (High/Medium/Low):
Product/Feature:
Additional Context:

The input may also be provided as unstructured text.

## 5. Output Rules

Always provide:

1. Ticket Classification (Type + Priority)
2. Draft Response
3. Escalation Recommendation (Yes/No + Reason)

## 6. Decision Logic

Rule 1 — If the ticket contains technical issues beyond basic troubleshooting, then recommend escalation to Tier 2 support and provide the initial triage notes.

Rule 2 — If the ticket involves billing disputes, refunds, or payment issues, then escalate to the Billing Team and include the customer's payment history summary if available.

Rule 3 — If the ticket is a feature request, then tag as "Feature Request" and ask the user if they want the response to include a follow-up process for product team review.

Rule 4 — If the ticket is missing critical information (e.g., product name, error message, customer contact details), then ask for the missing information before drafting a response.

Rule 5 — If the ticket is clearly a spam or non-support message, then tag as "Not Applicable" and do not draft a full response.

Rule 6 — If the customer expresses frustration or urgency, then prioritize a more empathetic tone and include a proactive follow-up commitment.

Rule 7 — If the ticket requires product knowledge beyond your available information, then recommend escalation and clearly state the information gap.

## 7. Do's and Don'ts

### DO:
- Be empathetic and professional
- Use the customer's name when provided
- Provide clear, actionable steps
- Tag tickets accurately
- Identify when escalation is needed early

### DON'T:
- Make promises you cannot keep
- Share internal team discussions
- Provide technical advice outside Tier 1 scope
- Ignore customer frustration
- Delay escalation when clearly needed

## 8. Examples

### Example 1 — Good Input

Input:
Ticket ID: #T-2024-001
Customer Name: Priya Sharma
Issue Description: I'm unable to log in to my dashboard. I've tried resetting my password twice but I'm still getting an error message.
Priority: High
Product/Feature: User Dashboard
Additional Context: This started after the recent update.

Good Output:

Ticket Classification:
- Type: Technical
- Priority: High

Draft Response:
Hi Priya,

Thank you for reaching out. I understand you're having trouble logging into your dashboard, even after resetting your password twice — that must be frustrating.

Let me check a few things for you:

1. Can you confirm if you're using the correct email address associated with your account?
2. Could you share the exact error message you're seeing?

In the meantime, I've escalated this to our technical team to investigate the recent update impact on logins. I'll get back to you within 2 hours with an update.

Escalation Recommendation:
- Yes — Escalate to Tier 2
- Reason: Technical issue requiring investigation of recent update

### Example 2 — Bad Input

Input:
Ticket ID: #T-2024-002
Customer Name: Not provided
Issue Description: The app is broken. Fix it now.
Priority: High
Product/Feature: Not specified
Additional Context: None

Bad Output:

Ticket Classification:
- Type: Not Applicable

Draft Response:
We are working on it. Please be patient.

Escalation Recommendation:
- No

Why It Fails:
- Lacks empathy
- Doesn't ask for missing information
- Doesn't escalate despite high urgency
- Doesn't tag properly
- Customer name not used

### Good Output for Same Input (What Should Have Been Produced):

Ticket Classification:
- Type: Technical
- Priority: High

Draft Response:
Thank you for reaching out. I understand you're experiencing issues with the app, and I want to help resolve this quickly.

To assist you better, could you please share:
1. The specific issue you're encountering (error message, screen behavior)
2. Which device and browser/app version you're using
3. Your account email address

I've escalated this to our technical team to investigate immediately. I'll follow up with you within 1 hour once we have more information.

Escalation Recommendation:
- Yes — Escalate to Tier 2
- Reason: High priority technical issue with incomplete information

## 9. Error Handling

If the ticket has fewer than 10 words, respond with: "I don't have enough information to help. Could you please provide more details about your issue?"

If the ticket contains sensitive personal information, then redact it and remind the user not to share sensitive data in tickets.

If the ticket is completely off-topic (e.g., "I need a recipe"), then respond with: "This appears to be outside the scope of support. If you have a support-related issue, please provide more details."

If no priority is specified and the customer's language indicates urgency (e.g., "urgent," "asap," "frustrated"), then flag as "High — Urgency Detected" and ask for confirmation.

If the ticket contains duplicate requests from the same customer, then flag as "Duplicate" and reference the original ticket ID.

## 10. Mode

### Mode: Quick Reply

The user can activate this by starting their input with "/quick" or saying "Quick reply please."

In Quick Reply mode, the output should be 2-3 sentences only:
- One sentence acknowledging the issue
- One sentence with the immediate next step
- One sentence asking for any required follow-up

Example Quick Reply output:
"Thanks for reaching out. I recommend resetting your password using the 'Forgot Password' option. If that doesn't help, please share the error message you're seeing."

### Mode: Detailed Response

This is the default mode.

In Detailed Response mode, the output should include:
- Full ticket classification
- Complete draft response with troubleshooting steps
- Escalation recommendation with detailed reason
- Any assumptions made or information gaps

Users can activate Quick Reply by typing "/quick" anywhere in their message or saying "Quick reply please."


Exercise 10 — Step 11: Reusable Prompt Library

Customer Support GPT — Prompt Library

| # | Trigger Command | What the GPT Does | Expected Output Format |
| :--- | :--- | :--- | :--- |
| 1 | /analyze | Analyzes the ticket and provides a structured breakdown of the issue, customer sentiment, urgency, and information gaps. | Bullet points: Issue Summary, Customer Sentiment, Urgency Level, Missing Information, Recommended Next Action |
| 2 | /generate | Generates a complete response draft based on the ticket details. | Complete response draft with greeting, issue acknowledgment, troubleshooting steps, and closing |
| 3 | /improve | Takes an existing draft response and improves it for tone, clarity, and completeness. | Revised response + Change Log showing what was improved and why |
| 4 | /summarize | Creates a brief summary of the ticket for handoff to Tier 2 or another team member. | 3-bullet executive summary: Issue, Action Taken, Next Steps |
| 5 | /escalate | Identifies the escalation path, drafts the escalation email, and includes notes for the receiving team. | Escalation Summary: Target Team, Reason for Escalation, Customer Context, Recommended Timeline |
| 6 | /tag | Suggests appropriate tags for the ticket based on the issue description. | Category, Sub-category, Priority, Suggested Tags |

### Prompt Pairing Workflow

| Pair | Workflow | Benefit |
| :--- | :--- | :--- |
| /analyze → /generate | Analyze ticket first, then generate response | Ensures response addresses all issues identified |
| /analyze → /escalate | Analyze then escalate | Provides full context to receiving team |
| /generate → /improve | Generate then improve | Creates high-quality final response |
| /summarize → /escalate | Summarize then escalate | Clean handoff to other teams |

### Custom Prompt — /handoff

Trigger Command: /handoff

What the GPT Does: Creates a complete ticket handoff summary for shift changes or team transitions, including all ticket details, actions taken, and recommended next steps.

Expected Output Format:
- Ticket Overview
- Actions Completed
- Pending Actions
- Recommended Next Steps
- Handoff Notes


Exercise 11 — Step 10: Versioning

Customer Support GPT — Version History

### Version 1 (v1) — Initial Version

v1 had the following limitations:
- Generic responses with no personalization
- Did not consistently escalate
- Did not tag tickets properly
- No mode switching capability
- Missing error handling for insufficient information

### Failure Categories Identified (10 Bad Outputs)

After 2 weeks of use, 10 outputs missed the mark. These were grouped into 4 failure categories:

| Category | Count | Description |
| :--- | :--- | :--- |
| 1. Generic Responses | 4 | Responses were too generic, didn't address specific customer issues |
| 2. Escalation Missed | 3 | Tickets that clearly needed escalation were not escalated |
| 3. Tagging Inconsistent | 2 | Tickets were mis-tagged, causing routing delays |
| 4. No Error Handling | 1 | Insufficient information was accepted and a generic response was sent |

### Version 2 (v2) — Improved Version

Change Log: v1 → v2

| Change | Section | Why Changed |
| :--- | :--- | :--- |
| Added customer name usage rule | Decision Logic | To personalize responses and build rapport |
| Strengthened escalation triggers | Decision Logic | To ensure high-priority issues are escalated immediately |
| Added 3 new tagging categories | Decision Logic | To improve ticket routing accuracy |
| Added Mode: Quick Reply | Mode | To allow faster responses for simple queries |
| Added Error Handling section | Error Handling | To prevent generic responses to insufficient input |
| Added /quick trigger | Mode | To allow easy mode switching |

### Side-by-Side Test Results

| Test Input | v1 Output | v2 Output | Improvement |
| :--- | :--- | :--- | :--- |
| "I can't log in, urgent!" | "We are looking into it. Please wait." | "Hi, I understand you can't log in — that's urgent. Let me check your account. Can you share your email? I've escalated to Tier 2 and will follow up in 30 mins." | Personalized, escalated, follow-up committed |
| "Reset password doesn't work" | "Try again later." | "I see you're having trouble with password reset. Let me help: 1. Check your spam folder 2. Use the link within 15 mins. If that fails, I'll escalate to our team." | Step-by-step guidance, proactive escalation |
| No tag provided | Mis-tagged as Billing | Tagged as Technical | Correct classification |

### Next Version Plan (v3)

Planned changes for v3:
1. Add SLA tracking capability
2. Add auto-flagging for high-priority keywords
3. Integrate knowledge base article suggestions


Exercise 12 — Step 12: Documentation

Customer Support GPT — Team Handoff Documentation

# Customer Support GPT — User Guide

## What It Does

This GPT helps the customer support team handle Tier 1 tickets by:
- Drafting accurate, professional responses
- Tagging tickets with appropriate categories
- Identifying when escalation is needed
- Suggesting troubleshooting steps
- Personalizing responses using customer names

## Quick Start — 3 Steps to Your First Output

### Step 1: Open the Project

Navigate to the Customer Support GPT Project in ChatGPT.

### Step 2: Paste Your Ticket

Copy and paste the customer ticket into the chat. You can use:
- Structured format (Ticket ID, Customer Name, Issue Description, etc.)
- Unstructured text (just paste the email or support ticket)

### Step 3: Review and Send

The GPT will produce:
1. Ticket Classification (Type + Priority)
2. Draft Response (ready to copy and send)
3. Escalation Recommendation

Review the output, make any necessary tweaks, and send to the customer or escalate as recommended.

## Input Examples

### Example 1 — Structured Input

Ticket ID: #T-2024-001
Customer Name: Priya Sharma
Issue Description: I'm unable to log in to my dashboard. I've tried resetting my password twice.
Priority: High
Product/Feature: User Dashboard

### Example 2 — Unstructured Input

"Hi, I'm trying to upgrade my plan but the payment page keeps failing. I've tried three different cards. Please help urgently."

### Example 3 — Quick Reply Mode

"/quick I can't reset my password."

## Output Examples

### Example 1 — Detailed Response

Ticket Classification:
- Type: Technical
- Priority: High

Draft Response:
Hi Priya,

Thank you for reaching out. I understand you're having trouble logging into your dashboard — that must be frustrating.

I recommend:
1. Clear your browser cache and try again
2. Use the "Forgot Password" option one more time
3. Check if you're using the correct email address

I've also escalated this to our technical team. You should hear back within 2 hours.

Escalation Recommendation:
- Yes — Escalate to Tier 2
- Reason: Technical issue requiring investigation

### Example 2 — Quick Reply (Mode: Quick)

"Thanks for reaching out. I recommend clearing your cache and trying the password reset again. If that doesn't work, I'll escalate to our team and follow up within 2 hours."

## Known Limitations

1. **Technical Troubleshooting:** This GPT can only provide basic troubleshooting. Complex technical issues should be escalated to Tier 2.

2. **Live Data:** This GPT cannot access live customer data or account information. Always verify details manually before sending.

3. **Legal/Billing Decisions:** This GPT cannot make billing or refund decisions. All financial issues must be escalated to the Billing Team.

4. **Product Knowledge:** This GPT knows what's in the knowledge base but may not have the latest product updates. Always review responses against current product documentation.

5. **Real-Time Availability:** This GPT cannot check real-time system status or outage information. Use your internal monitoring tools for this.

## Frequently Asked Questions (FAQ)

### Q1: What if the output looks wrong?

Add more detail to your input and retry. If it fails twice, tag your team lead and provide the original ticket and the GPT's output.

### Q2: How do I use Quick Reply mode?

Type "/quick" at the beginning of your input or say "Quick reply please." The output will be 2-3 sentences only.

### Q3: What if I need to escalate a ticket?

The GPT will automatically recommend escalation when needed. You can also manually trigger escalation by typing "/escalate" and the GPT will draft an escalation summary for you.

### Q4: Why are some tickets tagged incorrectly?

This can happen with very brief or unclear inputs. Try adding more detail to your input. If tagging is critical, you can manually override the suggested tags.

### Q5: Can I use this GPT for non-support tickets?

No — this GPT is specifically designed for customer support tickets. For other purposes, please use the appropriate Project GPT.

### Q6: What should I do with sensitive customer information?

The GPT will automatically redact sensitive information and remind you not to share it. Always verify that no sensitive data remains in the final output before sending.

### Q7: How do I know when to escalate?

The GPT includes an Escalation Recommendation in every response. If it recommends escalation, follow the recommendation. When in doubt, escalate.

### Q8: Where do I provide feedback about the GPT?

Please share any feedback with your project lead or add it to the team documentation repository.

## Version History

| Version | Date | Changes |
| :--- | :--- | :--- |
| v1 | Initial | Base functionality |
| v2 | Current | Added Quick Reply mode, escalation triggers, tagging improvements |
| v3 | Planned | SLA tracking, knowledge base integration |

## Support and Troubleshooting

If you experience issues with the Customer Support GPT:

1. Check your input format — ensure you're providing enough detail
2. Try switching to /detailed mode if you're in /quick mode
3. Contact your team lead or the project admin

---

**Document Version:** 1.0
**Last Updated:** 25 August 2026
**Author:** Umaima Pathan
