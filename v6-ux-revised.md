# How AI Actually Works — For People Who Haven't Opened a Terminal

---

## The Real Problem

Everyone is telling you AI is going to change everything. You've tried a few tools. They felt wrong. Your instincts are correct.

The tools most people encounter don't work well for real work. That's not because you're bad at them — it's because the version of AI people talk about in headlines is a different thing from the version that actually does useful work.

This guide explains how the real thing works. No hype. No courses to buy. Just the mechanics.

---

## Two Paths: Cloud and Local

When you use ChatGPT, Claude, or Gemini, you're using someone else's computer. When you run a model on your own machine, you're running software you own.

**Cloud:**
- Works instantly. No setup.
- But when you stop paying, it stops. Your data goes to their servers. They control what models you can use.

**Local:**
- Runs on your machine. Your data stays yours. No monthly fees after setup.
- Requires hardware that can hold a model. Results vary by model size.

The smartest workflow uses both: local for repetitive tasks you can automate (keyword research, document analysis, report building), cloud for the heavy thinking where you need the biggest models.

---

## What an LLM Actually Is

An LLM predicts the next word. That's all. It reads almost everything on the internet, plays a game with itself — guess the next word, check if it was right, adjust its connections slightly — billions of times until it learns the patterns of how language works.

It doesn't understand anything. It doesn't know anything the way you do. But the pattern matching is good enough that it *feels* like understanding.

**What this means for you:**
- It will confidently make things up if it doesn't know the answer. Verify important claims.
- It has no true comprehension. It's repeating learned patterns, not thinking.
- It's time-bound. A model trained on 2024 data won't know about events in 2025.

The key to using AI well is knowing these limits and working around them. When you know it might hallucinate, you check its facts. When you know it can't reason, you break complex problems into smaller pieces.

---

## Model Sizes, Plain English

Models are measured in billions of parameters — connections between artificial neurons. More connections mean more capacity, but not necessarily better results.

| Size | When to Use It |
|------|---------------|
| **2B–9B** | Quick tasks, fast responses, tight hardware |
| **27B–35B** | The everyday model. Writes code, summarizes documents, reasonsthrough most problems |
| **70B+** | Complex reasoning, heavy coding, requires serious hardware or cloud |
| **100B–1T+** | Cloud only. Enterprise-level tasks |

A 9B model trained on medical literature will give better medical advice than a trillion-parameter model trained on everything. Specialization beats scale in specific domains.

---

## The Team That Shows Up Only When Needed (MoE)

An Mixture of Experts model has hundreds of specialists. For each request, only the relevant ones wake up.

Write Python code? The code-writing experts activate. Ask a math question? The math experts take over. The rest stay asleep.

**Why this matters:** You can run a "35B model" on a laptop even though only 3B parameters are active for each response. The total model has 35 billion connections, but most of them sit idle until needed. This is what makes local AI practical.

| Model | Total | Active | What Actually Runs |
|-------|-------|--------|-------------------|
| Qwen 3.6-35B-A3B | 35B | 3B | 3B specialists wake up |
| Gemma 4-26B-A4B | 26B | 4B | 4B specialists wake up |

---

## What Runs the Show: The Engine

A model file is just frozen numbers. By itself, it does nothing.

The engine is the software that loads those numbers, receives your input, and runs the math to produce a response. Different engines handle this differently — some faster, some more memory-efficient.

**llama.cpp** is the core engine. Created to run AI directly on consumer hardware without heavy dependencies. Pure C/C++. Lightweight. Fast.

**Ollama** wraps llama.cpp into something you can use without touching a configuration file. One command — `ollama run llama3` — and you have a working model.

Start with Ollama. It's the fastest way to get running. Once you understand what's happening under the hood, you can explore llama.cpp directly.

---

## The Memory Problem

Your AI model has to fit in your computer's memory. If it doesn't, everything slows to a crawl.

**RAM** — your computer's regular memory. Huge but slower. Holds your OS, browser tabs, apps, and the model.

**vRAM** — memory inside your graphics card. Tiny compared to RAM but much faster. AI needs speed more than it needs size.

**The rule:** your model must fit in fast memory (vRAM or Apple Silicon's unified memory) for good performance. When it spills into slower system RAM, you might go from 15 tokens per second to 1 token per second.

---

## Why Apple Silicon Is Different

Regular PCs have two separate memory pools — CPU RAM and GPU vRAM. If a model doesn't fit in the GPU's 8–24 GB of vRAM, it spills into the slower CPU RAM.

Apple Silicon shares one memory pool between CPU and GPU. A MacBook with 32 GB of RAM means the GPU can use all 32 GB — not just 8 GB.

This is why local AI exploded on Macs. You get massive memory capacity without buying a $500 graphics card.

| Machine | RAM | What Fits (Q4) |
|---------|-----|----------------|
| MacBook Air M2 (8GB) | 8 GB | 5B–7B models |
| MacBook Pro M3 (16GB) | 16 GB | 11B–13B models |
| MacBook Pro M3 (32GB) | 32 GB | 22B–27B models |
| Mac Studio M3 Ultra (192GB) | 192 GB | 130B+ models |

Always leave 8 GB free for your OS and regular apps.

---

## Why Speed Varies: The Bandwidth Rule

Your model reads all its numbers every time it generates a token. The bottleneck isn't the math — it's getting the data to the processor fast enough.

**Bandwidth** = how much data flows from memory to the processor per second.

> Response speed ≈ Memory bandwidth ÷ Model size

A 22 GB model on a machine with 270 GB/s bandwidth generates about 12 tokens per second. A 5 GB model on the same machine? About 54 tokens per second. Smaller models run faster because they need less data flowing through the bus.

| Machine | Bandwidth | Typical Speed (22 GB model) |
|---------|-----------|-----------------------------|
| MacBook Pro M3 (32GB) | 270 GB/s | ~12 t/s |
| Mac Studio M3 Ultra | ~800 GB/s | ~35 t/s |
| RTX 4090 | ~1,000 GB/s | ~45 t/s |

For reference: 8–12 tokens per second feels like natural conversation. 30+ feels instant.

---

## Making Big Models Fit: Quantization

Quantization reduces the precision of the numbers in a model. A 16-bit number has more decimal places than an 8-bit number. Fewer bits means smaller file size, with some quality loss.

| Level | Size | Quality |
|-------|------|---------|
| Q8 | ~50% of original | Nearly identical |
| Q6_K | ~42% | Very good |
| **Q4_K_M** | **~32%** | **Great — sweet spot** |
| Q3_K_M | ~24% | Noticeable drop |

A 35B model in full precision needs 70 GB of RAM. Quantized to Q4, it needs 22 GB. That's the difference between not fitting on your machine at all and running comfortably on a MacBook Pro with 32 GB.

Q4 is the sweet spot. You keep nearly all the quality for about a third of the size.

---

## How Long Conversations Work (And When They Break)

AI models have a context window — a limit on how much text they can hold in memory at once. If the window is 8K tokens, the model can only remember the last ~8,000 tokens of the conversation.

**The KV cache** is the memory used to store what the model has seen so far. As your conversation grows, the KV cache grows with it. For long conversations, the KV cache can use more memory than the model itself.

**What happens in practice:**
- Short conversations (under 10 turns) — no issues
- Medium conversations (10–50 turns) — model remembers most of what was said
- Long conversations (50+ turns) — KV cache grows large, you might run out of RAM

**The workaround:** summarize the early parts of a long conversation and paste the summary back in. The model gets the key information without storing every single word.

---

## Other Tricks That Make It Faster

**Speculative decoding:** a small model guesses what the big model will say, and the big model verifies the guess in one pass. If it's right, you get the answer faster. If wrong, the big model corrects it. No quality loss, faster responses.

**Paged Attention:** borrows from operating systems. Lets the model use disk storage as "virtual RAM" for the KV cache. Longer conversations possible without running out of memory — slower, but not broken.

**Embedding compression:** reduces precision of the input text numbers. Similar to quantization, applied to your prompt instead of the model weights.

---

## Quick Reference

**Which model for your task?**
- Quick tasks on limited hardware → 2B–9B
- Everyday laptop use → 27B–35B (MoE recommended)
- Serious desktop work → 70B+ (quantized)
- Complex reasoning → cloud only

**Which quantization?**
- Plenty of RAM → Q8 or Q6
- Best balance → Q4 (default for most people)
- Short on RAM → Q3

**Hardware minimums:**
- Mac with Apple Silicon → 16 GB minimum, 32 GB recommended
- PC with NVIDIA GPU → 12 GB VRAM minimum for medium models
- PC without dedicated GPU → 32 GB+ system RAM for small models

---

## The Privacy Thing

When you ask ChatGPT about your health symptoms, that conversation goes to OpenAI's servers. When you ask Claude about your finances, it goes to Anthropic's servers.

They say they don't store your data. They say they don't use it to train their models. You have to trust them. You can't verify. You can't audit.

With local AI, your data stays on your machine. No servers. No policies. No trust required.

This is the benefit nobody talks about enough.

---

*Written for everyone who's been told AI is complicated and needs expensive courses. It isn't.*
