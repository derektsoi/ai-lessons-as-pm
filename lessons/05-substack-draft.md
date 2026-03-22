# I Couldn't See the Gap Because I Was Standing on It

*What months of building AI infrastructure taught me about why my team can't follow*

---

Every PM on my team now has an AI learning OKR. It affects their performance review — salary and bonus. I moved our OKR planning to GitHub as markdown files, which meant they had to use Claude Code to work on them. The team responded well. No pushback. AI learning tasks in everyone's goals.

Then I checked the pull requests. Only one PM had submitted anything outside of OKR work. Everyone else used Claude Code exactly when required and never again. That's not adoption. That's compliance. And the gap between the two is larger — and harder to see — than I expected.

---

## The Honest Check

They're not doing nothing. That's what makes this hard to see.

Everyone used Claude Code for OKRs — I know because all their output is in markdown format. Nobody is drafting in a chatbot and downloading it back to GitHub just to comply. And the team IS using AI: I can see them building demos on chatbots like POE. Give them credit. They're engaging with AI tools. But it's chatbot-level usage — no company context, no design guidelines, no accumulated knowledge, starting from zero each session.

One PM — O — has pull requests for non-OKR work. She's producing full interactive prototypes independently. Everyone else submits only when they're doing OKRs. The expectation-setting didn't create her adoption. It just confirmed it.

---

## The Infrastructure Gap

The gap between "using AI" and "using AI well" isn't about features or willingness. It's about accumulated infrastructure.

Over months, I kept adding layers to my Claude Code environment — company context files, brand guidelines, automated review patterns, agent teams that challenge work from multiple angles. Each layer took weeks to build. Each one made the next session smarter than the last.

The compound effect only shows up when you need it. A simple demo? A chatbot can handle that. But a UAT report for an OCR vendor evaluation — one that requires processing hundreds of images, cross-referencing two vendors' results, creating ground truth labels, embedding failure examples into the report, then drafting a message to management? That's five tools working in sequence, each one inheriting context from the last. The infrastructure is what makes the task possible, not just faster.

Then I watched one of my PMs building a demo by chatting with an AI. No test cases defined upfront. No clear end goal. Just conversing with the chatbot and hoping the output would converge on something useful. And I realized: that's how chatbots work. You chat and hope. The infrastructure approach is fundamentally different — you define what "done" looks like, let the agent work, then verify the output against your criteria. My PMs weren't just using a simpler tool. They had a completely different mental model for how AI should work. They were very far from the agentic approach with verification loops, and they didn't know what they were missing.

I couldn't see this gap because I was standing on it. I'd built the penthouse floor by floor over months. From up there, the view was obvious. From the ground, there's no skyline — just a tool that seems like a fancier chatbot.

---

## The O Evidence

O didn't adopt because of a feature demo or a vision speech. She had a monthly SEO report.

At the start, this meant manually pulling data from the data team's tables, assembling the numbers, writing the analysis. Same task every month, same metrics, same tedium. Now she runs a command and Claude generates a full visual report — branded charts, region-by-region breakdowns, trend lines the team can hover over to see specific numbers. The infrastructure she built didn't just save time. It made the output better than what she could produce manually.

Here's what makes the SEO report different from other PMs' recurring work: it has consistent metrics and a cross-team data dependency. O tracks the same numbers every month — sessions, rankings, click-through rates by region. And the data comes from the data team's pipeline, not from something she can pull up in a browser. That combination — stable metrics plus external dependency — made infrastructure worth building. You can automate what repeats and connects to other systems. You can't automate what changes every time.

Other PMs have monthly reports too. But their work is new feature analysis — different data, different questions, different stakeholders each cycle. There's no stable foundation to build on. It's not that they lack the pain. It's that the structure of their tasks doesn't reward the investment.

---

## The Feynman Test

Richard Feynman said if you can't explain something simply, you don't understand it well enough. He just caught me.

There are two versions of this test, and I pass one and fail the other.

Test A: can I explain what I built? Yes. Each layer does something specific — configuration files give Claude company context, skills automate repeated review patterns, agent teams challenge work from multiple angles, hooks enforce quality gates. I can walk anyone through the system. I pass this test.

Test B: can I explain what makes someone cross from using AI to building on it? No. And it's worse than I initially thought. I don't just fail this at the macro level — I can't even explain my own progression between layers. When should a PM move from writing a configuration file to building automated skills? When do quality hooks become worth the setup cost? I have no idea. I brute-forced it. I tried everything, kept what worked, and moved on. That only worked because I have the obsession to try everything.

Obsession isn't a method. I can't hand someone my obsession and say "now go build infrastructure." But that's essentially what I've been doing — showing the result of obsessive experimentation and wondering why people don't replicate it.

Test A is about the system. Test B is about the transformation. My team doesn't need a feature tour — they need me to understand the conversion mechanism so I can create the right conditions. And right now, the honest answer is: I don't understand it. I built something powerful through brute force and intensity, and I can't trace the path well enough to guide someone else down it.

---

## The Bet

I own this disruption. I tied AI adoption to performance reviews before I could explain the path. Before I could define what support looks like. Before I could even answer Feynman Test B.

The clean move would be to wait — understand the conversion mechanism first, build the support plan, then set the expectations. But waiting is the mistake I made before: staying in "proving it" mode for months because it was comfortable. I spent six months building my own infrastructure. If I need another six months to understand it before I act, the team falls further behind and the industry moves on.

So I'm doing both in parallel. Setting expectations and building understanding at the same time. That's uncomfortable, and it should be — because the alternative is choosing intellectual comfort over action.

I've started a weekly improvement loop to trace my own process — tracking what frustrated me, what I built in response, and whether it helped. The first iteration already caught something I would have missed: Claude fabricating business logic is a recurring problem, and my existing safeguards weren't catching it. Fabricated product names that passed through all three debate agents undetected. A fake contract clause cited in a vendor review. Multi-agent review — the infrastructure I was proudest of — didn't catch fabrications. It amplified them. The loop identified the pattern and produced a fix. One iteration doesn't prove it works. But it's the beginning of the map I need to eventually pass Test B. And next week, I'm having conversations with the team I should have had months ago: what does AI adoption look like from their side? Five lessons in, it's all been my perspective.

---

I still can't answer Feynman Test B. I don't know what makes someone cross from using AI to building on it. Pain is necessary but not sufficient. Disposition matters but I can't name it.

What I do know is that I've tied AI adoption to compensation before I can explain the path. If a junior PM fails to make the transition in the next review cycle, I need to be able to honestly say I gave them a fair shot. Right now, I'm not sure I can.

So next week: I sit with each PM and ask what AI adoption looks like from their side — not what I assume, what they actually experience. I map which tasks have the dependency structures that make infrastructure worth building. I make it clear they can push back for time to experiment — and I need them to be honest about whether they're actually using it. If they are, I'll defend them to management. If not, the time isn't helping.

That's what "fair shot" looks like in practice — not a philosophy, but a list of things I owe them before the next review cycle.

---

*I'm a PM based in Hong Kong, building with AI tools and writing about what I actually learn — not what sounds good in a LinkedIn post. This is lesson five in an ongoing series.*
