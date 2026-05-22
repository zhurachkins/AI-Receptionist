# n8n Test Checklist

Run these tests after every workflow JSON change.

## 1. Telegram Input Guard

Send non-text messages:

- Photo
- Sticker
- Voice

Expected:

- Bot replies: `Please send a text message`
- Workflow does not fail.

## 2. Booking Create

Message:

```text
Book manicure for Anna tomorrow at 3 pm
```

Expected:

- Google Calendar event is created.
- Client receives booking confirmation.
- Admin receives notification.
- Event description contains Telegram ID.

## 3. Booking Conflict

Message:

```text
Book pedicure for Maria tomorrow at 3 pm
```

Expected:

- No duplicate booking is created.
- Bot says the slot is busy.
- Bot suggests available times.

## 4. Cancel Own Booking

Message:

```text
Cancel my appointment for Anna tomorrow at 3 pm
```

Expected:

- Only the user's own event is deleted.
- Telegram ID matches before delete.
- Client receives cancellation confirmation.
- Admin receives notification.

## 5. Cancel Another User's Booking

Use another Telegram account or an event with a different Telegram ID.

Message:

```text
Cancel my appointment for Anna tomorrow at 3 pm
```

Expected:

- Event is not deleted.
- Bot sends a safe fallback response.
- Workflow does not fail.

## 6. Reschedule Own Booking

Message:

```text
Reschedule my appointment for Anna tomorrow at 3 pm to tomorrow at 5 pm
```

Expected:

- Old event is updated.
- Telegram ID matches before update.
- New slot is checked before update.
- Client receives reschedule confirmation.
- Admin receives notification.

## 7. Reschedule Another User's Booking

Use another Telegram account or an event with a different Telegram ID.

Expected:

- Event is not updated.
- Bot sends a safe fallback response.
- Workflow does not fail.

## 8. Outside Working Hours

Message:

```text
Book manicure for Anna tomorrow at 11 pm
```

Expected:

- No calendar event is created.
- Bot says time is outside working hours.

## 9. All-Day Blocked Calendar Event

Create an all-day Google Calendar event for the test day.

Then send:

```text
Book manicure for Anna on that day at 3 pm
```

Expected:

- Slot/day is treated as unavailable.
- No calendar event is created.

## 10. Parse Missing Details

Message:

```text
Book manicure
```

Expected:

- No calendar event is created.
- Bot asks for missing details.
