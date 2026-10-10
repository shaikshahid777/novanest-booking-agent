# Test Cases Summary

| ID | Scenario | Expected result | Priority |
|---|---|---|---|
| TC-001 | New booking, 3 windows (CT) | All fields captured, confirmation message delivered, no availability language | High |
| TC-002 | Cross-timezone caller (ET) | Timezone confirmed; window and caller_timezone show ET | High |
| TC-003 | Availability language audit | No "available/confirmed/booked/secured" in agent lines for a time slot | High |
| TC-004 | Reschedule, more than 4h before | No fee mentioned; request_type = Reschedule | Medium |
| TC-005 | Reschedule, within 4h | $50 fee stated before recording | High |
| TC-006 | Cancel, more than 24h before | No fee; request_type = Cancellation | Medium |
| TC-007 | Cancel, within 24h | $50 fee stated before confirming | High |
| TC-008 | Same-day request | 24-hour rule explained; booking not continued | High |
| TC-009 | Out-of-hours slot | Business hours explained; caller redirected | Medium |
| TC-010 | Confirmation message | Delivered before call ends | High |
