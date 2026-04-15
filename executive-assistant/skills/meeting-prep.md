# Skill: Meeting Prep
# Trigger: /prep [meeting name] OR auto-fires 30 minutes before external calendar events
# Output: Printed to terminal or saved to memory/meeting-prep/YYYY-MM-DD-[meeting].md
# Success criteria: Dave walks in knowing who, why, what to say, what to ask

## When This Fires Automatically
30 minutes before any calendar event where:
- At least one attendee is NOT an ATAK team member
- OR the location is outside the office
Does not fire for internal recurring meetings unless Dave runs /prep manually.

## What to Pull

MEETING BASICS: Title, time, location or video link, attendees, agenda. Flag if no agenda exists.

ATTENDEE RESEARCH:
- Check memory/contacts.md first
- If not found: web search [name] [company] for LinkedIn profile and recent news
- For each external attendee: company, role, any recent news about them

EMAIL HISTORY:
- Search Gmail for threads with attendee email addresses from last 90 days
- Surface: last touchpoint, any open items, anything promised and not delivered

HUBSPOT:
- If attendee or company is in HubSpot: pull deal stage, last activity, notes

OPEN LOOPS:
- Check memory/open-loops.md for anything connected to this person or company

## Output Format

MEETING PREP: [Event Title]
[Time] · [Location or Link]

WHO YOU ARE MEETING
[Name] — [Title], [Company]
[One sentence context or recent news]

LAST TOUCHPOINT
[Date and summary of last email or meeting]

OPEN ITEMS
[Anything owed to them or owed by them]

SUGGESTED TALKING POINTS
1. [Point]
2. [Point]
3. [Point]

WATCH FOR
[Sensitive topics, past friction, or pending decisions]

## After the Meeting
When Dave types /debrief:
- Capture what was decided, what was promised, next steps, who owns what
- Write decisions to memory/decisions.md
- Write open items to memory/open-loops.md
- Update memory/contacts.md with any new context about the attendees
