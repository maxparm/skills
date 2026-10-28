---
name: eli5
description: Say the last answer again in Simplified Technical English (ASD-STE100), with plain words, short sentences and a concrete example, so the user understands it on the first read. Adds no new facts and runs no tools. Use when the user types /eli5, or says "ELI5", "simpler", "I don't get it", "say it again", "explain like I'm 5", or "in simple English".
argument-hint: "[nothing, or the part to explain again, or a language such as French]"
---

# ELI5

Sometimes an answer is correct but too dense. English may be the user's
second language, or the topic may be new to them. This skill writes the same
answer again, in simple words.

The user should leave able to say:

> I understand what the last answer said, and I know what to do next.

## What to rewrite

* **No argument:** your last message to the user, before they typed /eli5.
* **An argument that names a part** ("the migration part", "point 3"):
  only that part.
* **An argument that is a language** ("French", "fr"): the last message,
  in that language. Keep code, file names and commands as they are.

## Rules

* **Same facts. Nothing new.** Do not run tools. Do not change a decision,
  a number, a file path or a recommendation. If the old answer was wrong,
  say so in one line at the end. Do not fix it silently.
* **Keep everything that matters.** Warnings, risks, numbers, links and the
  ask at the end stay in. Remove only padding.
* **Short sentences.** At most 20 words. One idea in each sentence.
* **Active voice.** "The job deletes the rows", not "The rows are deleted".
* **Simple words.** Use "use", not "leverage". Use "start", not "initiate".
  Use "because", not "due to the fact that".
* **One word for one thing.** Do not call the same thing "job", "task" and
  "worker". Pick one word and keep it.
* **Define each technical term** the first time, in one plain sentence.
  Example: "A migration is a script that changes the shape of the database."
* **Give one concrete example** from the user's own case, not an abstract
  one. If the idea is abstract, add one everyday comparison (a kitchen, a
  post office, a queue at a shop).

## Output

Use this shape. Leave out a part that has nothing in it.

```
**In one line:** <the answer, 1-2 sentences>

**Step by step:**
1. <one idea>
2. <one idea>
3. <one idea>

**Example:** <a concrete case, 2-3 sentences>

**Words:**
| Word | Meaning |
|---|---|
| <term> | <one plain sentence> |

**Your next step:** <the same one ask as the old answer>
```

At most 5 steps. At most 5 words in the table. Then stop.
