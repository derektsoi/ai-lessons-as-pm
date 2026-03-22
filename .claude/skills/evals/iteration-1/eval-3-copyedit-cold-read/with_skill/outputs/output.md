# Copyedit: lessons/05-substack-draft.md

**Reading cold. No scaffold context.**

**Thesis (one sentence):** The gap between "using AI" and "building on AI" is an infrastructure gap the author created but can't explain or transfer, and he owes his team a fair path before the next review cycle.

That holds. The piece argues one thing and lands where it starts. No thesis drift.

---

## Line Edits

```
Line 7: "Every PM on my team now has an AI learning OKR. It affects their performance review — salary and bonus."
→ "Every PM on my team now has an AI learning OKR. It affects their performance review — salary, bonus, the works."
Reason: "Salary and bonus" reads like an HR document. "The works" matches the author's direct, slightly wry voice and conveys the same stakes with less bureaucratic tone.
```

```
Line 7: "The team responded well. No pushback. AI learning tasks in everyone's goals."
→ "No pushback. AI learning tasks in everyone's goals."
Reason: "The team responded well" tells the reader what to think before showing the evidence. The next two sentences already demonstrate the response. Cut the narrator summary and let the facts land.
```

```
Line 9: "And the gap between the two is larger — and harder to see — than I expected."
→ "The gap between the two is larger — and harder to see — than I expected."
Reason: Starting with "And" after a period works for rhythm sometimes, but this sentence is the thesis landing. It's stronger without the conjunction softening the punch.
```

```
Line 17: "Everyone used Claude Code for OKRs — I know because all their output is in markdown format."
→ "Everyone used Claude Code for OKRs — I know because the output is all markdown."
Reason: "All their output is in markdown format" is wordy. "The output is all markdown" is tighter and matches the author's direct voice.
```

```
Line 17: "Nobody is drafting in a chatbot and downloading it back to GitHub just to comply."
→ "Nobody is drafting in a chatbot and copy-pasting it into GitHub just to comply."
Reason: "Downloading it back to GitHub" isn't how that works — you push or paste to GitHub, not download to it. "Copy-pasting" is what the actual workaround would look like, and it's more concrete.
```

```
Line 17: "And the team IS using AI: I can see them building demos on chatbots like POE."
→ "The team is using AI — I can see them building demos on chatbots like Poe."
Reason: Three changes. (1) Starting another sentence with "And" — second time in this section, loses its punch. (2) "IS" in all caps reads as shouting in text; the em-dash provides the emphasis. (3) "POE" should be "Poe" — that's the product's actual capitalization.
```

```
Line 17: "Give them credit."
→ Cut this sentence.
Reason: The author is talking to himself in front of the reader. The evidence that follows already gives them credit. This instruction-to-self breaks the essay's flow.
```

```
Line 17: "But it's chatbot-level usage — no company context, no design guidelines, no accumulated knowledge, starting from zero each session."
→ "But it's chatbot-level usage — no company context, no design guidelines, no accumulated knowledge. Starting from zero every session."
Reason: The list of three is strong. "Starting from zero each session" deserves its own sentence — it's the kicker, not a fourth list item. "Every" is slightly sharper than "each" here.
```

```
Line 19: "She's producing full interactive prototypes independently."
→ "She's producing full interactive prototypes on her own."
Reason: "Independently" is an adverb doing the work that a phrase does better. "On her own" sounds like a person; "independently" sounds like a performance review.
```

```
Line 19: "The expectation-setting didn't create her adoption. It just confirmed it."
→ "The OKR didn't create her adoption. It confirmed it."
Reason: "Expectation-setting" is management jargon. The reader knows you're talking about the OKR from context. Also cut "just" — the sentence is already concise; "just" adds a hedge.
```

```
Line 29: "But a UAT report for an OCR vendor evaluation — one that requires processing hundreds of images, cross-referencing two vendors' results, creating ground truth labels, embedding failure examples into the report, then drafting a message to management?"
→ "But a UAT report for an OCR vendor evaluation — processing hundreds of images, cross-referencing two vendors' results, creating ground truth labels, embedding failure examples, then drafting the summary for management?"
Reason: (1) "One that requires" is a relative clause that slows down the cascade. Cut it and let the list run directly. (2) "Embedding failure examples into the report" — "into the report" is obvious since we're talking about the report. (3) "Drafting a message to management" — "message" undersells it; "summary" is more precise for a UAT context.
```

```
Line 29: "That's five tools working in sequence, each one inheriting context from the last."
→ "Five tools in sequence, each inheriting context from the last."
Reason: "That's" + "working" are filler. The stripped version hits harder.
```

```
Line 31: "Then I watched one of my PMs building a demo by chatting with an AI."
→ "Then I watched a PM build a demo by chatting with an AI."
Reason: "One of my PMs building" is wordy. "A PM build" is cleaner. The possessive "my" is unnecessary — we know they're on your team.
```

```
Line 31: "No test cases defined upfront. No clear end goal. Just conversing with the chatbot and hoping the output would converge on something useful."
→ "No test cases. No end state. Just chatting and hoping the output would converge."
Reason: "Defined upfront" and "clear" are padding — the absence is the point. "End goal" → "end state" is more precise (goals are aspirational; states are verifiable, which is the author's own framework). "Conversing with the chatbot" → "chatting" — you already said "chatting with an AI" one sentence ago. "On something useful" is implied by "hoping."
```

```
Line 31: "And I realized: that's how chatbots work. You chat and hope."
→ "That's how chatbots work. You chat and hope."
Reason: Third "And I realized" pattern in the piece. The colon after "realized" already signals the insight. But cutting the whole lead-in is stronger — "That's how chatbots work" hits harder as a standalone declaration.
```

```
Line 31: "The infrastructure approach is fundamentally different — you define what 'done' looks like, let the agent work, then verify the output against your criteria."
→ "Infrastructure works differently — you define what done looks like, let the agent run, then verify."
Reason: "Fundamentally different" is a hedge-amplifier. "Differently" does the job. "The infrastructure approach" → "Infrastructure" — shorter, same meaning. "Let the agent work" → "let the agent run" — "run" is more concrete for software. "Against your criteria" is implied by "verify" in this context.
```

```
Line 31: "My PMs weren't just using a simpler tool. They had a completely different mental model for how AI should work."
→ "My PMs didn't have a simpler tool. They had a different mental model."
Reason: "Weren't just using" implies the simpler tool is part of it; the actual point is the mental model is entirely different. "Completely different mental model for how AI should work" — "completely" is filler, and "for how AI should work" restates what the whole section already establishes.
```

```
Line 31: "They were very far from the agentic approach with verification loops, and they didn't know what they were missing."
→ Cut this sentence.
Reason: This restates the previous three sentences. The reader already understands the gap. Ending on "They had a different mental model" is stronger.
```

```
Line 33: "I couldn't see this gap because I was standing on it. I'd built the penthouse floor by floor over months. From up there, the view was obvious. From the ground, there's no skyline — just a tool that seems like a fancier chatbot."
→ No edit. This is the best paragraph in the piece. Leave it.
```

```
Line 39: "O didn't adopt because of a feature demo or a vision speech. She had a monthly SEO report."
→ No edit. Strong opening. The contrast lands.
```

```
Line 41: "At the start, this meant manually pulling data from the data team's tables, assembling the numbers, writing the analysis."
→ "At the start: manually pulling data from the data team's tables, assembling the numbers, writing the analysis."
Reason: "This meant" is throat-clearing. A colon does the same work in one character.
```

```
Line 41: "Now she runs a command and Claude generates a full visual report — branded charts, region-by-region breakdowns, trend lines the team can hover over to see specific numbers."
→ "Now she runs a command and gets a full visual report — branded charts, region-by-region breakdowns, trend lines you can hover to see exact numbers."
Reason: "Claude generates" names the tool when the reader cares about the output. "The team can hover over" → "you can hover" — more direct, pulls the reader in. "Specific" → "exact" — sharper.
```

```
Line 41: "The infrastructure she built didn't just save time. It made the output better than what she could produce manually."
→ "The infrastructure didn't just save time. It made the output better than what she could produce by hand."
Reason: "She built" is unnecessary — we've been talking about her building it. "Manually" → "by hand" — less corporate, more physical, matches voice.
```

```
Line 43: "Here's what makes the SEO report different from other PMs' recurring work: it has consistent metrics and a cross-team data dependency."
→ "What makes the SEO report different: consistent metrics and a cross-team data dependency."
Reason: "Here's" is a filler opener. "It has" restates what the colon already introduces. Cut both.
```

```
Line 43: "That combination — stable metrics plus external dependency — made infrastructure worth building."
→ "That combination — stable metrics, external dependency — made infrastructure worth building."
Reason: "Plus" reads as casual math. The em-dash parenthetical works better as a list with a comma.
```

```
Line 51: "Richard Feynman said if you can't explain something simply, you don't understand it well enough. He just caught me."
→ "Feynman said if you can't explain something simply, you don't understand it. He just caught me."
Reason: "Richard Feynman" — everyone who reads Substack newsletters knows who Feynman is. First-name formality is unnecessary. "Well enough" is implied by the quote's logic.
```

```
Line 55: "configuration files give Claude company context, skills automate repeated review patterns, agent teams challenge work from multiple angles, hooks enforce quality gates"
→ "configuration files give Claude company context, skills automate review patterns, agent teams challenge work from multiple angles, hooks enforce quality gates"
Reason: "Repeated" is redundant — automation implies repetition.
```

```
Line 57: "And it's worse than I initially thought."
→ "It's worse than I thought."
Reason: "And" opening again (recurring pattern). "Initially" is filler — "than I thought" already implies an earlier assessment.
```

```
Line 57: "I have no idea. I brute-forced it."
→ No edit. Perfect.
```

```
Line 59: "Obsession isn't a method. I can't hand someone my obsession and say 'now go build infrastructure.'"
→ No edit. This is the piece's emotional peak. Don't touch it.
```

```
Line 59: "But that's essentially what I've been doing — showing the result of obsessive experimentation and wondering why people don't replicate it."
→ "That's what I've been doing — showing the result of obsessive experimentation and wondering why people don't replicate it."
Reason: "But" and "essentially" are both softeners. The sentence is an admission. Let it cut.
```

```
Line 67: "I tied AI adoption to performance reviews before I could explain the path. Before I could define what support looks like. Before I could even answer Feynman Test B."
→ No edit. The repetition is intentional and effective.
```

```
Line 69: "The clean move would be to wait — understand the conversion mechanism first, build the support plan, then set the expectations."
→ "The clean move would be to wait — understand the conversion first, build the support plan, then set expectations."
Reason: "Conversion mechanism" appeared earlier and was specific there; here it's becoming jargon through repetition. "The expectations" → "expectations" — the article drops after "set the," which slightly deflates the end of the sentence.
```

```
Line 69: "But waiting is the mistake I made before: staying in 'proving it' mode for months because it was comfortable."
→ No edit. Strong callback to lesson 04. Works even without having read that piece.
```

```
Line 73: "I've started a weekly improvement loop to trace my own process — tracking what frustrated me, what I built in response, and whether it helped."
→ "I've started a weekly improvement loop — tracking what frustrated me, what I built in response, and whether it helped."
Reason: "To trace my own process" is a purpose clause that restates what the list already shows. Cut the middleman.
```

```
Line 73: "The first iteration already caught something I would have missed: Claude fabricating business logic is a recurring problem, and my existing safeguards weren't catching it."
→ "The first iteration caught something I would have missed: Claude fabricating business logic. A recurring problem my safeguards weren't catching."
Reason: "Already" is filler enthusiasm. Breaking after "business logic" creates a beat before the admission that safeguards failed — more impact.
```

```
Line 73: "Fabricated product names that passed through all three debate agents undetected. A fake contract clause cited in a vendor review."
→ No edit. The specifics are excellent. This is the piece earning its credibility.
```

```
Line 73: "Multi-agent review — the infrastructure I was proudest of — didn't catch fabrications. It amplified them."
→ No edit. Best single sentence in the section.
```

```
Line 73: "One iteration doesn't prove it works. But it's the beginning of the map I need to eventually pass Test B."
→ "One iteration doesn't prove it works. But it's the start of the map I need to pass Test B."
Reason: "Beginning" → "start" — tighter. "Eventually" is hedging.
```

```
Line 73: "And next week, I'm having conversations with the team I should have had months ago: what does AI adoption look like from their side?"
→ "Next week, I'm having the conversations I should have had months ago: what does AI adoption look like from their side?"
Reason: "And" opener again. "With the team" is implied — the whole piece is about the team. "The conversations" (with "the") adds weight that "conversations" alone wouldn't.
```

```
Line 73: "Five lessons in, it's all been my perspective."
→ No edit. Good closing beat for this section.
```

```
Line 79: "If a junior PM fails to make the transition in the next review cycle, I need to be able to honestly say I gave them a fair shot."
→ "If a junior PM fails to make the transition next cycle, I need to honestly say I gave them a fair shot."
Reason: "In the next review cycle" → "next cycle" — we're in review context already. "Be able to honestly say" → "honestly say" — "be able to" is hedging the commitment.
```

```
Line 81: "So next week: I sit with each PM and ask what AI adoption looks like from their side — not what I assume, what they actually experience."
→ This partially repeats line 73. Consider cutting or condensing. If kept:
"Next week: I sit with each PM and ask what they actually experience — not what I assume."
Reason: "What AI adoption looks like from their side" was already stated two paragraphs ago. Flip the structure to lead with "actually experience" since that's the new emphasis.
```

```
Line 81: "I map which tasks have the dependency structures that make infrastructure worth building."
→ "I map which of their tasks have the structure that makes infrastructure worth building."
Reason: "Dependency structures" is jargon. You defined it in the O section — "consistent metrics and a cross-team data dependency" — so the reader understands the concept, but "dependency structures" as a compound noun hasn't been earned.
```

```
Line 81: "I make it clear they can push back for time to experiment — and I need them to be honest about whether they're actually using it."
→ "I tell them they can push back for time to experiment — and I need honesty about whether they're actually using it."
Reason: "Make it clear" is management-speak. "Tell them" is what you'd actually do. "I need them to be honest" → "I need honesty" — tighter.
```

```
Line 81: "If they are, I'll defend them to management. If not, the time isn't helping."
→ No edit. Clean conditional. Good.
```

---

## Structural Issues

- **Voice breaks:** Two minor zones. (1) The middle of the Infrastructure Gap section (line 31, "They were very far from the agentic approach with verification loops") slips into explainer mode — sounds like a conference talk, not a PM reflecting. Addressed by the line edit cutting that sentence. (2) "Expectation-setting" on line 19 is HR jargon. Addressed by line edit. Neither is severe enough to route back.

- **Missing emotional beat:** No. The piece has two strong felt moments: "Obsession isn't a method" (line 59) and the Feynman Test B failure admission (line 57). The fabrication discovery in The Bet section is a third. Emotional arc is solid.

- **Thesis drift:** None. The piece opens with the gap, explores why it exists, admits the author can't explain it, and commits to figuring it out. Linear and honest.

- **Hook strength:** The first two paragraphs work. The opening is concrete (OKRs, performance reviews, GitHub, pull requests) and delivers a twist by paragraph two ("That's not adoption. That's compliance."). A reader would keep scrolling. One small note: "Every PM on my team" is a cold open with no scene-setting — the reader doesn't know who this person is yet. But the bio at the bottom handles that, and the directness is a feature, not a bug. **Hook passes.**

---

## Verdict

**Needs line edits** — Substantive but sentence-level. The piece is structurally sound and emotionally honest. Main patterns to fix: (1) over-reliance on "And" as a sentence opener, (2) a few management-jargon phrases that break voice, (3) some redundancy in The Bet section's closing where the action items partially repeat. Apply the edits above and re-read once.

---

## Substack SEO Fields

- **SEO Title** (58 chars): `The AI Infrastructure Gap Your Team Can't See`
- **SEO Description** (~148 chars): `I tied AI adoption to performance reviews before I could explain the path. Here's what months of building taught me about why my team can't follow.`
- **URL Slug**: `infrastructure-gap-ai-adoption`
- **Suggested Tags**: Product Management, AI Tools, Leadership, Team Development, AI Adoption
