# Evals

Eight behaviour evals for the skill. Each is a user prompt plus a list of assertions about
how the facilitator should answer. `evals.json` holds them.

They exist because most of what this skill gets wrong is invisible in a single reading. A
response can be warm, well written, and still spend the whole session diagnosing someone who
came for a plan. Several of the assertions are written to catch exactly that.

## Running them

There is no runner. Give a model the skill and one of the prompts, let it answer, then check
the response against that eval's assertions. For evals 5, 7 and 8 you need a few turns rather
than one, because what they test only shows up once the conversation has somewhere to go.

Two things worth doing if you are comparing versions:

**Script the user's replies.** If each run invents its own user, you are measuring the
simulated user as much as the skill. Fix the user turns in advance and give both versions the
same ones.

**Grade the opening turn separately.** Assertions about headings, tables and question counts
apply to the first response only. Everything after that is a conversation and the rules are
different.

## What each one is for

| Eval | Catches |
|---|---|
| 1, 2 | Regressions in the two commonest openings: a first-timer, and someone whose last attempt died |
| 3 | The opening turn turning into a form. Headings, tables, stacked questions |
| 4 | Reading an interrupt-driven week as a discipline problem |
| 5 | The zero-capacity case. The one most likely to be handled badly |
| 6 | Scoring someone on a rota against a weekly denominator |
| 7 | Latency. Diagnosis quality is worth nothing if the person leaves before the plan lands |
| 8 | Couple-shaped questions asked of someone who lives alone |

Eval 5 is the one to run first if you only run one. It is the case where a plausible, kind,
well-written answer can still fail the person completely, by handing her a considered account
of why she cannot have what she came for.

## Triggering

There are no trigger-rate numbers here, on purpose.

Triggering means whether Claude reaches for this skill at all given a user's message, which
is governed by the `description` in `SKILL.md` rather than by anything in this directory. It
is worth measuring and it is not measured here.

The obvious tool for it is `run_eval.py` in Anthropic's `skill-creator` skill. It did not
work when this suite was written: it reported a 0.0 trigger rate for every query, including
for a skill that was definitely installed and definitely relevant. Because it counts a
non-trigger as a pass for any query marked `should_trigger: false`, a broken run looks like a
healthy 50% score with every negative case passing. Nothing from it is reproduced here, and
any trigger numbers produced that way should be checked against a known-good skill before
they are believed.

If you want to measure triggering, the honest cheap version is to paste the prompts from
`evals.json` into a fresh session with the skill installed and see whether it gets used.
