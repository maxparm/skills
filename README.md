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
4. One subagent reads each source, in parallel. The report shows the themes
   that appear in more than one source.

- **Read-only.** It never posts, comments or sends anything.
- **Your words or your agent's words.** It splits what you wrote yourself
  from what an AI agent wrote for you.

```
/maxparm:self-performance-review
/maxparm:self-performance-review 2026-07-01..2026-09-30
```
