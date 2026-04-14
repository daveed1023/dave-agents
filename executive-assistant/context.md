# Executive Assistant Agent — Context and Design

## Purpose
Replace the n8n personal assistant system with a native Claude Code agent that runs daily, handles morning briefing, monitors communications, does research, and manages task queues. This is the most important personal agent in the stack.

## When Dave Works Best
Early morning, before the team is up. The agent should be ready with everything Dave needs before 8am PT so he can think and plan before the day pulls him into reactive mode.

## Core Capabilities (Build Order)
1. Morning briefing (first build)
2. Email triage and flagging
3. Slack review and summarization
4. Task tracking and follow-up queue
5. Research: prospects, clients, topics, competitors
6. Web and content scraping: YouTube, LinkedIn, websites
7. Information filing and knowledge capture
8. Calendar prep: who am I meeting, what do I need to know

## Morning Briefing — Required Sections
Run every weekday before 8am PT. Deliver via Slack or terminal output.

1. Date and day context (any notable events, holidays, deadlines)
2. Calendar: today's meetings with attendee context and prep notes
3. Email: flagged items requiring action (not a full inbox dump)
4. Slack: summary of overnight and early messages worth knowing
5. Open tasks: what's overdue, what's due today, what's blocked
6. RB2B visitors: who visited the ATAK site yesterday worth knowing about
7. One news item relevant to AI, RevOps, or ATAK's clients
8. HubSpot pipeline snapshot: deals moving, deals stalled, new activity

## Research Capability Design
The agent should be able to:
- Search the web for any topic and return a structured brief
- Scrape a website and return copy, structure, or specific data points
- Pull a YouTube video transcript and summarize or extract key points
- Search LinkedIn for a person or company and return a profile summary
- Research a prospect before a meeting: company, recent news, key people, HubSpot record status
- Monitor specific sources (blogs, news, LinkedIn profiles) for new content

Human review required: any research output that will be used in client-facing communication, any financial or legal data, any claim that will be cited publicly.

Hallucination risk: high on specific statistics, recent news, and people's current roles. Always note source and date. Flag when data could not be verified.

## Information Filing System
When Dave shares something worth keeping, the agent should:
- Categorize it (client intel, competitor intel, idea, task, reference)
- Store it in the appropriate location in dave-agents or dave-skills
- Surface it when relevant in future sessions

## Task Queue Design
- Capture tasks from any source: email, Slack, voice note, conversation
- Tag by: owner, project, client, due date, priority
- Surface blockers: tasks waiting on others
- Daily: show what's overdue and what's due today
- Weekly: show what's been sitting untouched for 7+ days

## What the Best EA Agents Are Doing in 2025-2026
Based on current research, the most effective personal EA agents built by operators and founders:

- **Weekly synthesis emails**: every Friday, a summary of the week pulled from calendar, email, and Slack. What was decided, what was promised, what needs follow-up. (Diego Oppenheimer model)
- **Pre-meeting briefs**: 30 minutes before each meeting, a one-page brief on who's attending, what was discussed last time, what the goal is today, and any relevant news about them
- **Inbox zero sprints**: not just triage, but drafting replies for Dave's review — reduces email from a writing task to an approval task
- **Proactive monitoring**: watching for triggers (a prospect visits the site, a client goes quiet, a competitor publishes something) and surfacing them without being asked
- **Knowledge capture**: when Dave has a breakthrough or learns something, the agent files it so it's findable later — not lost in chat history
- **Narrow agents coordinated by one orchestrator**: the architecture that works is not one giant agent but several focused ones (email agent, calendar agent, research agent, briefing agent) coordinated by a central EA that routes tasks to the right sub-agent

## What Dave's EA Agent Is NOT
- Not a replacement for human judgment on sensitive decisions
- Not a source of truth for financial or legal matters (routes to those agents)
- Not a content publisher — drafts for Dave's review, never posts autonomously
- Not always-on in the background monitoring everything — runs on schedule and on demand

## Technical Notes
- Build natively in Claude Code, not n8n
- Start with morning briefing as the first working piece
- Add capabilities one at a time, confirm each works before adding the next
- Terminal commands and scripts are fine — Dave will run them if instructed clearly
- Teach the pattern when building each new capability so Dave understands what it does

## Connections Needed (Build Order)
1. Google Calendar (already connected via MCP)
2. Gmail (already connected via MCP)
3. Slack (already connected via MCP)
4. HubSpot (already connected via MCP)
5. Web search and scraping
6. RB2B data feed (was reading from Slack #rb2b channel)

## Failure Modes
- Briefing that's too long gets ignored — keep each section tight, surface exceptions not everything
- Research that doesn't cite sources is a liability — always include URL and date
- Task queue that grows without getting done creates anxiety not clarity — flag and escalate, don't just accumulate
- Agent that requires too much setup each session defeats the purpose — context should be persistent
