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
