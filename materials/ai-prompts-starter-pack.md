# The AI Prompt Starter Pack
Copy-paste prompts for research, writing, coding, and business. They work in ChatGPT, Claude, Gemini, Perplexity, or any similar assistant. Swap in your own details wherever you see [BRACKETS].

These prompts follow techniques from the most-used open prompt-engineering guides on GitHub. Each prompt uses one or more of them:

| Source | GitHub stars (Oct 9, 2026) | What we borrowed |
|---|---|---|
| f/prompts.chat (formerly Awesome ChatGPT Prompts) | ~172k | The "act as a…" role pattern, and a free library of 1,000+ community prompts |
| dair-ai/Prompt-Engineering-Guide | ~79k | Few-shot examples and step-by-step reasoning |
| openai/openai-cookbook | ~76.5k | Meta-prompting (asking the AI to improve your prompt) |
| anthropics/prompt-eng-interactive-tutorial | ~38k | Being clear and direct, separating data from instructions with tags, and avoiding hallucinations |

## The 5 rules that make any prompt better
1. Say who it's for and what "done" looks like.
"Write a summary" is weak. "Write a 5-bullet summary for a busy manager who will decide yes/no" is strong.
2. Put your material inside tags.
Wrap pasted text in <document>...</document> so the AI can tell your instructions from your data (Anthropic tutorial, ch. 4).
3. Show an example.
One sample of the output you want beats a paragraph describing it (few-shot prompting, DAIR guide).
4. Let it think first.
Ask it to reason step by step, or to list its assumptions before it answers (Anthropic tutorial, ch. 6).
5. Give it permission to say "I don't know."
This is the simplest guard against made-up facts (Anthropic tutorial, ch. 8).

## 1. Research
### 1.1 Fast, sourced briefing
Research [TOPIC] and give me a briefing for [WHO IT'S FOR, e.g. "a small-business owner deciding whether to adopt it"].
Format:
- 3-sentence summary
- 5 key facts, each with a source link and the date of that source
- What experts disagree about
- What is still unknown
Only use sources from the last [12 months]. If you can't find a reliable source for a claim, say "unverified" instead of guessing.

### 1.2 Compare options on the same criteria
Compare [OPTION A], [OPTION B], and [OPTION C] for [MY USE CASE].
Make a table with these columns: price, key strength, key weakness, best for, source link.
After the table, recommend one in two sentences and say what would change your recommendation.

### 1.3 Read a long document for me
<document>
[PASTE TEXT]
</document>
Answer these using only the document above. For each answer, quote the sentence it comes from. If the document doesn't say, write "Not in document."
1. [QUESTION]
2. [QUESTION]

### 1.4 Steelman both sides
I believe [YOUR POSITION]. Give me the strongest argument against it, as a smart critic would make it. Then tell me which of my assumptions is weakest and what evidence would change my mind.

### 1.5 Fact-check a claim
Fact-check this claim: "[CLAIM]".
Break it into separate factual statements. For each one, say whether it's true, false, misleading, or unverifiable, give the best source you can find, and explain in one sentence.

## 2. Writing
### 2.1 Rewrite in my voice
Here are two samples of my writing:
<sample1>[PASTE]</sample1>
<sample2>[PASTE]</sample2>
Describe my style in 5 bullet points (sentence length, tone, words I use, things I avoid). Then rewrite the following text in that style without changing its meaning:
<draft>[PASTE]</draft>

### 2.2 Email that gets a reply
Write an email to [RECIPIENT + RELATIONSHIP] asking for [SPECIFIC ASK].
Context: [1-2 SENTENCES].
Rules: under 120 words, the ask in the first two sentences, one clear question they can answer with yes or no, no buzzwords. Give me 2 subject-line options.

### 2.3 Edit, don't rewrite
Edit this for clarity and concision. Keep my voice. Do NOT add new ideas.
Show the edited version, then list each change you made and why, in one line each.
<text>[PASTE]</text>

### 2.4 Turn notes into a structured post
Turn these rough notes into a [blog post / LinkedIn post / newsletter section] of about [WORD COUNT] words for [AUDIENCE].
Open with the most surprising point, not background. Use short paragraphs. End with one practical takeaway.
<notes>[PASTE]</notes>

### 2.5 Headline and hook testing
Write 10 headlines for this piece, using different angles: number, question, contrarian, how-to, outcome, curiosity.
Then pick the 3 strongest and explain why in one line each. Avoid clickbait and claims the piece doesn't support.
<piece>[PASTE OR SUMMARIZE]</piece>

## 3. Coding
### 3.1 Explain unfamiliar code
Explain this code to someone who knows [LANGUAGE] basics but not this codebase.
1. What it does in one sentence
2. A walk through the logic, step by step
3. Any bugs, edge cases, or security issues you notice
<code>
[PASTE]
</code>

### 3.2 Debug with evidence
I'm getting this error:
<error>[PASTE FULL ERROR + STACK TRACE]</error>
Relevant code:
<code>[PASTE]</code>
What I expected: [X]. What happened: [Y]. What I already tried: [Z].
List the 3 most likely causes, ranked, with how to confirm each one before changing code. Then give the fix for the most likely cause.

### 3.3 Write a function with tests
Write a [LANGUAGE] function that [DOES X].
Inputs: [TYPES + EXAMPLES]. Output: [TYPE + EXAMPLE].
Requirements: handle [EDGE CASES], no external libraries except [ALLOWED].
Also write unit tests covering normal cases, edge cases, and invalid input. Explain any assumption you made.

### 3.4 Code review
Review this pull request as a senior engineer. Prioritize: correctness, then security, then performance, then readability.
For each issue: severity (high/med/low), the line, the problem, and a suggested fix. Don't comment on style unless it hurts readability.
<diff>[PASTE]</diff>

### 3.5 Plan before building
I want to build [PROJECT] using [STACK]. Before writing any code, give me:
1. The file and folder structure
2. Data models
3. The 5 riskiest parts and how to de-risk each
4. A build order where each step can be tested on its own
Ask me up to 3 questions first if anything important is unclear.

## 4. Business
### 4.1 Customer-research interview script
I'm validating a [PRODUCT/SERVICE] for [TARGET CUSTOMER].
Write a 15-minute interview script with 8 open questions about their current problem and what they do today. Don't pitch my idea, and avoid leading questions.
Add a short note on what answers would mean "real pain" vs. "nice to have."

### 4.2 Honest offer page
Write sales-page copy for [OFFER] for [CUSTOMER].
Include: the problem in their words, what they get (specific deliverables), price [PRICE], who it's NOT for, and an FAQ of 5 questions.
Rules: no income or results guarantees, no fake urgency, no claims I can't prove. Mark any spot where I should add a real testimonial or number as [ADD PROOF].

### 4.3 Pricing sanity check
I'm pricing [SERVICE/PRODUCT].
My costs: [TOOLS, HOURS, FEES]. Target customer: [WHO]. Competitor prices I've seen: [LIST WITH SOURCES].
Calculate my break-even price and the price at a [X]% margin. Suggest 3 pricing structures (one-off, monthly, tiered) with the trade-offs of each. Show your math.

### 4.4 Turn a messy process into an SOP
Here's how I currently do [TASK]:
<process>[DESCRIBE OR PASTE NOTES]</process>
Turn it into a standard operating procedure: numbered steps, who does each, tools used, time per step, and a checklist at the end. Flag any step that could be automated with AI, and say how.

### 4.5 Meeting to action items
<transcript>[PASTE]</transcript>
Extract: decisions made, action items (owner + deadline), open questions, and risks mentioned. Use only what's in the transcript. If an owner or deadline wasn't stated, write "unassigned."

### 4.6 Cold outreach that isn't spam
Write a short first message to [TYPE OF BUSINESS] offering [SERVICE].
Use this specific observation about them: [SOMETHING REAL YOU NOTICED].
Under 80 words, one clear low-effort next step, no hype, no fake familiarity.

## 5. Meta-prompts (prompts that improve prompts)
### 5.1 Improve my prompt
(adapted from the OpenAI Cookbook's meta-prompting example)
Here is a prompt I'm using:
<prompt>[PASTE]</prompt>
It produces [WHAT'S WRONG WITH THE OUTPUT].
Rewrite the prompt so it fixes that. Explain each change in one line.

### 5.2 Interview me first
I want help with [GOAL]. Before you answer, ask me the 3-5 questions whose answers would most change your advice. Wait for my answers.

### 5.3 Self-check before final
Before giving your final answer, check your draft for: claims without sources, numbers you're unsure of, and anything that doesn't answer my actual question. Fix those, then give me only the final version.

## Free places to learn more
- Anthropic's Prompt Engineering Interactive Tutorial: 9 chapters with exercises and an answer key.
- promptingguide.ai: the web version of the DAIR.AI guide.
- prompts.chat: a searchable community prompt library, CC0-licensed and free to reuse.
- NirDiamant/Prompt_Engineering: about 7.4k stars, with 22 hands-on notebook tutorials.

All prompts in this pack are original and free to share. Techniques are credited to the repositories above.

---
*From [AI Money Lab](https://www.youtube.com/@aimoneylab1-k6v) — honest, hands-on AI tool reviews. Full review archive: [ai-money-lab-reviews](https://github.com/linkipark/ai-money-lab-reviews).*
