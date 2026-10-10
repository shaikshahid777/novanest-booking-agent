# Test Results

Demo video with all four calls: https://www.loom.com/share/d7a16178b492428ba0942ea2fdb25e23

Fill in Result (PASS/FAIL) and notes after reviewing each call in Retell Call History.

## Call 1: New booking, three windows (TC-001, TC-003, TC-010)
- Caller: Mia Torres, buyer consultation, 312 555 0247, mia.torres@email.com
- Windows: Tue Oct 13 10 AM CT, Wed Oct 14 2 PM CT, Thu Oct 15 11 AM CT
- Result: [ ] PASS  [ ] FAIL
- Confirmation message delivered: [ ] Yes
- Availability language found in agent lines: [ ] None
- Screenshot: screenshots/call1_pca.png

## Call 2: Cross-timezone (TC-002)
- Caller: John Smith, seller consultation, window given without timezone, then "Eastern Time"
- Result: [ ] PASS  [ ] FAIL
- preferred_window_1 includes ET: [ ]  caller_timezone = ET / America/New_York: [ ]
- Screenshot: screenshots/call2_pca.png

## Call 3: Cancellation within 24 hours (TC-007)
- Original reference: Monday October 12 at 10 AM
- Result: [ ] PASS  [ ] FAIL
- $50 fee stated before cancelling: [ ]  request_type = Cancellation: [ ]
- Screenshot: screenshots/call3_pca.png

## Call 4: Same-day disqualification (TC-008)
- Caller: "Can I get a consultation today at 3 PM?"
- Result: [ ] PASS  [ ] FAIL
- 24-hour rule explained: [ ]  Booking not continued: [ ]
- Screenshot: screenshots/call4_transcript.png

## Availability language audit (TC-003)
Searched Call 1 transcript for "available", "confirmed", "booked", "secured" in agent lines: [ ] 0 occurrences
