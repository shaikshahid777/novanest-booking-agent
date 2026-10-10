# NovaNest Consultation Booking Agent

Retell AI Topic 6 assessment: **Appointment Booking Logic & Calendar Handoff Design**.

**Demo video:** https://www.loom.com/share/d7a16178b492428ba0942ea2fdb25e23

## Overview
A voice agent for NovaNest Real Estate, built as a **Single Prompt Agent** in Retell AI (inbound web call, tested from the dashboard). It handles three call paths: **New Booking, Reschedule, Cancellation**. It collects scheduling preferences and produces a structured booking request through Post-Call Analysis. It does not check a live calendar.

## Features
- Structured booking request (12 fields) captured via Post-Call Analysis
- Availability language control: never says "available", "confirmed", "booked", "secured" for a time slot
- Timezone anchoring on every time window
- Cancellation and rescheduling fee policy stated before the action is recorded
- Disqualification handling: same-day, out-of-hours, unsupported service
- Fixed Booking Confirmation Message for New and Reschedule calls

## Scheduling Rules
| Rule | Value |
|---|---|
| Business hours | Mon-Fri, 9:00 AM - 6:00 PM CT |
| Service duration | 45 minutes (latest start 5:15 PM CT) |
| Buffer | 15 minutes (handled by calendar system) |
| Timezone | Central Time (America/Chicago) |
| Advance notice | Minimum 24 hours, no same-day |
| Max advance booking | 30 days |
| Max preferred windows | 3 |
| Late cancellation (within 24h) | $50 fee |
| Late reschedule (within 4h) | $50 fee on original booking |

## Post-Call Analysis Schema (12 fields)
`caller_first_name`, `caller_last_name`, `caller_phone`, `caller_email`, `service_type` (Selector), `preferred_window_1`, `preferred_window_2`, `preferred_window_3`, `caller_timezone`, `booking_notes`, `request_type` (Selector), `original_booking_reference`.
Details: [post-call-analysis/pca_fields.md](post-call-analysis/pca_fields.md). Sample output: [sample_booking_request.json](post-call-analysis/sample_booking_request.json).

## Repository Structure
```
prompt/agent_prompt.md
post-call-analysis/pca_fields.md
post-call-analysis/sample_booking_request.json
tests/test_cases.md
tests/test_results.md
screenshots/
```

## How to Test
Open the agent in Retell, click **Test**, run the 4 calls in `tests/test_results.md`, then check the transcript and the 12 extracted fields in Call History.

## Assumptions
- No live calendar, API, webhook or custom function in this topic.
- Scheduling rules and policies are fixed values inside the prompt.

## Limitations
- The agent cannot verify real availability or write to a calendar.
- Timezone accuracy depends on the caller stating it correctly.
- Buffer rules are enforced later by the calendar system.
- Date validation relies on the model reading `{{current_time}}`.

## Future Enhancements
- Connect a calendar API through a custom function or webhook.
- Send automatic email/SMS confirmations.
- Add programmatic date and business-hours validation.
