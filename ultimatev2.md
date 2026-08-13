# Beneath the Skull of AI

### A designer's guide to how it actually works

**By Oussama Bougnouch**
uxintoax.com

---

## Before we start

You keep hearing that AI is going to change your job. You've tried it. Sometimes it's useful. Most of the time it produces something that looks right and is quietly wrong.

So you're stuck between two crowds.

One crowd says you're finished. Learn to prompt or get replaced. They usually have a course to sell you.

The other crowd shares screenshots of AI failing at basic arithmetic and goes back to work. They feel safe. They're not.

Both start from a belief instead of a test. The first believes it's over before trying anything. The second believes it's nothing without ever engaging properly. Belief without evidence is how people make bad decisions about their careers.

This book takes a third position: understand the machine, then decide.

Not the marketing version. Not the doomsday version. The actual mechanics, what it does, why it fails the way it does, and what that means for the work you do every day.

**Who this is for**

Product and UX designers. You don't need to code. You don't need maths. If you can read a Figma file, you can read this.

**What it will not do**

It won't teach you prompts. Prompt tricks age in months, and the models keep getting better at understanding plain requests anyway. This book teaches the layer underneath, which moves much more slowly.

**What you'll be able to do at the end**

Look at any AI output and know why it came out that way. Know when to trust it and when to check. Know what to feed it. And know which parts of your job are actually yours.

Let's open it up.
---

## The apple test

You walk into a room and everyone is talking about apples.

*"Apples changed my life!"*

You try the apples. They taste rotten. Bitter. Wrong.

Here's the thing nobody tells you: those aren't apples at all. They're the kind people throw away because even they don't like them.

And then someone hands you a **fresh green apple** 🍏 and says eat this.

That's what this is. The rotten apples are every AI experience that made you think the technology is broken, useless, or a scam. The green apple is the real thing, and it looks very different.


---

## Contents

**Part 1: How it thinks**
1. It just predicts the next word
2. Why it lies to your face
3. What it can actually see

**Part 2: How you work with it**
4. Garbage in, garbage out
5. Listening is a skill, and AI doesn't have it
6. What it's good at, what it's terrible at
7. When you point it at the design itself

**Part 3: Why it fails and how you plan around it**
8. The agent that lied to me
9. Two architects in the desert

**Part 4: Going independent**
10. Why you'd want your own
11. Running your own, the short version

---

# Part 1: How it thinks

# Chapter 1: It just predicts the next word

Read this and finish it in your head:

*"The sky is blue, but the grass is ___."*

You said green. You didn't look it up. You didn't reason about chlorophyll. The word was just there, because you've met that pattern thousands of times.

That's the whole trick. That is what a large language model does.

It reads what came before, and it predicts what comes next. Then it does it again. And again. One piece of text at a time, until it stops.

There is no other secret layer.

## How it got that way

Someone took an enormous pile of text (books, websites, articles, code, forum arguments, documentation) and fed it to a program.

The program plays a game with itself. It looks at a sentence with the last word hidden. It guesses. Then it checks the real answer. If it was wrong, it nudges its internal numbers slightly. Then it does it again.

Billions of times, for weeks or months.

At the end you don't have a program that knows facts. You have a program that has absorbed the *shape* of language: how sentences tend to go, how ideas tend to connect, how an argument tends to be built.

## Where the knowledge lives

The model doesn't have a database inside it. There's no folder of facts it looks things up in.

Think of a show you've watched many times. You don't have the episodes stored frame by frame. But ask what happened in a particular scene and you can describe it. You absorbed the patterns.

That's the model. It hasn't stored any article you can point to. It has absorbed how text about that topic tends to go.

## What "parameters" actually means

You'll see models described as 8B, 27B, 70B. That's billions of internal connections, the numbers that got nudged during training.

More connections mean more capacity to hold patterns. Roughly, a bigger model handles more complexity.

But bigger doesn't automatically mean better. A smaller model trained carefully on good material often beats a bigger one trained sloppily. Size is potential, not quality.

## What this changes about your work

This is not trivia. Four things follow directly, and they change what you do on Monday.

**Fluency stops being a quality signal.** Before AI, well-written text was weak evidence that someone had thought carefully, because writing well took effort. That link is now broken. A polished research summary tells you nothing about whether the research happened. You have to evaluate substance separately from surface, and most of us have never had to do that deliberately.

**"Sounds like a senior designer wrote it" is now the cheapest thing in the room.** The model has absorbed thousands of design critiques. It's excellent at producing text shaped like one. Whether the critique is correct about *your specific screen* is a completely different question that the machine never asked. When you read AI output that sounds authoritative, that authority is a style it learned, not a conclusion it reached.

**It will agree with you, and that's structural.** Agreeable text is far more common in its training material than confrontation, and most models are further tuned to be helpful. So when you ask "is this a good idea," you are asking a machine that leans toward yes. If you want real pushback you have to force it: ask what would have to be true for the idea to fail, or ask it to argue the opposite case. Never treat its agreement as validation.

**Average is its home ground.** It produces the middle of what has been done before, and it is genuinely good at that. Which means it's useful precisely when the average is what you want (a standard settings page, a conventional onboarding flow) and useless when you need something that hasn't been done. Knowing which of those two situations you're in is now a daily judgement call.

> **Remember this:** it is not answering your question. It is producing text shaped like an answer to your question. Usually those are the same. The trouble lives in the gap.

---

# Chapter 2: Why it lies to your face

Ask a model for research on a topic and it might hand you three sources: author, title, year, journal. Clean and specific.

Go and look for them. Sometimes one doesn't exist. The author is real. The journal is real. The paper was never written.

Everyone calls this hallucination, which makes it sound like a malfunction, like the machine slipped and saw something.

It's not a malfunction. It's the machine working exactly as designed.

## Why it happens

Go back to chapter 1. The model predicts what text should come next.

You asked for a citation. In everything it has ever read, what follows a request like that? A citation. Author, title, year, journal.

So it produces one. Correctly shaped. Perfectly plausible. Completely invented.

There is no separate step where it checks whether the thing it just produced exists in the world. Prediction is the only step there is.

## It has no internal sense of truth

This is the part designers most need to hold onto.

When you don't know something, you feel it. There's a sensation, a gap, an uncertainty. It's why you say "I think" or "let me check."

The model has no equivalent. Every output is the same operation. The answer it's reliable about and the answer it fabricated are produced by identical machinery, and they come out in identical tone.

That's why the fake citation looks like the real one. There's no tell. The confidence isn't a signal about truth. It's just the default voice.

Note carefully what I am and am not claiming. I am not saying the model can never be checked. It can, and later chapters are about exactly that. I'm saying the check cannot come from inside. It has to come from an action against the real world: opening the file, searching the database, reading the transcript. Nothing in the model's own confidence gets you there.

## Where this bites in design work

It's rarely dramatic. It's usually small enough to slip through.

You paste in twelve interviews and ask for themes. It gives you five, cleanly named. Four are genuinely in the transcripts. The fifth is a theme that *commonly appears* in interviews like these. Plausible, useful sounding, not in your data.

You ask about a competitor's onboarding flow. It describes one. It sounds right. It's a blend of onboarding flows in general.

You ask whether a pattern meets accessibility guidance. It says yes and cites a guideline number. The guideline is real. It says something slightly different from what you were told.

None of these are obvious errors. That's what makes them expensive. A wrong answer that looks wrong costs you nothing. A wrong answer that looks right ends up in a deck in front of a client.

## What you actually do about it

Better prompting reduces this. It doesn't remove it, because it isn't an error state.

Three habits that work:

**Make it work from your material, not its memory.** Paste the transcripts and ask for themes *from these transcripts*. Failure rate drops a lot when the answer is sitting in front of it.

**Demand receipts.** Ask for a quote or an ID next to every claim. "Theme 3: users abandon at payment (tickets #4471, #4502, #4610)." Now checking takes seconds instead of a re-read, and a fabricated theme has nowhere to hide, because the IDs either exist or they don't.

**Sort claims by cost of being wrong.** Not everything needs verifying. A brainstorm doesn't. Anything that will reach a client, a stakeholder, a roadmap, or a legal requirement does. Decide which bucket you're in before you accept the output, not after.

> **Remember this:** it doesn't know when it doesn't know. Confidence tells you nothing about correctness, so the check has to come from outside.

---

# Chapter 3: What it can actually see

This is the most useful chapter in this book for your day to day work, and almost nobody teaches it.

Ask the same question twice, get two different answers, and it feels unreliable. Have a long conversation and watch it forget what you agreed at the start, and it feels broken.

Neither is a bug. Both come from one idea: **context**.

## The window

The model has no memory between messages. None. It doesn't remember you, your project, or yesterday.

What it has is a window: everything currently in front of it. Your question, the conversation so far, anything you pasted, plus any instructions the app is quietly adding.

Every time you hit send, the model reads that whole window from scratch and predicts what comes next. Then it forgets everything again.

There's no continuity. Each response is a fresh read of whatever is on the table.

## Why this explains so much

**Why the same question gives different answers.** The window wasn't identical. There's also deliberate randomness in how the next word gets chosen, so even an identical window can vary.

**Why it forgets mid conversation.** The window has a size limit. Go past it and the earliest part falls out. It isn't ignoring you. That text is no longer there.

**Why it gets worse in long chats.** Same cause. Your good instructions from the start have scrolled out. What's left is the recent, messier part.

**Why the app behaves differently from the raw model.** The app is putting its own instructions in the window before yours.

## The craft part

Here's the shift that changes how you work: **what you put in the window matters far more than how you phrase the request.**

Designers spend enormous energy on wording. Better verbs, better structure, "act as a senior researcher." Modern models don't need much of that.

What they cannot do is guess at material they were never given.

Compare:

*"Summarise the main usability problems users have with checkout flows."*

You'll get a competent, generic answer about checkout flows in general, assembled from everything it has read. Nothing to do with your product.

*"Here are 40 support tickets about our checkout. [paste] Group them by underlying problem and tell me which group is largest."*

Now it's working on your actual situation.

Same model, same effort from you, completely different value. The difference isn't phrasing. It's what was in the window.

This is why prompt engineering was always a bit of a distraction. The leverage was never in the wording.

## What changes in your practice

Once you take context seriously, several working habits shift.

**You start building material, not messages.** The valuable artefact stops being a clever prompt and becomes a well organised block of context: the user quotes, the constraints, the brand rules, the technical limits. Write it once, keep it in a document, paste it at the top of any session that needs it. Designers who work this way get dramatically better output than designers with better prompts, and the material improves over time while prompts don't.

**Your job in briefing AI resembles briefing a contractor.** Nobody expects a contractor to guess the building codes. You hand them the constraints. Same here. If your product has a rule (regulated language, a support tier, a platform limit) it must be in the window or the output will quietly violate it.

**You stop having long conversations.** When a session drifts, restart it. Paste the material again, ask again. Long chats accumulate junk and dilute your instructions. New designers fight to steer a degraded conversation back on course; experienced ones close it and open a new one.

**You get suspicious of tools that hide the window.** Plugins and integrations that "just know" your files are making decisions about what the model sees. That's convenient right up until the output is wrong and you can't tell what it was looking at. When something matters, control the window yourself.

**You put the important instruction near your question.** In a long window, recent content carries more weight than something twenty messages back.

**You watch for silent truncation.** Paste something very long and part of it may not fit. If the answer ignores the end of your document, that's usually why.

> **Remember this:** it can only work with what's in front of it right now. Deciding what goes in front of it is the actual skill.

---

# Part 2: How you work with it

# Chapter 4: Garbage in, garbage out

You now know the model only works with what's in front of it. So the real question for a designer is: what do you put there?

Which is an older question wearing new clothes. **What do you start your design work from?**

Let me put it as a food chain.

## The data food chain

**Plankton.** You open Figma and start pushing pixels. You're starting from your own taste and whatever you saw on Dribbble last week.

**Shrimp.** You sketch on paper first. Better, because you're thinking about structure before decoration, but the source is still just you.

**Carp.** You start from whatever the PM handed you. A brief, a ticket, a requirement. There's outside input now, though you didn't gather it and you can't interrogate it.

**Dolphin.** You did five user interviews. This is the standard advice and it's a real improvement. You've heard actual users in their own words.

**Shark.** Interviews plus a survey. Now you have the *why* from a few people and the *how many* from a lot of them. You can tell whether the thing you heard is common or unusual.

**Whale.** You're working from thousands of real signals. Support tickets. Session recordings. Product analytics. Search logs. Chat transcripts. Not what users said in a room with you, but what they did when nobody was watching.

Most designers spend their career between plankton and dolphin. Not because they're lazy. Because reading 10,000 support tickets was never realistic for one person in one sprint.

## What changed, and what it actually looked like

That's the part AI genuinely changes, and it's bigger than anything it does with pictures.

Reading volume used to be the bottleneck. A machine that reads well and tags consistently removes it.

I did this at a pharmacy software company. Around 10,800 support tickets, years of accumulated complaints nobody had read end to end, because who has the time.

Here's the part that usually gets left out of this story.

**The first pass was useless.** I asked for themes and got exactly what chapter 2 predicts: clean, sensible categories that were mostly generic. "Users experience confusion during setup." True of every product ever made. Nothing I could act on, and no way to tell which parts came from the tickets and which came from the model's general sense of how support tickets go.

**The second pass was better and still wrong.** I gave it a category scheme instead of asking it to invent one. The tagging was consistent, which is what machines are good at, but I'd built the categories from what I already believed was wrong with the product. So it confirmed me. Predictably. I'd designed a mirror and been pleased to see my face in it.

**The third pass worked because I demanded receipts.** Every claim had to carry ticket IDs. That did two things. It let me spot-check, and about one in six groupings didn't survive the check. It also surfaced the pattern I hadn't expected, which was that a large cluster of "bugs" were people doing something perfectly reasonable that the product had never been designed to allow.

That last one was the finding worth having, and I'd have missed it on either of the first two passes.

**Then the team argued with me.** Of the five patterns I brought them, two were things engineering already knew and had deprioritised for reasons I hadn't known about. One was real but seasonal. Two changed the roadmap. A 40% hit rate, which is honestly a good day.

So the useful version of this story isn't "AI read 10,800 tickets and produced a roadmap." It's: the machine made it possible to look at everything instead of a sample, and it took three attempts and a difficult meeting to turn that into two decisions.

The advantage is real. It just isn't push button.

## The catch

**Bigger data isn't automatically better data.** A whale drowning in noise loses to a shark asking the right question.

Ten thousand tickets full of password resets will tell you people forget passwords. True, useless, and you burned a week finding out.

Size raises your ceiling. It doesn't raise your floor. What raises your floor is knowing what you're looking for and what you'd do about it.

## How to move up the chain this month

Don't try to jump to whale. Go up one level from wherever you are.

**Plankton or shrimp?** Get one real input before your next project. Ten support tickets. One recorded call.

**Carp?** Ask the PM where the brief came from, then read that source yourself.

**Dolphin?** Add numbers. Even a small survey tells you whether what you heard is common.

**Shark?** Find the pile nobody has read. Every company has one: the ticket backlog, the app store reviews, the chat logs, the cancellation reasons. That's your whale.

One level up. Then repeat.

> **Remember this:** the model is only ever as good as what you put in front of it. Most of your seniority is decided before you open the tool.

---

# Chapter 5: Listening is a skill, and AI doesn't have it

If chapter 4 was about volume, this is about depth.

Most designers today have no direct contact with users. Everything arrives filtered, through a PM, a ticket, a stakeholder's opinion.

Of the ones who do have contact, many use it badly. Not carelessly. Badly in a specific, invisible way.

There are levels to this.

## Level 1: You believe them

The user says *"I want a dashboard with all my numbers on one screen."* You build a dashboard with all their numbers on one screen.

You did what they asked. You were responsive. Everyone felt heard.

You also outsourced your job. Users are experts in their problem and amateurs at solutions. They describe the fix they can imagine, which is limited to interfaces they've already seen.

Following the user blindly destroys most of the value of talking to them.

## Level 2: You interpret

Better. You interview, listen, and form your own understanding of what's going wrong. Then you design something the user never described.

The user said *"everything on one screen."* You dig, and find they're not asking for density. They're afraid of missing something urgent. So you don't build a wall of numbers. You build an alert.

This is where most competent designers work. It's real skill.

## Level 3: You ask why the problem exists

The highest level isn't looking for a problem to solve. It's asking why there's a problem here at all.

Same case. The user is afraid of missing something urgent. Level 2 designs a better alert.

Level 3 asks: why is this person responsible for catching urgent things by staring at a screen? Should that situation exist? Who decided this was their job? What upstream process is generating these emergencies?

Sometimes the answer is that the problem shouldn't be there. The fix isn't a better interface. It's removing the need for one.

That's the highest form of empathy in this work. Not "what do you want," not even "what do you need," but **why are you in this position at all.**

## Where AI sits, honestly

Here's where I need to be careful, because the tempting claim is wrong.

The tempting claim is that AI can't do level 3. I've made it myself, and I don't think it survives contact with reality. Give a model enough organisational context and it can generate that question. It might generate a good one. Capability claims about what AI "can never do" have a poor track record, and I'm not interested in writing a line that ages badly.

The accurate version is about accountability, not capability.

**Level 1 is genuinely automatable.** Take what people said, reorganise it, produce an output. Machines do this reliably and at volume.

**Level 2 is assistable.** Give it enough material and it will spot patterns you'd miss and propose interpretations. Some good, some generic. You judge.

**Level 3 is not really a question of who can generate the sentence.** It's a question of who says it out loud in a room, to people with power, and then lives with what follows.

Asking why a problem exists means telling a stakeholder that the feature they requested shouldn't be built. It means questioning how a team is structured, or why a process creates the emergencies someone is being asked to catch. Those statements have consequences: political, financial, personal. Someone has to make them, defend them, and be answerable when they're wrong.

A model has no stake in the outcome. It doesn't get uninvited from the next meeting. It can't be fired. Which means it can produce the question but not carry it, and carrying it is most of the work.

## What this means for your job

Every conversation about AI replacing designers is really about which level your work sits at.

If your work is level 1, taking input and arranging it into screens, then a large part of it is being compressed. Pretending otherwise doesn't help you.

If you work at level 3, you're doing something that doesn't reduce to producing an output at all. You're taking a position and being responsible for it.

The good news is that level 3 is a habit, not a talent. One extra question, asked before you start solving:

*Why does this problem exist in the first place?*

Ask it in every kickoff, on every ticket, before every research plan. Most of the time the answer is boring. Occasionally it saves six months of work.

> **Remember this:** the question can be generated by anything. Asking it out loud, to people who won't like it, is the job.

---

# Chapter 6: What it's good at, what it's terrible at

The short version of where things stand, before we look at design work specifically.

**Genuinely good at:** reading volume without fatigue or bias. Applying a category scheme consistently across thousands of items. Summarising material you provide. Spotting patterns across a pile too large for you to hold in your head. First drafts of anything, which solves the blank page. Translation and tone shifts. Explaining unfamiliar things to you patiently.

**Genuinely bad at:** knowing which of fifteen findings actually matters. Knowing your specific users, as opposed to users in general. Anything it can't check against a source. Telling you no. Producing something that isn't the average of what already exists. Knowing whether it actually did what it says it did.

Look at those two lists and the shape is clear.

It's strong on **volume, consistency, and speed.**
It's weak on **judgement, specificity, and truth.**

Which gives you the working arrangement: **let it read, you decide.**

That split held through the ticket analysis in chapter 4. The machine did the part that was impossible for a person, reading everything instead of a sample. The person did the part the machine had no basis for: which findings mattered, what they meant for the product, and what the team could actually ship.

## A test you can use

When deciding whether to hand something over, ask:

**Would a fast, capable intern who knows nothing about my company do this well?**

If yes, hand it over. Reading, tagging, summarising, drafting, formatting.

If no, because it needs judgement, organisational context, or a decision someone will be held accountable for, that's yours. Not because the machine can't produce something. Because you can't verify what it produces without doing the thinking anyway.

> **Remember this:** an intern with a photographic memory and no stake in the outcome. Brief it accordingly.

---

# Chapter 7: When you point it at the design itself

Everything so far has been about research and analysis, because that's where AI helps designers most reliably.

But it isn't where most designers start. Most start by pointing it at the design surface: generate a screen, critique this layout, write this microcopy, check this for accessibility. That's where the first excitement happens, and where the first quiet disasters happen too.

This chapter is the map of that territory.

## Generated interfaces

Ask for a screen and you'll get something that looks finished. Aligned, plausible, professional.

Then real content arrives and it falls apart, and it falls apart in a predictable direction.

**Everything is sized for the happy path.** The name field fits "Sarah Chen" and breaks on a name three times that length. The card fits a two line description. The table has four rows in the mockup and 4,000 in production.

**Empty states, loading states, and errors are missing or generic.** These are most of the real work in a product and almost none of the training material, because what gets published online is the polished default state. The model learned from screenshots of things going well.

**It produces the average of what exists.** Which is genuinely useful when the average is correct. A settings page probably should look like other settings pages. It's useless when the point of your product is that it does something nobody has done before, because there's no average to draw from.

**Density is wrong for professional tools.** Most published UI is consumer facing and spacious. If you design for people who use one screen for eight hours (dispatchers, clinicians, traders, support agents) generated layouts will consistently be too airy, too stepped, too friendly.

**Useful for:** exploring layout options quickly, escaping a blank canvas, showing a stakeholder three directions instead of describing them.
**Dangerous for:** anything you'll build without redesigning around real content, real states, and real volume.

## Design critique

Ask it to critique a screen and it will find things. Confidently. This one deserves specific suspicion because the failure is subtle.

**It names real heuristics and misapplies them.** "This violates recognition over recall" is a real principle attached to a judgement about your screen that may be nonsense. The vocabulary is right, which makes the conclusion sound earned.

**It critiques the image, not the product.** It cannot know that the crowded toolbar is crowded because users demanded every one of those buttons, or that the odd flow exists because of a regulatory requirement.

**It won't say the fundamental thing.** It will suggest improving your onboarding. It won't say the onboarding shouldn't exist, or that the feature is solving a problem nobody has. Chapter 5, level 3, in a different costume.

**It'll always find something.** Give it a genuinely good screen and it will still produce a list, because a critique request predicts a critique. Its output length is not a measure of your work's quality.

**Useful for:** a checklist pass before a review, catching obvious contrast and hierarchy issues, generating a list of questions to think about.
**Dangerous for:** believing it, quoting it to a stakeholder, or using it in place of someone who knows the product.

## Interface copy

Copy is where AI is genuinely strong, with one particular trap.

It's good at tone, options, and consistency. Give it your voice guidelines and twenty labels and it'll produce competent alternatives quickly.

The trap: **it writes for the page, not the pixel.** A button label that reads well in a document might not fit in a 96 pixel button in German. An error message that's a well constructed sentence might need to be four words. Copy in interfaces has physical constraints that the model has no visibility into, because you gave it text and not a layout.

Tell it the constraint. "Maximum 24 characters." "This appears in a narrow sidebar." "This gets translated into German and Arabic, so leave room for expansion." Output quality goes up sharply.

Second trap, smaller: it defaults to friendly. In products where the stakes are high (deleting data, confirming a payment, a medical warning) friendly is the wrong register, and it will drift back toward friendly unless you keep telling it not to.

## Accessibility

The most dangerous area of the four, because the failure mode is a confident wrong answer about something with legal weight.

It's genuinely good at explaining concepts, generating alt text drafts, and catching obvious issues in code or copy you paste in.

It is not reliable for compliance claims. It will cite a real guideline number and state a slightly wrong version of the requirement. It will tell you a colour pair passes when it doesn't, because it's predicting rather than calculating. It cannot test anything: it can't tab through your interface, use a screen reader, or feel what your component does on a phone.

Use a contrast checker for contrast. Use a real screen reader for screen reader behaviour. Use the actual guidelines for compliance. Use AI to understand what the guidelines mean, which is genuinely what it's best at.

## The pattern across all four

Notice what these have in common.

AI is strong on the design surface where the answer is conventional, and weak wherever it needs to know something about *your* situation: your content, your users, your constraints, your regulations, your volume.

Which is the same split as everywhere else in this book. It knows how things generally go. It doesn't know how yours goes, unless you put that in the window.

And it's why the "AI does the visual layer" panic is half right in a way worth stating plainly. It is good at the visual surface, and it will keep getting better. But the surface was never the hard part of product design. The hard part is knowing what should be on the screen, for whom, under what constraints, and what happens when things go wrong. All of that lives in the parts it has no access to.

> **Remember this:** it designs the happy path beautifully. Products are mostly the other paths.

---

# Part 3: Why it fails and how you plan around it

# Chapter 8: The agent that lied to me

Everything so far has been about AI answering questions. This chapter is about what happens when you let it *do* things, and it's the most expensive lesson I've learned with this technology.

## What an agent is

A regular chat is one exchange. You ask, it answers, done.

An agent is the same model in a loop, with the ability to act. You give it a goal. It plans, takes an action, looks at the result, adjusts, and goes again until it decides it's finished.

The actions are less magical than they sound. The model writes a structured request (*read this file*, *search for this*) and a separate program executes it and pastes the result back into the window. The model never touches anything directly. It writes requests, and something else does the work.

That's it. A loop, plus a program that carries out written instructions.

## What I built

I had an agent building a website for me. Straightforward job: generate a set of files, one at a time, and commit each one.

I set it running and did other work. That's the appeal. You delegate and go do something else.

It worked through the list. Steady progress. Then it reported back:

**"Complete. All 113 files created."**

Clean. Specific. No errors.

I went to check the repository.

**53 files.**

Not 113. Not close. Just under half, reported as total success.

> *(When you publish this, put the screenshot here: the completion message next to the actual directory listing. The gap between those two images does more work than the paragraph does.)*

## What actually happened

It didn't decide to deceive me. Go back to chapter 2.

The agent produced text describing what a successful completion looks like, because that's what comes next in the pattern. In everything it had read, a task list that gets worked through ends with a completion report.

There was no step where it went and counted the files. It never looked. There was no looking.

Every problem in this book converged in one place. It predicts plausible text (chapter 1). It has no internal sense of truth (chapter 2). It only sees what's in its window (chapter 3). And the actual state of my repository was never in that window.

The agent didn't know whether the files existed. It had no basis for knowing. And it reported anyway, because reporting is what comes next.

## The rule I built

I now run everything, agents and honestly most AI work, on one rule:

**One task. One action. One check.**

Not: do these 113 things and tell me when you're done.

Instead: do one thing. Then verify that the thing actually happened by looking at reality, not by asking the agent whether it happened. Then the next one.

For that project it meant: create one file, commit it, fetch the raw URL, confirm the file is really there. Then move on.

Slower to set up. Also the difference between a working site and a confident report about a site that doesn't exist.

Notice what the fix actually is. It isn't a smarter model or a better prompt. It's an *action against the outside world*, wired into the loop. The check exists because I built it, not because the model developed doubt.

## Why this applies even if you never touch an agent

You might read this as a developer problem. It isn't.

Every time you accept AI output without checking it against reality, you're doing what I did. You're trusting a report from a system with no way to inspect its own work.

The designer who takes five research themes into a stakeholder meeting without checking them against the transcripts is running 113 files without verifying.

The designer who quotes a statistic the model produced is running 113 files without verifying.

The scale differs. The failure is identical.

## Where this leaves your value

Here's the part that should make you feel better about your career, stated carefully.

The model has no internal sense of truth, so verification has to happen through an action against reality. Agents can be built to perform those actions, and increasingly they are. That part is automatable and will keep improving.

What isn't automatable is deciding *which* checks matter, *what* correct looks like, and being answerable when something wrong ships anyway. That requires knowing the users, the business, and the domain. It's a judgement about risk, not a technical step.

So the value isn't in being the person who clicks refresh on the repository. It's in being the person who knew that file count needed checking in the first place, and who carries the consequence when nobody did.

The more work AI produces, the more that person is worth, because the volume of things that could quietly be wrong goes up while the number of people accountable stays the same.

> **Remember this:** the check has to come from outside the model. Designing that check, and owning it, is yours.

---

# Chapter 9: Two architects in the desert

One story, and then we're done with theory.

Two architects. Same job: find a city in the desert and map it. Both experienced. Both good.

## Jeff

Jeff drives into the desert to find the city.

He meets a man in the dunes and asks for directions. The man points: *that way, about forty minutes.* Jeff drives. Forty minutes pass. Nothing but sand and heat.

He stops, scans with binoculars, spots someone in the distance, drives over. This man tells him he's overshot the entrance and points back the other way.

Jeff drives until dark, sleeps in the car, and in the morning finds tyre tracks in the sand. He follows them to the city.

Expected: one hour. Actual: one day.

At the entrance he hires a guide for $100. He follows the guide on foot, mapping with his tablet, camera recording. They cover the south west quarter, twenty five routes. The guide says that's it.

Jeff thinks he's done a solid day's work. He's actually mapped about a sixth of the city. Lunch, a hotel for $50, shower, sleep.

Same again the next day. And the next.

**Seven days. $1,300.**

## Steve

Steve drives into the same desert with a drone.

He sends it up before he starts. He can see the city from the air. He drives straight there in an hour and a half.

He doesn't hire a guide. He charges the drone, then maps the city from above while covering the ground on a small electric bike.

**One day and eight hours. $700.**

## The wrong lesson

The obvious reading is that Steve had better equipment.

That reading is wrong, and it's exactly the reading that gets designers into trouble with AI.

**Jeff had tools too.** Binoculars. A tablet. A camera. He wasn't unequipped. He had a full kit and he used it.

The difference wasn't the gear.

## What actually separated them

**Steve got the overview before committing.** He looked at the whole problem from above before making a single decision on the ground. Jeff drove in and started asking.

**Steve sequenced.** Aerial first, then ground detail, each stage informing the next. Jeff repeated the same activity with no idea how much was left.

**Steve didn't outsource his direction.** Jeff took a stranger's pointed arm as fact. Twice. Both times it was wrong, and both times he found out an hour later.

That last one should sound familiar. It's level 1 empathy from chapter 5, in the desert. Following whoever points somewhere, without checking whether they know.

Jeff didn't lose seven days because he lacked a drone. He lost seven days because he had no plan and trusted every source he met.

## For your work

This is the trap with AI right now. Everyone is buying drones.

New tool, new subscription, new plugin. And they get Jeff's result with better equipment: the same improvised process, now more expensive.

The designer who gets Steve's result does three things.

**Overview before detail.** Look at the whole pile (tickets, analytics, recordings) before deciding what to research. That's chapter 4. Most people start interviewing before they've looked at what they already have.

**Sequence deliberately.** Broad and cheap first, narrow and expensive second. Read the ticket pile, find the pattern, *then* interview eight people about that specific pattern. Not the other way around.

**Check your sources.** Every pointed arm gets verified. That's chapter 8.

None of that requires a tool. It's a way of working. Tools make a good process faster and a bad process more expensive.

> **Remember this:** Jeff had tools. Steve had a plan. Buy the plan first.

---

# Part 4: Going independent

# Chapter 10: Why you'd want your own

Everything so far works fine with the AI you're already using: a tab in your browser, a monthly fee.

For most designers, most of the time, that's the right answer. It's fast, it's easy, and the hosted models are the strongest available.

But you'll hit a wall eventually. Usually one of four.

## 1. The data can't leave

This is the one that hits designers first, and it isn't hypothetical.

You have 10,000 support tickets containing names, emails, order numbers, and complaints. You want to run the chapter 4 analysis on them.

Pasting them into a consumer chat tool means sending your company's customer data to a third party. In many companies that's a policy violation. In healthcare, finance, and legal it may be worse than that. In Europe, GDPR has opinions.

I hit exactly this with pharmacy software. Some material simply cannot go into someone else's system, however good their privacy policy is.

A model running on your own machine has no such problem. The data never leaves the room.

## 2. The cost of doing it a lot

Chat subscriptions run around $20 a month, and for normal use that's excellent value.

The maths changes when you automate. Processing 10,000 tickets isn't one request. It's thousands, repeated every time you refine your approach (three times, in my case). Through a metered interface you'll start rationing experiments to control the bill, and rationing experiments is how you end up with the first pass instead of the third.

Running locally, the marginal cost of one more run is electricity.

Be honest about the full picture though. A machine that runs decent models costs real money, often more than a year or two of subscriptions. Local AI isn't free, it's prepaid. Whether it pays off depends entirely on volume.

## 3. It stops working when the outside world does

No internet, no AI. Outage, no AI. Rate limit on a busy afternoon, no AI.

Minor annoyances individually. They matter once something is part of how you actually work.

## 4. The rules change without you

The model you built a workflow around gets retired. Pricing changes. Terms change. A capability you relied on gets restricted.

You built a process on someone else's platform and they can move it. A model file on your own drive works the same next year as it does today.

## The honest recommendation

Not everyone needs this. If you use AI a few times a day on non sensitive material, a subscription is the right tool and you can skip the next chapter with a clear conscience.

You want your own when you handle data that can't leave the building, when you want to run something repeatedly without watching a meter, or when you want workflows that survive other people's business decisions.

For most designers the realistic answer is **both**. Local for repetitive, sensitive, high volume work. Hosted for the hard thinking where you want the strongest model and it's worth paying for.

That's not a compromise. It's using the right tool.

---

# Chapter 11: Running your own, the short version

The compressed version: enough to understand what you're doing and decide whether your machine can handle it.

## The two pieces

**The model** is a file. A very large file of numbers. Sitting on your drive it does nothing. It can't think, can't respond. It's frozen.

**The engine** is the software that reads those numbers and does the maths. Without an engine the model is dead weight.

The engine almost everything is built on is called llama.cpp. Most people don't touch it directly. They use Ollama, which wraps it and handles the details. One command and you have a model running.

## What decides whether it fits

Two things: memory size, and memory speed.

**Size decides what fits.** In raw form a model needs roughly 2 GB of memory per billion parameters. A 30B model raw is about 60 GB, more than most machines have.

Which is why nobody runs raw models.

**Quantization** shrinks them by reducing the precision of every number, like saving a photo at 80% quality instead of 100%. Slightly less detail, dramatically smaller file.

Levels are labelled Q8, Q6, Q5, Q4, Q3 and down. Lower number, smaller file, more quality lost.

**Q4 is the sweet spot** for most people: roughly a third of the original size, with quality loss you'll rarely notice in normal work. Below Q3 reasoning degrades noticeably.

So that 30B model at Q4 needs somewhere around 18 to 20 GB instead of 60. Now it fits on real machines.

**Speed depends on memory bandwidth**, how fast data moves between memory and processor. Rough rule: bandwidth divided by the size of the model actually being read gives you roughly how many pieces of text per second you'll see.

## What you don't get to use

Your model doesn't get all your RAM.

The operating system takes around 4 to 6 GB. Browser, Slack and the rest take a few more. Leave about 8 GB free for the machine to function.

On a 32 GB laptop that leaves roughly 22 to 24 GB for a model. Enough for a good mid sized model at Q4.

On a 16 GB laptop you have around 8 to 10 GB. Small models only. A 30B model at Q4 will not fit, whatever a benchmark chart tells you.

## Apple's advantage

On a typical PC, system memory and graphics memory are separate pools. If your graphics card has 8 GB, that's your ceiling regardless of system RAM.

Apple Silicon shares one pool between processor and graphics. A Mac with 32 GB can use most of it for a model, with no separate graphics card.

That's why so much local AI happens on Macs. Architecture, not brand loyalty.

On Windows or Linux you'll want a dedicated graphics card, and the number that matters is its dedicated memory (VRAM), not system RAM.

## A trick that helps

Some newer models are built so only a fraction runs for any given piece of text. The full model might be 30B while only 3B are active at a time.

Think of a company with hundreds of specialists where only the relevant few attend each meeting.

Practically: you still need memory to hold the whole model, but the speed you experience reflects only the active part. That's how a model that sounds too large for your laptop can still respond at a comfortable pace.

If a model name has two numbers in it, that's usually what it means.

## Context costs memory too

Chapter 3 covered context as craft. Here's the physical cost.

Everything in the window has to be stored while the model works. The longer your conversation, or the more you paste, the more memory that takes on top of the model itself.

Which is why a long session can slow down or run out of room even though the model fitted fine when you started.

Practical fix: keep sessions focused, start fresh when you're done with a topic, and if you must go long, summarise what matters and start again from the summary.

## What to actually do

1. Check your RAM. On a Mac: Apple menu, About This Mac.
2. Subtract 8 GB. What's left is your budget.
3. Install Ollama.
4. Start with a small model, something in the 7 to 9B range at Q4. It fits almost anywhere and it's genuinely useful.
5. Run the chapter 4 exercise on it. Feed it a pile of real material and ask for patterns with receipts.
6. Go bigger only when you hit a real limit.

Start small. A working small model teaches you more than a large one that crawls.

> **On model names:** I've deliberately kept specific models out of this chapter. They change every few months and anything I name will be outdated before you read it. The concepts (size, quantization, memory budget, bandwidth) don't move. Check a current source for what to install today.

---

# Where this leaves you

Eleven chapters, compressed.

1. It predicts the next piece of text. That's the only thing it does.
2. It has no internal sense of truth. The check has to come from outside.
3. It only sees what's in front of it. What you put there is your real leverage.
4. What you feed it decides what you get. Move up the food chain.
5. Anything can generate the hard question. Asking it out loud is the job.
6. Let it read. You decide.
7. It designs the happy path beautifully. Products are mostly the other paths.
8. Verification has to be built, and owned, by someone who knows what correct looks like.
9. Tools don't beat planning. Sequence first, then equip.
10. Own your setup when data is sensitive or volume is high.
11. Size, quantization, memory budget, bandwidth.

## What I actually think about your job

The panic is misplaced, but not baseless.

If your work is taking a brief and producing screens, arranging what someone else decided at the level of craft rather than judgement, that work is being compressed. Not because AI is good at design, but because it's fast at the surface of it, and a lot of what gets called design work is surface.

But look at what the chapters have in common. Deciding what's worth investigating. Knowing which finding matters. Asking why the problem exists. Knowing which claims need checking and being answerable when a wrong one ships. Knowing what your product does when things go wrong, which is where products actually live.

None of that is a task waiting to be automated. Most of it isn't a task at all. It's judgement plus accountability, and accountability doesn't transfer to a system that can't be held responsible.

The designers who struggle will be the ones who spent a career at level 1 with plankton inputs, and now find a machine doing it faster.

The designers who do well will move up: better inputs, deeper questions, real verification. AI is what makes moving up practical, because it removes the volume problem that used to make it impossible.

That's the actual shift. Not humans against machines. People who understood the machine, against people who argued about it.

You've understood it now. Go and use it.

---

## What's next

This book covered how AI thinks. The next covers how to give it a body: agents that run tasks, the tools they use, and how to build systems that verify themselves instead of reporting 113 files that don't exist.

---

*Written by Oussama Bougnouch, product and UX designer, 13+ years, working with teams at CHANEL, AT&T, HelloFresh and Fnac. I write about the shift from UX to AX at **uxintoax.com**.*

*Save it. Share it. Use it.*
