\# n8n Test Checklist



Run these tests after every workflow JSON change.



\## 1. Telegram input guard



Send non-text message:

\- photo

\- sticker

\- voice



Expected:

\- bot replies: Please send a text message

\- workflow does not fail



\## 2. Booking create



Message:



Book manicure for Anna tomorrow at 3 pm



Expected:

\- Google Calendar event is created

\- client receives booking confirmation

\- admin receives notification

\- event description contains Telegram ID



\## 3. Booking conflict



Message:



Book pedicure for Maria tomorrow at 3 pm



Expected:

\- no duplicate booking is created

\- bot says the slot is busy

\- bot suggests available times



\## 4. Cancel own booking



Message:



Cancel my appointment for Anna tomorrow at 3 pm



Expected:

\- only user’s own event is deleted

\- Telegram ID matches before delete

\- client receives cancellation confirmation

\- admin receives notification



\## 5. Cancel another user’s booking



Use another Telegram account or event with different Telegram ID.



Message:



Cancel my appointment for Anna tomorrow at 3 pm



Expected:

\- event is not deleted

\- bot sends safe fallback response

\- workflow does not fail



\## 6. Reschedule own booking



Message:



Reschedule my appointment for Anna tomorrow at 3 pm to tomorrow at 5 pm



Expected:

\- old event is updated

\- Telegram ID matches before update

\- new slot is checked before update

\- client receives reschedule confirmation

\- admin receives notification



\## 7. Reschedule another user’s booking



Use another Telegram account or event with different Telegram ID.



Expected:

\- event is not updated

\- bot sends safe fallback response

\- workflow does not fail



\## 8. Outside working hours



Message:



Book manicure for Anna tomorrow at 11 pm



Expected:

\- no calendar event is created

\- bot says time is outside working hours



\## 9. All-day blocked calendar event



Create all-day Google Calendar event for test day.



Then send:



Book manicure for Anna on that day at 3 pm



Expected:

\- slot/day must be treated as unavailable

\- no calendar event is created



\## 10. Parse missing details



Message:



Book manicure



Expected:

\- no calendar event is created

\- bot asks for missing details

