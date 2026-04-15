# Skill: Morning Briefing
# Trigger: /morning or cron at 6:00 AM PT weekdays
# Output: HTML email to david@atakinteractive.com
# Success criteria: Dave opens one email and knows what matters in under 3 minutes

## Step 0: Location Check
Before pulling weather:
1. Check Google Calendar for today's events
2. Look for travel blocks or meeting locations outside Los Angeles
3. If a meeting is in another city, use that city for weather
4. Default to Los Angeles, CA (Sherman Oaks) if nothing suggests otherwise
5. Note the location used in the briefing if it is not LA

## Step 1: Gather All Data
Pull everything before composing.

CALENDAR: All events today. Time, title, location, attendees. Flag events with no description as "needs prep."

TASKS: All Google Tasks. Separate overdue from due today. Flag anything 3+ days overdue as urgent.

EMAIL: Top 3 unread Gmail threads from last 24 hours needing a human response. Skip newsletters, no-reply senders, automated notifications. For each: sender, subject, one sentence why it needs attention.

SLACK: Read for unresolved threads or mentions in last 18 hours:
- #atak-leadership (GJDPYGYN4)
- #atak-bizdev (C09PBCBBFCH)
- #wins (C0CA2DNTZ)
- #rb2b (GTYMSUGV8)
- #ai-and-innovation (C08P6P490UQ)
- #linkedin (C04NPDCUP32)
- #askelephant (C098U8F3ENP)
- #atak-pto (C09T0DEJN02)

WEATHER: Search "weather [LOCATION] today forecast". Pull conditions, high temp, any alerts. Flag if in-person meeting is affected.

AI INTELLIGENCE: Run three searches:
1. site:youtube.com AI automation agency tools this week
2. LinkedIn AI RevOps HubSpot trending posts this week
3. AI news this week site:techcrunch.com OR site:theverge.com OR site:simonwillison.net
Top 3 findings total. Source, topic, one sentence why it matters to a B2B agency founder.

CONTENT ANGLE: Based on AI intelligence, one LinkedIn post angle in Dave's voice. First-line hook only. Not a full post.

RB2B VISITORS: Check Google Sheet for yesterday's site visitors. Surface anyone worth knowing: company, title, pages visited.

HUBSPOT PIPELINE: Deals with activity in last 48 hours. Flag any deal stalled 7+ days.

## Step 2: Monday Check
If today is Monday, add a Monday flag and reminder to run the Weekly 10.

## Step 3: Read Memory
Read memory/priorities.md for weekly focus. Use it for the "Today's Focus" line.
Read memory/open-loops.md and cross-reference anything in today's data.

## Step 4: Compose and Send
Populate the HTML template in skills/morning-email-template.html.
Send via Gmail MCP to: david@atakinteractive.com
Subject: Good morning, Dave — [Day], [Date]

Section order:
1. Header with date and Monday flag if applicable
2. Today's Focus
3. Weather
4. Calendar
5. Tasks
6. Email Triage
7. Slack Digest
8. RB2B Visitors
9. HubSpot Pipeline
10. AI Intelligence
11. Content Angle of the Day

## Step 5: Update Memory
After sending:
- External meetings with no prep context: add to memory/open-loops.md
- Emails Dave has not replied to in 48+ hours: add to memory/open-loops.md
- Tasks 5+ days overdue: flag in memory/open-loops.md

## Failure Handling
- If a data source times out: note it in that section and continue
- If Gmail send fails: save the email to memory/briefings/YYYY-MM-DD.html and print a terminal alert
- Never fail silently
