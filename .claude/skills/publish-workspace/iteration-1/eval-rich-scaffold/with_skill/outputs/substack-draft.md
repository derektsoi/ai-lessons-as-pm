# A Working Demo Doesn't Let You Be Vague

*What happens to product development when the PM stops writing specs and starts building evidence.*

---

Here's how product development used to work at my company: management has an idea. A PM writes a PRD in a format the boss won't read. Everyone discusses it anyway — ineffectively. Designers and engineers aren't involved until later. By the time the idea becomes concrete enough for anyone to react to, weeks have passed. And about half the time, we only caught the misalignment when we had a finished design. Sometimes it was a disaster.

I changed this by building demos with Claude Code. Not polished prototypes — working demos grounded in real API calls, real data, real edge cases. The lesson I learned wasn't "AI makes PMs faster." It's that a concrete demo compresses decisions — and removes the safety net I didn't know I was relying on.

---

## I didn't set out to change how I write specs

I was building a demo for a Pokemon card shopping agent — scripting conversations that showed how a user would find and buy a Japanese Charizard card through our chatbot. Somewhere in the middle of that, I realized I wasn't writing a demo anymore. I was writing the spec.

The 13 Golden Conversations I scripted aren't a presentation. Each one defines exactly how the product should behave — what the user says, what the agent responds, what data it pulls, from which API, in what order. They're acceptance tests that happen to be readable by a COO. I think of them like TDD for LLM products: you can't spec LLM behavior declaratively ("be helpful but concise" means nothing), but you can show what good looks like through a concrete example.

The spec and the demo co-evolved. Every time I built a conversation, I'd test the real APIs through Claude Code and discover something the spec needed to say. Every time I updated the spec, it changed the demo. I wasn't writing a requirements doc, handing it off, and waiting. I was doing both at once, and each one made the other better.

---

## What Claude Code actually does here

Claude Code handles the mechanical parts — browsing API documentation, calling endpoints, handling authentication. I don't need to know Postman. What I bring is product judgment about what to test and what matters.

I discovered that all the Pokemon APIs use different card identification standards. The price API has one standard, the card catalog has another, the photo recognition returns a third. This meant the architecture needed a middle LLM layer to translate between them. I found this before any engineer touched the project.

The sequence diagrams I built aren't engineering deliverables — they're thinking tools. Whether EN vs JP card identification is a phase-1 problem (identify the card) or a phase-2 problem (choose the price) changed how we call APIs and what information the LLM has at each stage. That decision came from thinking through the diagram and testing the APIs at the same time.

---

## This isn't specific to AI products

The merchant pinning project made this even clearer. A marketer pins a merchant to the homepage — sounds simple. I started building the demo thinking it was. Then I saw the HTML output and realized: what happens when a marketer pins a merchant that's already ranked #3? What about pinned merchants that conflict with the data-driven ranking? What about multiple marketers pinning different merchants?

I wrote 15 test cases before sharing anything with engineers. Each one set up mock merchant data to show how the logic would handle a specific scenario. I wouldn't have written those test cases from a blank PRD — I didn't even know the edge cases existed until the demo forced me to confront them.

---

## Decision compression

This is what I mean by decision compression. It's not about speed. I actually did more work, not less — thousands of lines of spec, 13 scripted conversations, 5 tech spikes, sequence diagrams. The total output is denser than any PRD I've written.

But decisions that used to take 4-10 weeks of back-and-forth happened in the first few sessions. When the COO asks "can it do X?" — the answer is based on an API call I already made, not a guess. The stakeholders are reacting to real output, not wireframes of idealized flows. Their feedback is grounded too — they can't say "make it smarter," they have to point to a specific conversation and say "this answer is wrong because X."

A PRD can say "marketers can pin merchants to the homepage" and everyone nods. A demo has to answer: what actually happens when they do?

---

## The risk I didn't expect

In the old workflow, my product judgment got applied gradually over 4-10 weeks. I'd make a decision, see it interpreted by a designer, react, adjust, see it built by an engineer, react again. The slow iteration was a safety net — my judgment didn't need to be sharp upfront because there were many correction points.

Now I jump almost to the end. The demo is concrete. The spec is detailed. The API contracts are tested. By the time anyone else sees it, I've already made dozens of product decisions baked into the golden conversations. If my judgment is wrong, it's wrong at scale — and it looks authoritative because it's grounded in real data.

I also said I don't need to understand API authentication or Postman. That's true for mechanical details. But I'm now building specs and sequence diagrams that engineers implement. The line between "technical details I can safely skip" (auth plumbing, request formatting) and "technical understanding I need" (how APIs behave under load, error conditions, pagination at scale) is real, and I haven't drawn it carefully enough. What I validated: this API returns this data in this format when called this way. What I assumed: this will work at scale, under error conditions, with production authentication.

---

## Where this works — and where it probably doesn't

I've done this on two projects. That's not a general method. So I'll be honest about the boundaries I can see.

It works when you have external APIs with discoverable behavior you can actually test. When stakeholders respond to visual or interactive demos. When the PM has deep domain context — because judgment about what to test needs to be calibrated, and the output will look authoritative regardless.

It might not work for internal system behavior you can't probe from the outside. For incremental improvements where a PRD might genuinely be faster. For a PM who's new to the domain — because the demo will still look grounded even if the judgment behind it is wrong. I haven't had it fail yet, and that's exactly why these boundaries are theoretical.

---

## What I'm still figuring out

I didn't save time — I compressed decisions. I spent more PM time upfront, but the COO conversation was productive because I had real answers, and the PRD became a by-product of thinking I'd already done. Whether that's a good trade depends on whether the upfront thinking was right.

The old safety net of slow iteration is gone. I don't have a replacement yet.

And the honest answer to "are you doing this because it produces better decisions or because you like building?" is both. That's fine — but I should be honest about which one drives me on any given day, because "I enjoy this" is not the same as "this is the right use of PM time."

---

*Derek is a PM based in Hong Kong. This is the first in a series about what he's learning building with AI.*
