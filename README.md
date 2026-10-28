# skills

Claude Code skills I use in my own work. I'm Max Parmentier, co-founder of
[Topicflow](https://topicflow.com).

## Install

In Claude Code:

```
/plugin install maxparm --marketplace maxparm/skills
```

Or copy one folder from `skills/` into `~/.claude/skills/` (all your repos)
or `.claude/skills/` (one repo).

## Skills

### `/maxparm:self-performance-review`

An honest mirror for your self performance review. It tells you your 3 to 5
strengths and your 3 to 5 things to improve. Each point has a date or a
link, plus a short quote or a count.

1. It asks for a time range. The default is the last 30 days.
2. It looks at the tools you connected to Claude Code (MCP servers and
   logged-in CLIs). It finds the ones that hold your own words: meeting
   transcripts, chat messages, review comments, ticket comments.
3. You choose the sources. You can also paste text.
4. One subagent reads each source, in parallel. The report groups the
   findings by theme, with evidence from each source.

- **Read-only.** It never posts, comments or sends anything.
- **Your words or your agent's words.** It splits what you wrote yourself
  from what an AI agent wrote for you.

```
/maxparm:self-performance-review
/maxparm:self-performance-review 2026-07-01..2026-09-30
```

### `/maxparm:eli5`

Says the last answer again in simple English. It follows ASD-STE100
Simplified Technical English: short sentences, one idea each, plain words.

- **Same facts.** It runs no tools and adds nothing new.
- **Clear words.** It explains each technical term in one plain sentence,
  and gives one concrete example.
- **Same next step.** It keeps the warnings, numbers, links and the final ask.

```
/maxparm:eli5
/maxparm:eli5 the migration part
/maxparm:eli5 French
```
