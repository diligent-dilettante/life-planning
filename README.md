# Life Planning

**Life Planning is a free, open-source Claude skill that coaches one person through what they want, what is getting in the way, and what they are actually going to do about it.** It asks questions instead of handing out templates, keeps one markdown file so sessions compound, and does the tracking so you never maintain a system.

MIT licensed. Works on Claude web, Claude desktop and Claude Code.

```
Settings → Capabilities → turn on Code execution and file creation
Customize → Skills → + → Create skill → upload life-planning.zip
```

## What it does

Most planning tools help you write the plan. The plan is the easy part. Almost nobody fails at the planning session, they fail in week three, when nothing gets looked at, something slips, and the slip reads as evidence the whole idea was naive.

So the weight sits on keeping it alive. A first conversation is twenty minutes, not ninety. The weekly check-in is ten minutes and asks you for one number. You never open a spreadsheet, because any system that needs you to be organised has already failed the person who most needs it.

Every session opens with Claude reading your file and telling you where you stand before you ask. What you set, what you logged, what has not been touched in a month. Three quarters in, that file knows things you do not: which kinds of goals you finish and which you quietly carry, that both stalls happened in the fortnight after a work trip, that a goal with a weekly number attached gets done and one without does not.

## Who it is for

One person. That is the design centre, not a fallback. Everything works if you are the only one who ever uses it.

If you have a partner, the skill adds an optional layer: one question per session worth asking them, and a note of what they have and have not seen. It never depends on them taking part, and it assumes they never will.

## What is in it

| File | What it covers |
|---|---|
| `stance.md` | How to be in the conversation. The most important file here |
| `keeping-it-going.md` | Why plans die, and accountability that survives a bad week |
| `foundations.md` | Maslow rung check, commitments audit, runway, career and business goals |
| `values.md` | Peak moments, disproportionate irritation, values with a cost line |
| `vision.md` | Workview and Lifeview, Odyssey Plans, an ordinary Tuesday three years out |
| `goals.md` | Twelve-week goals, WOOP, if-then plans, lead measures |
| `weekly.md` | Ten-minute check-in, and a thirty-minute one for two people |
| `review.md` | Quarterly scoring and the annual past-year review |
| `stuck.md` | Immunity to Change, decisions, recurring disagreements |
| `money-and-load.md` | Money scripts, household load |
| `facilitation.md` | Session mechanics |

## How is this different from other planning skills

The published alternatives are template systems. They give you the frameworks and the documents, and they assume the hard part is knowing what to write down.

The hard part is week three. This skill spends most of its length there, and on how the conversation is conducted rather than on what the exercises are. `stance.md` is the largest file in the repo and contains no frameworks at all.

Three examples of what that means in practice.

**It holds back the excuse.** When your log shows the goal stalled right after a work trip, it does not say so before asking why you stalled. Offer someone a ready-made external cause and they will take it, sincerely, and the conversation ends there. It asks the open question first and raises the pattern afterwards, if it still matters.

**It will tell you to drop things.** Most people cannot drop a goal, because dropping feels like failing, so they carry it dead for another quarter and it discredits everything next to it. You get asked directly whether you still want it or just do not want to be the person who dropped it.

**It does not grade you.** No praise for a good answer, no concern about a bad number. The moment tracking sounds like judgement, the numbers you report start being wrong.

## Does it work if I do not have a partner

Yes, completely. The skill was rewritten around the single-user case after testing showed partner-shaped scaffolding leaking through. Nothing assumes a partner exists, and the belonging rung, friendships and community, gets watched precisely because there is no partner in the conversation pointing at it.

## Is this therapy

No, and it says so itself. If what surfaces is beyond a planning conversation, a rupture, a loss, anything about safety, the skill says once and plainly that a therapist is the right person, and then returns to the planning work rather than continuing to excavate. It is a coaching tool for goals and direction. It is not a substitute for professional mental health care.

## How it was tested

Six single-turn evaluations against no-skill baselines, then seven multi-turn conversations run between isolated agents. One agent played a person who did not know a skill existed. Another ran the skill and did not know the user was simulated. A third relayed between them and wrote a critique.

The personas were built to attack specific failure modes: someone whose partner is not really interested, someone demanding a full system, someone deflecting a lapse with a plausible excuse, someone for whom a values session turns into a marriage in trouble, someone with no partner at all, and someone about to leave a salary for a business.

Thirty-two defects were found and fixed. The most useful were not bugs in the exercises. They were rules that contradicted each other, and habits that felt warm and were not: grading a disclosure, announcing the mechanic out loud, reassurance dressed up as a statistic, returning someone's words sharpened.

## Frameworks and credits

The exercises are established work, assembled and adapted. None of it is original here, and the debts are large.

**Coaching and change**
GROW, Sir John Whitmore and colleagues at Performance Consultants.
Wheel of Life, attributed to Paul J. Meyer.
Motivational Interviewing and the righting reflex, William R. Miller and Stephen Rollnick.
Person-centred conditions, Carl Rogers.
Solution-Focused Brief Therapy, the miracle question, exceptions and scaling, Steve de Shazer and Insoo Kim Berg.
Immunity to Change, Robert Kegan and Lisa Laskow Lahey.

**Values and direction**
The Bull's Eye values exercise, Tobias Lundgren, popularised by Russ Harris in Acceptance and Commitment Therapy.
Designing Your Life, Workview, Lifeview and Odyssey Plans, Bill Burnett and Dave Evans.
Hierarchy of needs, Abraham Maslow, used here as a diagnostic prompt rather than a hierarchy.
Ikigai and PERMA, Martin Seligman.

**Goals and execution**
WOOP and mental contrasting, Gabriele Oettingen.
Implementation intentions, Peter Gollwitzer.
The 12 Week Year, Brian P. Moran and Michael Lennington.
Lead and lag measures, The 4 Disciplines of Execution, Chris McChesney, Sean Covey and Jim Huling.
Theory of Constraints, Eliyahu Goldratt.
Past Year Review, Tim Ferriss.

**Two people**
State of the Union, ATTUNE, softened start-up and perpetual problems, John and Julie Gottman.
Marriage Meetings, Marcia Naomi Berger, whose contribution is the running order.
Fair Play and the mental load, Eve Rodsky.
Money scripts, Brad Klontz and colleagues.
Joint goals research, Berg and colleagues, [Joint Goals in Older Couples](https://pmc.ncbi.nlm.nih.gov/articles/PMC8093431/).

**Claude skills used to build this**
`whisper`, from [diligent-dilettante/business-planner](https://github.com/diligent-dilettante/business-planner). The interruption discipline in `stance.md` is lifted from it: silence as the default state, a four-question gate before speaking, and the confabulation guard, would I say this if I were not trying to be helpful right now.
`skill-creator`, Anthropic, for the authoring workflow and the evaluation loop.
`humanizer`, for a pass over this README.
`artifact-design`, for the setup guide.

Prior art worth reading if you want a template system rather than a conversation: [gislio/MyPlan](https://github.com/gislio/MyPlan), [tandregbg/goals-skills](https://github.com/tandregbg/goals-skills), [danielrosehill/Claude-Personal-Planning-Plugin](https://github.com/danielrosehill/Claude-Personal-Planning-Plugin).

## Frequently asked questions

**How long is a session?** Twenty minutes for the first one. Ten minutes a week after that. Thirty minutes once a quarter. The long versions exist and are usually the wrong choice.

**Where does my data live?** One markdown file called `life-plan.md`, wherever you keep it. Nothing is uploaded anywhere, nothing is locked in, and you can read the whole thing in five minutes.

**Do I need Claude Code?** No. It runs on Claude web with code execution enabled, which is where most people will use it.

**What if I fall off for a month?** That is the normal case and it is built for. Go back without tidying up first. The skill asks whether it is a bad month or whether the goal is not actually the one, halves what you were doing, and gets you running again without an autopsy.

**Can two people use it?** Yes, separately. Each person runs their own conversation with their own file. Neither reads the other's. Every so often one of you gets a question worth asking the other.

**Will it write my plan for me?** No. It asks the questions and writes down what you said. A plan you were handed is one you will not recognise in November.
