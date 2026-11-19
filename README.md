# ContextSync AI: Ending Meeting Overload and Knowledge Loss

> A product discovery case study by Prasmita Sahu, built during the AI-Powered Product Management & Growth Marketing programme (Masai School x IIM Rohtak).

**In one line:** ContextSync is a background workflow tool that turns meetings into clear, shared decisions and action items, so teams stop holding the same alignment meeting twice.

---

## 1. The problem

Recurring alignment meetings are rarely documented accurately. Decisions get forgotten, owners are unclear, and teams end up repeating the same conversation. A Senior Engineering Manager I spoke to during market research described forgetting Monday's decisions by Thursday.

## 2. What I learned from users (survey, n=20)

I ran a 2-minute anonymous survey with students, interns, working professionals and managers (9 working professionals, 5 students, 4 managers, 2 interns).

![Survey results](survey_results.png)

| Finding | Result |
|---|---|
| Need a follow-up because something was unclear or undocumented (at least sometimes) | **80%** (35% often or almost always) |
| Forget a decision or action item within 3 days (at least sometimes) | **70%** |
| Leave a meeting unsure what was decided or who owns it (at least sometimes) | **60%** |
| Average time lost per week re-asking, clarifying or writing notes | **about 56 minutes** (25% lose an hour or more) |
| Rated a Slack post-meeting summary tool 4 or 5 out of 5 | **85%** (average 4.3; 4.6 among non-students) |
| Take manual notes today | 55% (25% record, 20% rely on someone else) |

**Pain grows with meeting load.** Among people with 8 or more meetings a week (n=7), 57% need follow-ups often or almost always. For people with fewer meetings (n=13) it is 23%.

**The biggest worry is trust, not features.** Privacy concerned 80% of respondents, recording consent 55%, summary accuracy 45%, cost 35% and notification overload 30%. This shaped the MVP below.

*Method note: time lost uses the midpoint of each answer range, and 4+ hours was not a selectable option, so the average is approximate. Survey answers are self-reported.*

## 3. Value Proposition Canvas

- **Customer job:** Leave a meeting with clear decisions, owners and next steps.
- **Pain:** Manual admin logging, forgotten decisions, duplicated conversations.
- **Pain reliever:** Verbal action items are extracted automatically and posted where the team already works (Slack).
- **Gain creator:** Time reclaimed from clarifying and re-asking. The survey shows this is about an hour a week on average, and more for meeting-heavy people.

## 4. Opportunity sizing

I sized the value at the level of one team, using survey data where I have it and clearly labelled assumptions where I do not.

| Input | Value | Source |
|---|---|---|
| Team size | 50 people | Assumption |
| Time lost per person per week | 0.94 hours | Survey average |
| Working weeks per year | 48 | Assumption |
| Cost of an hour of employee time | Rs 500 | Assumption |
| Share of lost time ContextSync recovers | 30% | Assumption, to be tested in the pilot |

- Time lost per team per year = 50 x 0.94 x 48 = **about 2,256 hours**
- Value of that time = 2,256 x Rs 500 = **about Rs 11.3 lakh per team per year**
- Recoverable at 30% = **about 677 hours, or Rs 3.4 lakh per team per year**

Scaling this to a market size needs verified data on how many teams use Slack and similar tools, which I have not collected yet. I would rather leave that out than guess.

## 5. Feature prioritisation (RICE)

Reach (1-100), Impact (0.25-3), Confidence (%), Effort (story points, 1-13). Confidence for F1 reflects the 85% survey demand. Confidence for F3 is lower because 30% worry about notification overload. Scores are my own estimates.

| Feature | Reach | Impact | Confidence | Effort | RICE |
|---|---|---|---|---|---|
| **F1. Post-meeting summary with action items posted to Slack** | 90 | 2.0 | 85% | 3 | **51.0** |
| F3. Reminders for open action items | 70 | 1.0 | 60% | 2 | 21.0 |
| F4. Searchable decision log | 60 | 1.0 | 70% | 4 | 10.5 |
| F2. Auto-update Jira / Notion | 50 | 1.5 | 60% | 5 | 9.0 |

RICE = (Reach x Impact x Confidence) / Effort. F1 wins by a wide margin: it reaches everyone, is cheap to build and removes the core pain directly.

## 6. MVP scope (MoSCoW)

- **Must have:** F1 summary and action items posted to Slack, **opt-in only, with a consent notice at the start of each meeting and summaries visible only to attendees** (driven by the privacy and consent findings).
- **Should have:** F3 reminders, with a frequency cap to avoid notification overload.
- **Could have:** F4 searchable decision log.
- **Won't have (for now):** F2 Jira / Notion auto-sync. It is the most effort for the least confidence, so it waits until the core summary is trusted.

## 7. One metric that matters

**Follow-up rate: the share of meetings that trigger a follow-up message or meeting about something that was unclear.**

Baseline from the survey: 35% of people need a follow-up "often" or "almost always". I chose this metric because the tool succeeds only if teams stop re-explaining the same decisions. Hours saved would be a weaker measure, since it depends on self-reporting.

## 8. Validation plan (Wizard-of-Oz pilot, proposed)

*This pilot has not been run yet. It is the next step.*

- **Setup:** A small Slack group of 8 to 10 people for 2 weeks. Week 1 is the baseline with no summaries. In week 2, I manually write and post a summary with action items after each meeting.
- **Measure:** Follow-up rate in each week, how many people edit or correct the summary, and a 1-5 trust rating.
- **Success threshold:** At least 80% of active users say the summaries prevented a follow-up alignment meeting.
- **Questions it answers:** Do people trust the summaries? Do follow-ups actually fall? Do the negative or private details cause discomfort?

## 9. Risks and how the MVP addresses them

| Risk (share of survey respondents) | Mitigation |
|---|---|
| Privacy (80%) | Opt-in per meeting, attendee-only visibility, clear data retention rules |
| Recording consent (55%) | Consent notice at the start of each meeting; no summary if anyone opts out |
| Accuracy of summaries (45%) | Show summaries as drafts; one-click edit and correct before they are shared |
| Cost (35%) | Free tier for small teams in the pilot; pricing tested later |
| Notification overload (30%) | One summary per meeting, capped reminders, easy mute |

## 10. Prototype

I built an AI prototype of the Slack summary delivery flow using Lovable.

*(Add 1-2 screenshots of the Lovable prototype here.)*

## 11. Limitations

- The survey has 20 responses from my own network, so it is an early signal, not proof.
- Only 5 respondents were students, and they showed lower interest (3.4 out of 5) than working professionals and managers (4.6), so the target user is the working professional.
- Sizing relies on stated assumptions that the pilot should test.

## 12. Next steps

1. Run the 2-week Wizard-of-Oz pilot.
2. Re-measure follow-up rate against the survey baseline.
3. Interview 3 to 5 meeting-heavy managers to dig into the privacy concerns.

## Skills demonstrated

User research and surveys, Value Proposition Canvas, opportunity sizing, RICE and MoSCoW prioritisation, metric definition, Wizard-of-Oz experiment design, AI prototyping (Lovable), risk and privacy thinking.


