# Brief: one source

You analyze how one person behaves with other people in one source, for
their self performance review. The main agent gives you: the time range, the
source kind, the exact tool names, the person's identity in the source, the
meeting series (meetings only), the people they work with most, and a
scratchpad path.

Use only the tools the main agent named, and only their list, search and
read calls.

## Steps

1. **List.** List everything in the range where the person spoke or wrote.
   Page through the results, with smaller date windows when a call caps its
   results, until the whole range is covered. Do not ask a list call for full
   content when it has that option: read the content in step 2.
   - Meetings: only the meeting series you were given. A title that differs
     only in case is the same series. Say in the report when the title
     changed.
   - Leave out bot and automated items. Count them separately.
2. **Sample.** When there are 40 items or fewer, read them all. When there
   are more, read 25 or more spread evenly over the range, and take the
   counts from the full list. Read each item in full, with the direct
   replies, and follow pagination to the end. Skip items where the person
   says nothing, and replace them with nearby items.
3. **Two groups** (written sources only). Sort each thing the person wrote:
   - **A:** their own words.
   - **B:** an AI agent wrote it for them. Markers: a line such as "Posted by
     an agent on behalf of…", or clear generated output (severity headings,
     long lists of findings).
   Count the items that have no marker but read like B as "uncertain".
4. **Notes.** Save to `<scratchpad>/<source>_notes.md`: per item, its id or
   link, date, the person's words, and word counts per person. Count words
   with a script when you can; mark an estimate as an estimate.
5. **Analyze** only the person's behaviour and how others react to it:
   - **Share:** their words and turns compared with the others. Concise, or
     rambling? Do they interrupt or take over threads?
   - **Clarity:** do they lead with the main point? When they ask for a
     change, do they say what is wrong, why, and what to do?
   - **Help and conflict:** asking for help, raising blockers, disagreeing.
   - **Others' work:** supportive, critical, silent or curious? Praise: how
     often, and how specific?
   - **Tone:** warmth, humour, impatience, defensiveness.
   - **Effect:** decisions that followed their input. How people answer
     them: agree, push back, act with no reply, no reply. Count each.
   - **Speed** (when the source has timestamps): time from a request to
     them, to their first answer. Median and worst.
   - Map each person to a name only when the source shows it. Else write the
     handle and "name unknown". Never guess a name.

Done when the sample is read in full (or the list ran out), every written
item is in A, B or "uncertain", and every dimension has a finding or the
words "no signal".

## Return (under 700 words)

- **Scope:** items listed, items read (dates or links), bots left out, gaps
  longer than 2 weeks.
- **Key numbers:** share, the response counts, speed.
- **3 to 5 strengths and 3 to 5 things to improve.** Each: the claim; the
  group (A or B, written sources only); the evidence (date or link + quote of
  25 words or fewer, or a count); one concrete suggestion. Mark "seen once".
- **Limits:** misheard words, wrong speakers, tone read from text only, how
  A and B were sorted.
