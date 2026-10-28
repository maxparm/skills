---
name: self-performance-review
description: Honest feedback on how the user works with people, for a self performance review. It finds the user's own words in the tools they connected (meeting transcripts, chat messages, review and ticket comments), or asks them, and backs each point with dated evidence. Read-only.
disable-model-invocation: true
argument-hint: "[time range, default: the last 30 days]"
---

# Self performance review

The user wants a frank mirror for a self performance review: how they behave
with other people at work, and how those people react. Every claim carries
**evidence**.

They should leave able to say:

> I know my 3 to 5 strengths and my 3 to 5 things to improve, with the dates
> and quotes that prove them, and the themes that show in more than one place.

## Rules

* **Read-only.** Use only list, search and read calls. This is a hard
  guardrail: never post, comment, react, approve, edit, label, assign, create
  or send anything. Every subagent brief repeats it.
* **Evidence.** Each claim has a date or a link, plus a quote of 25 words or
  fewer, or a count. Mark a pattern seen only once as "seen once".
* **The user's behaviour only.** Read what the user said or wrote, and the
  direct replies to it. Never read private 1-on-1s, feedback or reviews that
  other people wrote about the user, or anything the user did not choose.
* **Raw data stays out of the main chat.** Subagents read it and save notes
  to the scratchpad.

## Steps

### 1. Time range

When the argument gives a range, use it. Else ask the user, with "the last
30 days" as the first, recommended answer. Write both dates as `YYYY-MM-DD`.

Done when you have a start date and an end date.

### 2. Find the sources

A **source** is a place that holds the user's own words with other people.
Look at every connected tool (MCP servers, and CLIs that are logged in) and
list the ones that can show, for the range:

| Kind | What to read |
|---|---|
| Meetings | Transcripts with a speaker on each turn |
| Chat | The user's messages in team channels and threads, and the replies |
| Code review | The user's review comments on other people's changes, and their own changes |
| Tickets and docs | The user's comments on issues, tasks and documents |
| Email | Threads the user sent or replied to, with colleagues |

Load the tools you need with one tool search. For each source, check with
one small read call that it works and that it holds data in the range. Find
the user's identity in each source (a "who am I" call, a profile, or their
email). Never guess an identity.

Then show the user the list: each source, its kind, and about how much data
it holds. Ask which ones to use, all selected by default. Also ask:

- Is there a source that is missing, for example a meeting tool that is not
  connected? The user can paste text or give a file path instead.
- For meetings: which recurring meeting shows them best with their team (for
  example the daily stand-up)? Use only that series.

When no source works, say so, and ask the user to connect one or paste text.

Done when the user has chosen the sources, and for each one you know its
tools, the user's identity in it, and the meeting series when it has one.

### 3. Read the sources in parallel

Start one `general-purpose` subagent per chosen source, in one message, in
the background. The brief is `source-brief.md` in this skill's base
directory (shown when the skill loads). In each prompt, give: the time range,
the source kind, the exact tool names, the user's identity in that source,
the meeting series (when it has one), the names of the people the user works
with most (when you know them), and the scratchpad path. Paste the Rules
section above into each prompt. Tell each subagent to read its brief first
and follow it exactly.

Pasted text or a file: read it yourself with the same brief.

Done when every subagent has returned its report.

### 4. Merge and report

1. Check every report against the Evidence rule. Drop a claim without a
   date or link, and without a quote or count.
2. Match the same person across sources (a chat name, a login, an email)
   only when a source proves the match. When a subagent guessed a name, say
   so.
3. Find the 2 or 3 **themes** that appear in two or more sources. A theme
   needs evidence from each of them.
4. Write the report in the format below.

## Report format

Keep it short. Use tables. Mark strengths ✅ and things to improve ⚠️.

1. **Scope:** the time range; per source, what was found, what was read in
   full, and the gaps.
2. **Per source:** 3 to 5 strengths and 3 to 5 things to improve. Each row:
   point, evidence, one concrete suggestion. In a written source, each row
   says its group: **A** (the user's own words) or **B** (an AI agent wrote
   it for them).
3. **Themes across sources:** 2 or 3, each with one fix.
4. **Limits:** transcript errors, how A and B were sorted, what no source
   could show (calls, in-person talks).
5. The full paths of the notes files.
