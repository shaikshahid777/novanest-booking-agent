# Post-Call Analysis Fields

| # | Name | Type | Allow empty | Description |
|---|---|---|---|---|
| 1 | caller_first_name | Text | No | First name as confirmed during the call. |
| 2 | caller_last_name | Text | No | Last name with confirmed spelling. |
| 3 | caller_phone | Text | No | 10-digit phone number as confirmed by digit repeat-back. Digits only. |
| 4 | caller_email | Text | No | Email address as confirmed by character spell-out. |
| 5 | service_type | Selector | Yes | Buyer Consultation / Seller Consultation / Investment Review |
| 6 | preferred_window_1 | Text | Yes | First preferred window including timezone. |
| 7 | preferred_window_2 | Text | Yes | Second preferred window including timezone; empty if not provided. |
| 8 | preferred_window_3 | Text | Yes | Third preferred window including timezone; empty if not provided. |
| 9 | caller_timezone | Text | Yes | Caller's timezone if different from CT (e.g. ET / America/New_York); empty if CT. |
| 10 | booking_notes | Text | Yes | Additional context or constraints; empty if none. |
| 11 | request_type | Selector | No | New / Reschedule / Cancellation |
| 12 | original_booking_reference | Text | Yes | Original date/time or reference for reschedule or cancellation; empty for new. |

"Save to contact field" is OFF for all fields.
