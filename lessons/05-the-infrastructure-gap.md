# The Gap Between Using AI and Using AI Well Is Invisible Infrastructure

> Status: Draft
> Core message (1 sentence): I couldn't see the gap between my team and me because I was standing on months of infrastructure I'd built through obsession — and obsession isn't a method I can teach.
> Core message (full): My team uses AI. I build on AI. The difference is months of accumulated infrastructure I can't see from the inside, can't explain simply enough to teach, and built through obsessive experimentation that isn't replicable — which means I'm leading a transformation I don't yet understand.

## The Setup

Lesson 04 ended with: "I'm about to set expectations. I'll let you know how it goes."

I set them. Every PM now has an AI learning OKR, and it affects their performance review — which means salary and bonus. I moved OKR planning to GitHub, with my departmental OKR and individual guidance as .md files. To work on their OKRs, the team had to use Claude Code because that's where the inputs lived.

But I was deliberate about what the expectation actually was. It's not "use AI." It's "deliver more." AI just happens to be the most likely way to get there. I told the senior PM: if you can deliver consistent business reviews without AI, go for it — but I don't think that's possible. For the other PMs, I was specific: if your gap is metrics monitoring and problem solving, focus there. Don't waste time learning to build demos if that's not where you need to grow.

The team responded reasonably. Their OKRs include AI learning tasks. No pushback. Early signs are OK. Then I looked closer.

---

## The Honest Check

Everyone used Claude Code for OKRs. I know this because all their output is in .md format — nobody is drafting in a chatbot and downloading it back to GitHub just to comply.

But I checked the pull requests. Only Olivia has PRs for non-OKR work. Everyone else submits only when they're doing OKRs. That's compliance, not adoption. Nobody has used Claude Code for something they weren't asked to do.

The team IS using AI — I can see them building demos on POE, which is a chatbot. Give them credit for that. They're not refusing to engage with AI. But it's chatbot-level usage: no brand guidelines, no accumulated context, starting from zero each session.

Olivia is the standout. She's producing full interactive prototypes independently — merchant rankings, marketplace data, Cantonese content, trend lines the COO can explore. But she was already the strongest adopter before the OKR move. The expectation-setting didn't create her adoption. It just confirmed it.

---

## The Infrastructure Gap

The gap between "using AI" and "using AI well" isn't about features or willingness. It's about accumulated infrastructure.

Over months, I layered my Claude Code environment: configuration files that give it company context, brand guidelines so every output follows our design system, skills that automate my most common review patterns, agent teams that challenge work from multiple perspectives. Each layer took weeks to build. Each one made the next session smarter than the last.

To be fair, a chatbot can compound too — Claude's Cowork feature is remarkably close to Claude Code on VS Code. If you're an individual contributor at an equity research firm, no team to coordinate with, Cowork might be all you need. The limitation isn't capability. It's that everything stays local. You can't share your infrastructure with a team. You can't have five PMs inheriting the same brand guidelines, the same review patterns, the same company context. For a team, the infrastructure needs to live somewhere shared — and that's where the gap between chatbot-level usage and infrastructure-backed usage starts to matter.

The compound effect only shows up when you need it. A simple demo? A chatbot can brute-force that — I see my PMs doing it on POE. But a UAT report for an OCR vendor evaluation — one that requires processing hundreds of images, cross-referencing two vendors' results, creating ground truth labels, embedding failure examples into the report, then drafting a message to management? That's not a chatbot task. That's five tools working in sequence, each one inheriting context from the last. The infrastructure is what makes the task possible, not just faster.

I couldn't see this gap because I was standing on it. When I looked at the team and thought "why aren't they getting it?" — I was comparing months of accumulated layers to a first login. The view from the penthouse is obvious to the person who built it, floor by floor. From the ground, there's no skyline — just a tool that seems like a fancier chatbot.

---

## The Olivia Evidence

Olivia didn't adopt because of a feature demo or a vision speech. She had a monthly SEO report.

At the start, this meant manually pulling data from the data team's tables, assembling the numbers, writing the analysis. Same task every month, same metrics, same tedium. Now she runs a command and Claude generates a full visual report — branded charts, region-by-region breakdowns, trend lines the team can hover over to see specific numbers. The infrastructure she built didn't just save time. It made the output better than what she could produce manually.

But here's what makes the SEO report different from other PMs' recurring work: it has consistent metrics and a cross-team data dependency. Olivia tracks the same numbers every month — sessions, rankings, click-through rates by region. And the data comes from the data team's pipeline, not from something she can pull up in a browser. That combination — stable metrics plus external dependency — made infrastructure worth building. You can automate what repeats and connects to other systems. You can't automate what changes every time.

Other PMs have monthly reports too. But their work is new feature analysis — different data, different questions, different stakeholders each cycle. There's no stable foundation to build on. It's not that they lack the pain. It's that the structure of their tasks doesn't reward the investment.

The forcing function isn't just recurring pain. It's recurring pain with a stable structure underneath — consistent metrics, repeated data dependencies, the same pipeline month after month. That's what converts pain into infrastructure instead of endurance.

And the payoff extends beyond the report. Olivia built a shopping intelligence prototype for the COO — a full interactive page with merchant rankings, marketplace comparisons, FAQ content in Cantonese, trend data you can explore. The COO liked it. That prototype wasn't the goal of her infrastructure investment. It was a side effect. Once the layers existed, they applied to new problems she hadn't planned for.

I can't fully explain why this worked for Olivia and not other PMs. The task structure matters — but something about her disposition made the pain convert to building rather than enduring. I asked her about it. She pointed to the SEO reports as the driver. She couldn't name the rest either.

---

## The Feynman Test

Richard Feynman: "If you can't explain something simply, you don't understand it well enough." I studied physics. This principle is in my bones. And it just caught me.

There are two versions of this test, and I pass one and fail the other.

Test A: can I explain what I built? Yes. Each layer does something specific — configuration files give Claude company context, skills automate repeated review patterns, agent teams challenge work from multiple angles, hooks enforce quality gates. I can walk anyone through the system. I pass this test.

Test B: can I explain what makes someone cross from using AI to building on it? No. And it's worse than I initially thought. I don't just fail this at the macro level — I can't even explain my own progression between layers. When should a PM move from writing a CLAUDE.md to building skills? When do hooks become worth the setup cost? I have no idea. I brute-forced it. I tried everything, kept what worked, and moved on. That only worked because I have the obsession to try everything.

Obsession isn't a method. I can't hand someone my obsession and say "now go build infrastructure." But that's essentially what I've been doing — showing the result of obsessive experimentation and wondering why people don't replicate it.

Test A is about the system. Test B is about the transformation. My team doesn't need a feature tour — they need me to understand the conversion mechanism so I can create the right conditions. And right now, the honest answer is: I don't understand it. I built something powerful through brute force and intensity, and I can't trace the path well enough to guide someone else down it.

Until I can answer Test B simply, I don't understand AI transformation well enough to lead it deliberately.

---

## The Weekly Learning Loop

I can't explain my process. But I can start tracking it.

I've built a weekly improvement loop: pull GitHub PRs, Slack messages, and Claude Code usage insights, then run a structured retrospective — what worked, what didn't, what to change. The output isn't a report. It's new rules, new skills, new hooks that become part of the environment for next week's work. Infrastructure building infrastructure.

The first iteration already surfaced something I would have missed: Claude fabricating business logic is a recurring problem, and my existing safeguards weren't catching it. Fabricated product names that passed through all three debate agents undetected. A fake contract clause cited in an eBay review. Contradictory data counts that nobody flagged. Multi-agent review — the thing I was proudest of building — didn't catch fabrications. It amplified them. The rules I'd written to prevent this were scoped to specific project directories, so they didn't apply everywhere. The loop caught the pattern, the gap analysis identified why, and the fix was a universal source-tracing rule: every factual claim must cite where it came from.

That's one week. One frustration traced to one infrastructure fix. Going forward, I'll be able to map: what frustrated me, what I built in response, and whether it actually helped. That's the map I need to eventually pass Feynman Test B.

Honest framing: one iteration doesn't prove the loop works. I don't know yet if it produces the understanding I'm hoping for, or if the pattern is too messy to map. It's a bet, not a solution.

---

## The Role Shift

My first instinct was: "If you join my team, I'll elevate you to where I am."

I've learned this is wrong. Not from this team — from four years of building an org to 60 people. Early in my managerial career, I spent hours on progress reviews, 1-on-1s, handholding people through their development. And at the end, the biggest factor in whether someone grew was whether they did things on their own. I could spend 30 minutes walking them through a problem, but if they waited for the next 30 minutes with me instead of working on it between sessions, nothing changed. Growth happened when people treated their career as part of the job, not as something that would improve because they spent time with their manager discussing it.

I also learned something about myself: I lose patience when people don't take initiative. That's not sustainable — not for them, and not for me. Taking ownership of someone else's growth sounds generous. In practice, it leads to frustration on both sides and dependency on one.

So: I'm not accountable for their growth. It's their career. My role is creating conditions.

But there's a scope clause I didn't see before this lesson. I don't own their growth — but I do own the disruption I'm creating. When I'm the one raising the bar, tying AI learning to performance reviews and compensation, "adequate conditions" is a higher bar than in steady state. I owe them clear expectations, real support, an honest timeline, and candid conversations early enough to matter. If a junior PM fails to make the transition, I need to be able to honestly say I gave them a fair shot.

There's a fair challenge here: did I move too fast? I've tied AI adoption to performance reviews before I can explain the path, before I've defined what support looks like, before I've even asked the team what this feels like from their side. The intellectually clean move would be to wait — understand the conversion mechanism first, build the support plan, then set the expectations.

But I've seen where waiting leads. Lesson 04 was about staying in "proving it" mode for months because it was comfortable. Waiting for full understanding before acting is the same mistake wearing different clothes. I spent six months building my own infrastructure. If I need another six months to understand it well enough to teach it, the team falls further behind, the industry moves on, and I fail everyone — the team, the company, and myself.

So the honest position is: I'm setting expectations and building understanding in parallel, not sequentially. The OKR move was acting on instinct while I figure out the theory. That's uncomfortable, but the alternative — waiting until I'm ready — is a luxury I don't have.

What I can do right now, without passing Feynman Test B:

In my next 1-on-1s, I need to make it clear that PMs can and should push back to get time to experiment. And I need them to be honest — are they truly using that time to build, or not? If they are, I'll defend them to management. If they're not, the time isn't helping.

I need to sit with each PM on their actual work — not show them my skills or my OCR eval, but help them build infrastructure for their task. Lesson 04 already told me: demos of my work produce polite nods, help with theirs produces adoption.

I need to map which PMs have Olivia-style tasks — recurring, data-dependent, with cross-team dependencies — and curate those as starter tasks for infrastructure building. Not every PM has one. For those who don't, I need to figure out whether to create one or accept that their path will be different.

And I need to ask the team what this looks like from their side. Five lessons about AI adoption and it's all been my perspective. What's working for them? What's frustrating? When they hit a wall, what do they do? Next week, I ask.

---

## What I'm Still Figuring Out

**The conversion mechanism.** What makes someone cross from using AI to building on it? Pain is necessary but not sufficient. Disposition matters but I can't name it. This is the central open question — Feynman Test B — and answering it is the prerequisite for creating the right conditions deliberately rather than by instinct.

**Can you find pain points for people, or do they find their own?** Olivia's SEO task was assigned. The data lead found his own project. Both paths led to infrastructure, but one was managed and the other was self-directed. I don't know which is more durable.

**Does this scale?** If adoption is driven by individual pain points, dependency structures, and something about disposition, it's inherently personal. You can't mass-deploy it. That might mean the leader's job is one-on-one — finding each person's forcing function. That's expensive.

**The performance question is now urgent, not theoretical.** I've tied AI to compensation. I can't explain the path. If someone fails to make the transition, can I honestly say I gave them a fair shot? Right now, I'm not sure. Defining what "fair shot" means — concretely, not philosophically — is something I need to do before the next review cycle, not after.

---

## The Lesson

I set the expectations from lesson 04. Moved OKRs to GitHub, tied AI learning to performance reviews, told the team this is the direction. It worked — sort of. Everyone used Claude Code for OKRs. Nobody self-initiated beyond that. The team is using AI, but as a chatbot. Give them credit, but be honest about the gap.

The gap between "using AI" and "using AI well" is invisible infrastructure — months of accumulated layers that make each session smarter than the last. I couldn't see the gap because I was standing on it.

The tasks that force infrastructure are the ones with dependencies — cross-team data, pipeline setup, coordination that chatbots can't brute-force. Olivia's monthly SEO reports required data from another team. That dependency made building infrastructure worth the investment. Self-contained tasks let you stay in chatbot mode forever.

Then the Feynman test caught me. I can explain what I built. I can't explain what makes someone cross from using AI to building on it. Obsession isn't a method, and I can't hand someone mine.

I moved fast on accountability — maybe too fast. I tied adoption to compensation before I could explain the path or define the support plan. The clean move would be to wait. But waiting is the lesson 04 mistake in a new outfit: choosing intellectual comfort over action while the industry moves on. So I'm doing both in parallel — setting expectations while building understanding — and accepting the discomfort of not having the full answer yet.

My role is creating conditions, not engineering outcomes. But I own the disruption, which means the conditions need to be real: protected time to experiment, pairing on their actual work, curated tasks with the right dependency structure, and honest conversations about what's working and what isn't.

I don't have the map yet. I'm building the tools to draw it — and next week, I'm asking the team to tell me what the terrain actually looks like from where they're standing.

---

## Raw Material & References

- Claude Code Insights (Feb 19 – Mar 21, 2026): 1,621 messages, 195 sessions, 55.9 msgs/day, 257 commits
- 5 work areas: strategic docs (~35 sessions), git workflows (~29), skills/agents (~22), OKR (~20), OCR eval (~18)
- Olivia's demo output: `shop-global.html` — full React app with brand guidelines, bilingual, Recharts, animations
- Olivia's adoption path: forced monthly SEO reports (requiring data team dependency) → built skills → now produces demos independently. Confirmed in conversation: SEO pain was the driver. Key insight: the cross-team data dependency made infrastructure necessary, not just convenient.
- OKR structure: departmental OKR + individual guidance as .md files in GitHub
- Team status post-expectations: using Claude Code for OKR (verified via .md output), only Olivia has non-OKR PRs, demos built on POE (chatbot), AI learning tasks in OKRs
- Infrastructure layers (author's journey): CLAUDE.md → brand guidelines → skills → team agents → meta-improvement loops. Timeline: months, each layer unknown duration (not tracked at the time).
- Weekly learning loop: started week of 2026-03-21. Observe (GitHub + Slack + insights) → reflect → scope → specify → execute → validate → codify. Produces new rules, skills, hooks weekly. One iteration completed; too early to assess.
- Feynman principle: "If you can't explain something simply, you don't understand it well enough." Two tests — Test A (explain the system) passes; Test B (explain the conversion from using to building) fails. Test B is the key question.
- Leadership principle: "Create conditions, not outcomes. Their growth is their career." Tested over 4 years building org to 60 people. Scope clause: when imposing disruption, "adequate conditions" is a higher bar — includes clear expectations, real support, honest timeline.
- METR study (2025): experienced developers 19% slower with AI tools. Raw practice hours don't compound without workflow redesign.
- Lesson 04 connection: set expectations (done), team responded OK. This lesson: discovered the infrastructure gap underneath the adoption gap, and the Feynman gap underneath that.
- Next actions: (1) ask team members what AI adoption feels like from their side, (2) map which team tasks have dependency structures that make infrastructure necessary, (3) continue weekly loop to trace frustration → infrastructure patterns.
