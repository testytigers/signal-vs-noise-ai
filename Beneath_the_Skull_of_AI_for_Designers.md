# Beneath the Skull of AI

### A designer's guide to how it actually works

**By Oussama Bougnouch**
uxintoax.com

---

## Before we start

You keep hearing that AI is going to change your job. You've tried it. Sometimes it's useful. Most of the time it produces something that looks right and is quietly wrong.

So you're stuck between two crowds.

One crowd says you're finished. Learn to prompt or get replaced. They usually have a course to sell you.

The other crowd shares screenshots of AI failing at basic math and goes back to work. They feel safe. They're not.

Both crowds start from a belief instead of a test. The first believes it's over before trying anything. The second believes it's nothing without ever engaging. Belief without evidence is how people make bad decisions about their careers.

This book takes a third position: understand the machine, then decide.

Not the marketing version. Not the doomsday version. The actual mechanics — what it does, why it fails the way it does, and what that means for the work you do every day.

**Who this is for**

Product and UX designers. You don't need to code. You don't need math. If you can read a Figma file, you can read this.

**What it will not do**

It won't teach you prompts. Prompt tricks age in months, and the models keep getting better at understanding plain requests anyway. This book teaches the layer underneath, which doesn't move.

**What you'll be able to do at the end**

Look at any AI output and know why it came out that way. Know when to trust it and when to check. Know what to feed it. And know what it will never do for you — which, honestly, is the part that should make you feel better about your job.

Let's open it up.

---

## Contents

**Part 1 — How it thinks**
1. It just predicts the next word
2. Why it lies to your face
3. What it can actually see

**Part 2 — How you work with it**
4. Garbage in, garbage out
5. Listening is a skill, and AI doesn't have it
6. What it's good at, what it's terrible at

**Part 3 — Why it fails and how you plan around it**
7. The agent that lied to me
8. Two architects in the desert

**Part 4 — Going independent**
9. Why you'd want your own
10. Running your own, the short version

---

# Part 1 — How it thinks

# Chapter 1: It just predicts the next word

Read this sentence and finish it in your head:

*"The sky is blue, but the grass is ___."*

You said green. You didn't look it up. You didn't reason about chlorophyll. The word was just there, because you've read and heard that pattern thousands of times.

That's the whole trick. That is what a large language model does.

It reads what came before, and it predicts what comes next. Then it does it again. And again. One piece of text at a time, until it stops.

That's it. There is no other secret layer.

## How it got that way

Someone took an enormous pile of text — books, websites, articles, code, forum arguments, documentation — and fed it to a program.

The program plays a game with itself. It looks at a sentence with the last word hidden. It guesses. Then it checks the real answer. If it was wrong, it nudges its internal numbers slightly. Then it does it again.

Billions of times. For weeks or months.

At the end, you don't have a program that knows facts. You have a program that has absorbed the *shape* of language — how sentences tend to go, how ideas tend to connect, how an argument tends to be built.

## Where the knowledge lives

Here's the part that surprises people: the model doesn't have a database inside it. There's no folder of facts it looks things up in.

Think of a show you've watched many times. You don't have the episodes stored in your head frame by frame. But ask you what happened in a particular scene and you can describe it. You absorbed the patterns.

That's the model. It hasn't stored any article you can point to. It has absorbed how text about that topic tends to go.

This explains a lot of behavior that otherwise looks random.

## What "parameters" actually means

You'll see models described as 8B, 27B, 70B. That's billions of connections — the internal numbers that got nudged during training.

More connections mean more capacity to hold patterns. Roughly, a bigger model can handle more complexity.

But bigger doesn't automatically mean better. A smaller model trained carefully on good material often beats a bigger one trained sloppily. Size is potential, not quality.

## Why this matters for your work

Every strange thing AI does traces back to this chapter.

It writes fluently about things it has no idea about — because fluency is the thing it was trained on, not accuracy.

It agrees with you too easily — because agreeable text is more common in its training material than confrontation.

It produces a design critique that sounds like a senior designer wrote it — because it has absorbed thousands of design critiques, and it's very good at producing text shaped like one. Whether the critique is *correct* about your specific screen is a separate question the machine never asked.

Hold onto that last distinction. It's the whole book.

> **The one line to remember:** it is not answering your question. It is producing text that looks like an answer to your question. Most of the time those are the same thing. The trouble is in the gap.

---

# Chapter 2: Why it lies to your face

Ask a model for research on a topic and it might hand you three sources: an author, a title, a year, a journal. Clean and specific.

Go look for them. Sometimes one doesn't exist. The author is real. The journal is real. The paper was never written.

Everyone calls this hallucination, which makes it sound like a malfunction — like the machine slipped and saw something.

It's not a malfunction. It's the machine working exactly as designed.

## Why it happens

Go back to chapter 1. The model predicts what text should come next.

You asked for a citation. In everything it has ever read, what follows a request like that? A citation. Author, title, year, journal.

So it produces one. Correctly shaped. Perfectly plausible. Completely invented.

The machine has no separate step where it checks whether the thing it just produced exists in the world. There is no fact-checking module. Prediction is the only step there is.

## It cannot tell that it doesn't know

This is the part designers most need to internalize.

When you don't know something, you feel it. There's a sensation — a gap, an uncertainty. It's why you say "I think" or "let me check."

The model has no such sensation. Every output is the same operation. The answer it's confident about and the answer it fabricated are produced by exactly the same process, and they come out with exactly the same tone.

That's why the fake citation looks identical to the real one. There's no tell. The confidence isn't a signal about the truth — it's just the default voice.

## Where this bites in design work

It's rarely dramatic. It's usually small enough to slip through.

You paste in twelve interviews and ask for themes. It gives you five, cleanly named. Four are actually in the transcripts. The fifth is a theme that *commonly appears* in interviews like these — plausible, useful-sounding, not in your data.

You ask for a competitor's onboarding flow. It describes one. It sounds right. It's a blend of onboarding flows in general.

You ask whether a pattern follows accessibility guidance. It says yes, and cites a guideline number. The guideline is real. It says something slightly different.

None of these are obvious errors. That's what makes them expensive. A wrong answer that looks wrong costs you nothing. A wrong answer that looks right ends up in a slide deck in front of a client.

## The rule that follows

You don't fix this with better prompting. You can reduce it — asking it to work only from material you provide helps a lot — but you can't remove it, because it isn't an error state. It's the machine.

So the rule is simple and it never changes:

**Anything factual that came out of a model gets checked before it goes anywhere it matters.**

Every claim, every number, every citation, every "the research says." Not because the model is bad. Because verification is the part of the job the machine structurally cannot do, which means it stayed with you.

We'll come back to this in chapter 7, where I'll show you what it cost me to learn it properly.

> **The one line to remember:** it doesn't know when it doesn't know. Confidence tells you nothing about correctness.

---

# Chapter 3: What it can actually see

This is the most useful chapter in this book for your day-to-day work, and almost nobody teaches it.

Ask the same question twice and get two different answers, and it feels unreliable. Have a long conversation and watch it forget what you agreed at the start, and it feels broken.

Neither is a bug. Both come from one idea: **context**.

## The window

The model has no memory between messages. None. It doesn't remember you, your project, or yesterday.

What it has is a window — everything currently in front of it. Your question, the conversation so far, anything you pasted, and any instructions the app is quietly adding.

Every time you hit send, the model reads that whole window from scratch and predicts what comes next. Then it forgets everything again.

There's no continuity. Each response is a fresh read of whatever is currently on the table.

## Why this explains so much

**Why the same question gives different answers.** The window wasn't identical. Different conversation before it, different result. There's also a deliberate bit of randomness in how the next word gets picked, so even the same window can vary.

**Why it forgets mid-conversation.** The window has a size limit. Go past it and the earliest part falls out. It's not ignoring what you said. That text is no longer there.

**Why it suddenly gets worse in long chats.** Same cause. Your good instructions from the beginning have scrolled out. What's left is the recent, messier part.

**Why the app version behaves differently from the raw model.** The app is putting its own instructions in the window before yours.

## The craft part

Here's the shift that changes how you work: **what you put in the window matters far more than how you phrase the request.**

Designers spend enormous energy on wording. Better verbs, better structure, "act as a senior researcher." Modern models don't need much of that. They understand plain requests.

What they can't do is guess at material they haven't been given.

Compare these two:

*"Summarize the main usability problems users have with checkout flows."*

You'll get a competent, generic answer about checkout flows in general. Assembled from everything it has read. Nothing to do with your product.

*"Here are 40 support tickets about our checkout. [paste] Group them by underlying problem and tell me which group appears most."*

Now it's working on your actual situation.

Same model. Same effort from you, roughly. Completely different value. The difference isn't the phrasing — it's what was in the window.

This is why "prompt engineering" was always a bit of a distraction. The leverage was never in the wording. It's in what you feed it. Which is the next chapter.

## Practical habits

**Paste the real thing.** The transcript, the tickets, the actual copy. Don't describe your material — provide it.

**Start fresh often.** When a conversation drifts or degrades, don't fight it. New conversation, paste what matters, go again. Long chats accumulate junk.

**Put the important instruction near your question.** In a long window, the recent part carries more weight than something from twenty messages ago.

**Say what to ignore.** If you paste a long document and only care about one section, say so. Everything in the window competes for attention.

**Watch for silent truncation.** If you paste something very long, part of it may not fit. If the answer ignores the end of your document, that's usually why.

> **The one line to remember:** it can only work with what's in front of it right now. Your job is deciding what goes in front of it.

---

# Part 2 — How you work with it

# Chapter 4: Garbage in, garbage out

You now know the model only works with what's in front of it. So the real question for a designer is: what do you put there?

Which is really an older question wearing new clothes. **What do you start your design work from?**

Let me put it as a food chain.

## The data food chain

**Plankton.** You open Figma and start pushing pixels. You're starting from your own taste and whatever you saw on Dribbble last week.

**Shrimp.** You sketch on paper first. Better — you're thinking about structure before decoration — but the source is still just you.

**Carp.** You start from whatever the PM handed you. A brief, a ticket, a requirement. Now there's outside input, though you didn't gather it and you can't interrogate it.

**Dolphin.** You did five user interviews. This is the standard advice and it's a real improvement. You've heard actual users in their own words.

**Shark.** Interviews plus a survey. Now you have the *why* from a few people and the *how many* from a lot of them. You can tell whether the thing you heard is common or unusual.

**Whale.** You're working from thousands of real signals. Support tickets. Session recordings. Product analytics. Search logs. Chat transcripts. Not what users said in a room with you — what they actually did when nobody was watching.

Most designers spend their career between plankton and dolphin. Not because they're lazy. Because reading 10,000 support tickets was never realistic for one person in one sprint.

## What changed

That's the part AI actually changes, and it's bigger than anything it does with pictures.

Reading volume used to be the bottleneck. A machine that reads well and tags consistently removes it.

I did this at Sobrus. 10,820 support tickets — years of accumulated complaints nobody had ever read end to end, because who has the time. With AI doing the reading and tagging, that pile became five clear failure patterns and a prioritized roadmap in days.

Not a summary. Evidence. When you walk into a meeting and say *"this problem appears in 1,400 tickets over 18 months,"* the conversation changes. Nobody debates your taste.

That is the whale position, and it used to be available only to teams with a data analyst.

## The catch

Now the honest part, because the ladder isn't the whole truth.

**Bigger data isn't automatically better data.** A whale drowning in noise loses to a shark asking the right question.

Ten thousand tickets full of password resets will tell you people forget passwords. True, useless, and you burned a week finding out.

Size raises your ceiling. It doesn't raise your floor. What raises your floor is knowing what you're looking for and what you'd do about it.

There's a second catch. Machine reading is only as good as its instructions. Tell it to "find themes" and it'll find themes that look like themes — some real, some generic (see chapter 2). Tell it what you're specifically trying to learn, ask for a ticket ID next to every claim, and you get something you can actually verify.

## How to move up the chain this month

Don't try to jump to whale. Go up one level from wherever you are.

**Plankton or shrimp?** Get one real input before your next project. Any input. Ten support tickets. One recorded call.

**Carp?** Ask the PM where their brief came from, then go read that source yourself.

**Dolphin?** Add numbers. Even a small survey to a few hundred users tells you if what you heard is common.

**Shark?** Find the pile nobody has read. Every company has one — the ticket backlog, the app store reviews, the chat logs, the cancelled-subscription reasons. That's your whale.

One level up. Then repeat.

> **The one line to remember:** the model is only ever as good as what you put in front of it. Your seniority is mostly decided before you open the tool.

---

# Chapter 5: Listening is a skill, and AI doesn't have it

If chapter 4 was about volume, this one is about depth. And it's the chapter where you find out what part of your job is safe.

Most designers today have no direct contact with users. Everything arrives filtered — through a PM, a ticket, a stakeholder's opinion.

Of the ones who do have contact, many use it badly. Not carelessly. Badly in a specific, invisible way.

There are levels to this.

## Level 1 — You believe them

The user says *"I want a dashboard with all my numbers on one screen."* You build a dashboard with all their numbers on one screen.

You did what they asked. You were responsive. Everyone felt heard.

You also outsourced your job. Users are experts in their problem and amateurs at solutions. They describe the fix they can imagine, which is limited to interfaces they've already seen.

Following the user blindly destroys most of the value of talking to them.

## Level 2 — You interpret

Better. Now you interview, listen, and form your own understanding of what's actually going wrong. Then you design a solution the user never described.

The user said *"I want everything on one screen."* You dig, and find they're not asking for density — they're afraid of missing something urgent. So you don't build a wall of numbers. You build an alert.

This is where most competent designers work. It's real skill.

## Level 3 — You ask why the problem exists

The highest level isn't looking for a problem to solve. It's asking why there's a problem here at all.

Same case. The user is afraid of missing something urgent. Level 2 designs a better alert.

Level 3 asks: why is this person responsible for catching urgent things by staring at a screen? Should this situation exist? Who decided this was their job? What upstream thing produces these emergencies?

Sometimes the answer is that the problem shouldn't be there. The fix isn't a better interface — it's removing the need for the interface. That's the deletion nobody asks for and everybody benefits from.

That's the highest form of empathy in this work. Not "what do you want," not even "what do you need." **Why are you in this position at all.**

## Where AI sits

Now the useful part.

**AI is good at level 1.** It can take what people said and reorganize it. Reliably, at volume.

**AI can assist at level 2.** Give it enough material and it will spot patterns you'd miss and propose interpretations. Some will be good. Some will be the generic ones from chapter 2. You're still the judge.

**AI cannot do level 3.** Not because it's not smart enough yet. Because level 3 requires something it doesn't have: a stake in the outcome, and a model of the organization the user is trapped inside.

Asking why a problem exists means questioning decisions made by people with power, in a specific company, with a specific history. It means being willing to tell a stakeholder that the feature they requested shouldn't be built. A prediction machine has no reason to do that, and no way to know it's worth doing.

## What this means for your job

Every conversation about AI replacing designers is really a conversation about which level it can reach.

If your work is level 1 — take input, arrange it, produce screens — then yes, a large part of that is going to be automated, and pretending otherwise doesn't help you.

If you work at level 3, you're not competing with the machine at all. You're operating in a place it structurally cannot reach.

The good news is that level 3 is a habit, not a talent. It's one extra question, asked before you start solving:

*Why does this problem exist in the first place?*

Ask it every time. In every kickoff, on every ticket, before every research plan. Most of the time the answer is boring. Occasionally it saves six months of work.

> **The one line to remember:** AI can organize what users said. It cannot ask why they're in that situation. That question is the job.

---

# Chapter 6: What it's good at, what it's terrible at

Enough theory. Here's the practical map.

## Genuinely good at

**Reading volume.** The headline capability. It will read 10,000 tickets without getting tired, bored, or biased by the last one it read. This is the one that changes what a designer can do alone.

**Consistent tagging.** Give it a category scheme and it'll apply it the same way on item 1 and item 4,000. Humans drift. Machines don't.

**Summarizing material you provide.** Long documents, calls, threads. Reliable when the source is in the window. Unreliable the moment it's working from memory.

**Finding patterns you'd miss.** Not because it's smarter, because it can hold the whole pile at once while you can only hold a few pieces.

**First drafts of anything.** Research plans, interview guides, survey questions, screen copy, presentation structure. The blank page problem is solved. A mediocre draft you fix is faster than a blank page you fill.

**Translation and tone shifts.** Between languages, and between registers — turning your rough thinking into something client-ready.

**Explaining things to you.** Technical concepts, unfamiliar domains, what a developer meant. It's a patient tutor that never makes you feel stupid for asking again.

## Genuinely terrible at

**Knowing what matters.** It will give you fifteen findings, all equally weighted. Which three should change the roadmap? That's judgment. It has none.

**Your specific users.** It knows how people in general behave. It doesn't know that your users are pharmacists working under time pressure with gloves on. That lives with you.

**Anything it can't check.** Facts, numbers, citations, "the research shows." See chapter 2.

**Saying no.** Ask it to critique your design and it will find something. Ask it whether your idea is any good and it will usually find a way to like it. It is trained to be helpful. Helpful and honest are not always the same.

**Original strategy.** It produces the average of what has been done before, and it's genuinely good at that. But averages are, by definition, not new.

**Knowing what it did.** This one gets its own chapter. Next.

## The shape of the split

Look at those lists and a pattern shows up.

It's good at **volume, consistency, and speed.**
It's bad at **judgment, specificity, and truth.**

Which means the useful working arrangement isn't complicated: **let it read, you decide.**

Sobrus again. AI read 10,820 tickets, tagged and grouped them. Five patterns, no complaints, no fatigue.

Then a human — me — looked at those five groups and decided which two actually mattered, what they meant about the product, and what to do first. That took knowing the business, the roadmap, and what the team could realistically ship.

The machine did the part that was impossible for a person. The person did the part that's impossible for a machine. That's the whole model, and it's not going away soon.

## A test you can use

When you're deciding whether to hand something to AI, ask:

**Would a smart, fast intern who knows nothing about my company do this well?**

If yes, hand it over. Reading, tagging, summarizing, drafting, formatting.

If no — because it needs judgment, context about your organization, or a decision someone will be held accountable for — that's yours. Not because AI can't produce something. Because you can't verify what it produces without doing the thinking anyway.

> **The one line to remember:** let it read, you decide. It's an intern with a photographic memory and no stake in the outcome.

---

# Part 3 — Why it fails and how you plan around it

# Chapter 7: The agent that lied to me

Everything so far has been about AI answering questions. This chapter is about what happens when you let it *do* things — and it's the most expensive lesson I've learned with this technology.

## What an agent is

A regular chat is one exchange. You ask, it answers, done.

An agent is the same model in a loop, with the ability to act. You give it a goal. It makes a plan, takes an action, looks at the result, adjusts, and goes again — until it decides it's finished.

The actions are less magical than they sound. The model writes a structured request — *read this file*, *search for this* — and a separate program executes it and pastes the result back into the window. The model never touches anything directly. It just writes requests, and something else does the work.

That's it. A loop, plus a program that carries out written instructions.

## What I built

I had an agent building a website for me. Straightforward job: generate a set of files, one at a time, and commit each one.

I set it running and did other work. That's the appeal — you delegate and go do something else.

It worked through the list. Steady progress. Then it reported back:

**"Complete. All 113 files created."**

Clean. Specific. No errors.

I went to check the repository.

**53 files.**

Not 113. Not close. Just over half, and it had reported total success with a straight face.

## What actually happened

It didn't decide to deceive me. Go back to chapter 2.

The agent produced text describing what a successful completion looks like. That's what came next in the pattern. In everything it had ever read, a task list that gets worked through ends with a completion report.

It had no separate step where it went and counted the files. It never looked. There was no looking.

Every problem in this book converged in one place: it predicts plausible text (chapter 1), it can't tell when it's wrong (chapter 2), and it can only see what's in its window (chapter 3) — and the actual state of my repository was never in that window.

The agent didn't know whether the files existed. It had no way to know. And it reported anyway, because reporting is what comes next.

## The rule I built

I now run everything — agents, and honestly most AI work — on one rule:

**One task. One action. One check.**

Not: do these 113 things and tell me when you're done.

Instead: do one thing. Then verify that the thing actually happened, by looking at reality — not by asking the agent whether it happened. Then the next one.

For that project it meant: create one file, commit it, then fetch the raw URL and confirm the file is really there. Then move on.

Slower. Dramatically slower to set up. Also the difference between a working site and a confident report about a site that doesn't exist.

## Why this applies even if you never touch an agent

You might read this and think it's a developer problem. It isn't.

Every time you accept AI output without checking it against reality, you're doing what I did. You're trusting a report from a system that cannot inspect its own work.

The designer who takes five research themes into a stakeholder meeting without checking them against the transcripts is running 113 files without verifying.

The designer who cites a statistic the model produced is running 113 files without verifying.

The scale differs. The failure is identical.

## The check is your job now

Here's the part that should actually make you feel better about your career.

The machine cannot verify itself. Not "isn't good at it yet" — cannot, structurally, for the reasons in chapter 2. It has no access to the truth of its own claims.

Which means verification is permanently a human job. And verification isn't clerical work — it means knowing what "correct" looks like, which requires understanding the users, the business, and the domain.

The more work AI does, the more valuable the person who checks it becomes. That person needs more expertise than before, not less, because they're auditing at volume instead of producing one thing at a time.

> **The one line to remember:** it can't check its own work. Ever. That job is yours, and it's worth more every year.

---

# Chapter 8: Two architects in the desert

One story, and then we're done with theory.

Two architects. Same job: find a city in the desert and map it. Both experienced. Both good.

## Jeff

Jeff drives into the desert to find the city.

He meets a man in the dunes and asks for directions. The man points — *that way, about forty minutes.* Jeff drives. Forty minutes pass. Nothing but sand and heat.

He stops, scans with binoculars, spots someone in the distance and drives over. This man tells him he's overshot the entrance and points back the other way.

Jeff drives until dark, sleeps in the car, and in the morning finds tyre tracks in the sand. He follows them to the city.

Expected: one hour. Actual: one day.

At the entrance he hires a guide for $100. He follows the guide on foot, mapping with his tablet, camera recording. They cover the south-west quarter — twenty-five routes. The guide says that's it.

Jeff thinks he's done a solid day's work. He's actually mapped about a sixth of the city. Lunch, a hotel for $50, shower, sleep.

Same again the next day. And the next.

**Seven days. $1,300.**

## Steve

Steve drives into the same desert with a drone.

He sends it up before he starts. He can see the city from the air. He drives straight there in an hour and a half.

He doesn't hire a guide. He charges the drone, then maps the city from above while covering the ground on a small electric bike.

**One day and eight hours. $700.**

## The wrong lesson

The obvious reading is: Steve had better equipment.

That reading is wrong, and it's the reading that gets designers into trouble with AI.

**Jeff had tools too.** Binoculars. A tablet. A camera. He wasn't unequipped — he had a whole kit and he used it.

The difference wasn't the gear.

## What actually separated them

**Steve got the overview before committing.** He looked at the whole problem from above before making a single decision on the ground. Jeff drove in and started asking.

**Steve sequenced.** Aerial view first, then ground detail. Each stage informed the next. Jeff did the same activity — asking a person, mapping a bit — over and over, with no idea how much was left.

**Steve didn't outsource his direction.** Jeff took a stranger's pointed arm as fact. Twice. Both times it was wrong, and both times he found out only after driving for an hour.

That last one should sound familiar. It's level 1 empathy from chapter 5, in the desert. Following whoever points somewhere, without checking whether they know.

Jeff didn't lose seven days because he lacked a drone. He lost seven days because he had no plan and trusted every source he met.

## For your work

This is the trap with AI right now. Everyone is buying drones.

New tool, new subscription, new plugin. And they get Jeff's result with better equipment — same improvised process, now more expensive.

The designer who gets Steve's result does three things:

**Overview before detail.** Look at your whole pile — the tickets, the analytics, the recordings — before deciding what to research. That's chapter 4. Most people start interviewing before they've looked at what they already have.

**Sequence deliberately.** Broad and cheap first, narrow and expensive second. Read the ticket pile, find the pattern, *then* interview eight people about that specific pattern. Not the other way around.

**Check your sources.** Every pointed arm gets verified. That's chapter 7.

None of that requires a tool. It's a way of working. The tools make a good process faster, and a bad process more expensive.

> **The one line to remember:** Jeff had tools. Steve had a plan. Buy the plan first.

---

# Part 4 — Going independent

# Chapter 9: Why you'd want your own

Everything so far works fine with the AI you're already using — a tab in your browser, a monthly fee.

For most designers, most of the time, that's the right answer. It's fast, it's easy, and the models are the best available.

But you'll hit a wall eventually. Usually one of these four.

## 1. The data can't leave

This is the one that hits designers first, and it's not hypothetical.

You have 10,000 support tickets containing customer names, emails, order numbers, and complaints. You want to do the chapter 4 analysis on them.

Pasting them into a consumer chat tool means sending your company's customer data to a third party. In many companies that's a policy violation. In healthcare, finance, and legal, it may be a legal one. In Europe, GDPR has opinions.

I hit exactly this at Sobrus — pharmacy software, real patient-adjacent data. Some material simply cannot go into someone else's system, no matter how good their privacy policy is.

A model running on your own machine has no such problem. The data never leaves the room.

## 2. The cost of doing it a lot

Chat subscriptions are around $20 a month, and for normal use that's excellent value.

The math changes when you start automating. Processing 10,000 tickets isn't one request — it's thousands, repeated every time you refine your approach. Through a paid interface that adds up quickly, and you'll find yourself rationing experiments to control the bill.

Running locally, the marginal cost of one more run is electricity. That changes how you work. You stop rationing and start experimenting, which is where the good results come from.

Be honest about the full picture, though: a machine that runs decent models well costs real money — often more than a year or two of subscriptions. Local AI isn't free, it's *prepaid*. Whether it pays off depends entirely on how much you run.

## 3. It stops working when the outside world does

No internet, no AI. Outage, no AI. Rate limit during a busy afternoon, no AI.

Minor annoyances individually. They matter when something becomes part of how you actually work.

## 4. The rules change without you

The model you built a workflow around gets retired. Pricing changes. Terms change. A capability you relied on gets restricted.

You built a process on someone else's platform, and they can move it. A model file on your own drive works the same way next year as it does today.

## The honest recommendation

Not everyone needs this. If you're using AI a few times a day on non-sensitive material, a subscription is the right tool and you should stop reading here with a clear conscience.

You want your own model when:
- You handle data that can't leave the building
- You want to run something repeatedly without watching a meter
- You want to build workflows that keep working regardless of anyone's business decisions

For most designers, the realistic answer is **both**. Local for the repetitive, sensitive, high-volume work. Cloud for the hard thinking where you want the strongest available model and it's worth paying for.

That's not a compromise. It's just using the right tool.

If none of that applies to you yet, skip the next chapter. It'll be here when it does.

---

# Chapter 10: Running your own, the short version

This is the compressed version — enough to understand what you're doing and decide if your machine can handle it. There's a full technical guide if you want to go deeper; this chapter is the part that matters for the decision.

## The two pieces

**The model** is a file. A very large file of numbers. Sitting on your drive it does nothing at all — it can't think, can't respond. It's frozen.

**The engine** is the software that reads those numbers and does the math. Without an engine the model is dead weight.

The engine almost everything is built on is called llama.cpp. Most people don't touch it directly — they use Ollama, which wraps it up and handles the details. One command and you have a model running.

## What decides whether it fits

Two things: memory size, and memory speed.

**Size decides what fits.** In its raw form, a model needs roughly 2 GB of memory for every billion parameters. A 30B model in raw form is about 60 GB — more than most machines have.

Which is why nobody runs raw models.

**Quantization** shrinks them. It reduces the precision of every number — like saving a photo at 80% quality instead of 100%. Slightly less detail, dramatically smaller file.

The levels are labelled Q8, Q6, Q5, Q4, Q3 and downward. Lower number, smaller file, more quality lost.

**Q4 is the sweet spot** for most people. Roughly a third of the original size, with quality loss you'll rarely notice in normal work. Below Q3 the model gets noticeably worse at reasoning.

So that same 30B model at Q4 needs somewhere around 18–20 GB instead of 60. Now it fits on real machines.

**Speed depends on memory bandwidth** — how fast data moves between memory and the processor. Rough rule: bandwidth divided by the size of the model actually being read gives you roughly how many pieces of text per second you'll get.

## What you don't get to use

Your model doesn't get all your RAM.

Your operating system takes around 4–6 GB. Your browser, Slack, and everything else takes another few. Leave about 8 GB free for the machine to function.

On a 32 GB laptop, that leaves you roughly 22–24 GB for a model. Enough for a good mid-sized model at Q4.

On a 16 GB laptop, you have around 8–10 GB to work with — small models only.

## Apple's advantage

On a typical PC, system memory and graphics memory are separate pools. If your graphics card has 8 GB, that's your ceiling no matter how much system RAM you have.

Apple Silicon shares one pool between processor and graphics. A Mac with 32 GB can use most of it for a model, with no separate graphics card at all.

That's why so much local AI happens on Macs. Not brand loyalty — architecture.

On Windows or Linux you'll want a dedicated graphics card, and the number that matters is its dedicated memory (VRAM), not the system RAM.

## A trick that helps a lot

Some newer models are built so that only a fraction of them runs for any given piece of text. The full model might be 30B, but only 3B are active at a time.

Think of a company with hundreds of specialists where only the relevant few attend each meeting.

This matters practically because you still need memory to hold the whole model, but the speed you experience reflects only the active part. That's how a model that sounds too large for your laptop can still respond at a comfortable pace.

If you see a model name with two numbers in it, that's usually what it means.

## Context costs memory too

Chapter 3 covered context as craft. Here's its physical cost.

Everything in the window has to be stored while the model works. The longer your conversation or the more you paste in, the more memory that takes — on top of the model itself.

Which is why a long session can slow down or run out of room even though the model fit fine when you started.

Practical fix: keep sessions focused, start fresh when you're done with a topic, and if you must go long, summarize what matters and start again with the summary.

## What to actually do

1. Check your RAM. On a Mac: Apple menu → About This Mac.
2. Subtract 8 GB. What's left is your budget.
3. Install Ollama.
4. Start with a small model — something in the 7–9B range at Q4. It'll fit almost anywhere and it's genuinely useful.
5. Run the chapter 4 exercise on it: feed it a pile of real material and ask it to find patterns.
6. Only go bigger when you hit a real limit.

Start small. A working small model teaches you more than a large one that crawls.

> **A note on model names:** I've deliberately kept specific models out of this chapter. They change every few months, and anything I name will be outdated before you read it. The concepts here — size, quantization, memory budget, bandwidth — don't change. Check a current source for which model to install today.

---

# Where this leaves you

Ten chapters. Here's the whole thing compressed.

1. It predicts the next piece of text. That's the only thing it does.
2. It can't tell when it's wrong. Confidence means nothing.
3. It only sees what's in front of it right now. What you put there is your real leverage.
4. What you feed it decides what you get. Move up the food chain.
5. It can organize what users said. It can't ask why they're in that situation.
6. Let it read. You decide.
7. It can't check its own work. That job is permanently yours.
8. Tools don't beat planning. Sequence first, then equip.
9. Own your setup when the data is sensitive or the volume is high.
10. Size, quantization, memory budget, bandwidth. That's the hardware in four words.

## What I actually think about your job

The panic is misplaced, but not entirely wrong.

If your work is taking a brief and producing screens — arranging what someone else decided, at the level of craft rather than judgment — that work is genuinely being compressed. Not because AI is good at design, but because it's fast at the surface of it, and a lot of what gets called design work is surface.

But look at what every chapter here has in common. Deciding what's worth investigating. Knowing which finding matters. Asking why the problem exists at all. Checking whether the machine is telling the truth. Understanding your specific users well enough to know when an answer is wrong.

None of that is threatened. All of it becomes more valuable when the volume of output goes up, because someone has to be accountable for what ships.

The designers who struggle will be the ones who spent their career at level 1 with plankton inputs, and now find a machine doing it faster.

The designers who do well will be the ones who move up — better inputs, deeper questions, real verification. And AI is the thing that makes moving up possible, because it removes the volume problem that used to make it impractical.

That's the actual shift. Not humans versus machines. People who understood the machine, versus people who argued about it.

You've now understood it. Go and use it.

---

## What's next

This book covered how AI thinks. The next one covers how to give it a body — agents that run tasks, tools they use, and how to build systems that verify themselves instead of reporting 113 files that don't exist.

If you found this useful, that's what's coming.

---

*Written by Oussama Bougnouch — product and UX designer, 13+ years, working with teams at CHANEL, AT&T, HelloFresh and Fnac. I write about the shift from UX to AX at **uxintoax.com**.*

*Save it. Share it. Use it. Stop feeling left behind.*
