# /draft — "The Problem This Solves"

## Section Under Review

From the lesson file, here are the current bullets:

> - Old workflow: PM waits for vague idea from management. Writes PRD in a format boss won't read. Discusses with boss — ineffective. Designers and engineers not involved at all.
> - The PRD is theater. It serves a bureaucratic function, not a thinking function.
> - By the time the idea becomes concrete enough to react to, weeks have passed.
>
> **Think through:** What specifically made the old workflow ineffective? Was it the format (document), the timing (too late), the abstraction (too vague), or the people (wrong audience)?

---

## Questions I'd Ask Before Drafting

The scaffold's own "Think through" prompt is good — it asks whether the problem was format, timing, abstraction, or audience. But the rest of the lesson actually answers this in scattered places. Before writing prose, I'd want to nail down three things:

**1. What did "discusses with boss — ineffective" actually look like?**

Later in the lesson, you describe the old workflow more concretely: "decisions took 4-10 weeks to surface. A PM writes a spec based on assumptions. A designer interprets it. An engineer starts building and discovers the API doesn't work that way." And: "We only caught misalignment with the COO when we had a finished design — and not every product even got a design critique session with the COO. I'd say 50% of the time we got it wrong."

So the ineffectiveness wasn't just "boss doesn't read the PRD." It was that the PRD was too abstract for anyone to react to meaningfully. The COO couldn't say "this is wrong" because there was nothing concrete enough to be wrong. Is that right? Or was it more that the COO simply didn't engage with documents at all?

**2. "The PRD is theater" — is this your conclusion about PRDs in general, or about PRDs in your specific context?**

You write later: "Incremental improvements to existing features — a PRD might actually be faster." So you don't think PRDs are always theater. The problem was specifically using a PRD as the primary thinking artifact for complex or greenfield features where the unknowns are high. Can you draw that line sharper here?

**3. "By the time the idea becomes concrete enough to react to, weeks have passed" — what happened during those weeks?**

The lesson mentions 4-10 weeks later in the "Why this matters" sub-section. But in the opening section, you're setting up the problem. What were you actually doing during those weeks? Were you writing and revising the PRD? Were you waiting for design? Were you in meetings debating abstractions? The specific waste matters for framing the problem.

---

## Suggested Prose (Based on Context from the Rest of the Lesson)

Since the author isn't available to answer, here's a draft inferred from what the lesson says elsewhere. Every claim here traces to something already in the file — nothing invented.

---

Here's how product development used to work for me. Management had a vague idea. I wrote a PRD — a document my boss wouldn't read in the format I wrote it, and my designers and engineers weren't part of the conversation yet. Then I'd discuss the idea with my boss, but the discussion was ineffective because we were reacting to abstractions, not to anything concrete.

The PRD served a bureaucratic function. It existed so we could say "there's a spec." But it wasn't a thinking tool. You can write "marketers can pin merchants to the homepage" in a PRD and everyone nods — because there's nothing concrete enough to disagree with. The hard questions — what happens when a pinned merchant conflicts with the data-driven ranking? what about multiple marketers pinning different merchants? — don't surface until someone tries to build it.

By the time the idea became concrete enough for anyone to react to meaningfully, 4-10 weeks had passed. A designer had interpreted my spec. An engineer had started building and discovered the API didn't work that way. It escalated back. We only caught misalignment with the COO when we had a finished design — and not every product even got a design critique session with the COO. I'd say 50% of the time we got it wrong and had to adjust last minute.

The problem wasn't that PRDs are bad. For incremental work, a PRD is fine. The problem was using a document full of assumptions as the primary artifact for complex features — and then waiting weeks to discover those assumptions were wrong.

---

## Flags

- **"A document my boss wouldn't read in the format I wrote it"** — this is directly from the bullets but I'd push on it. Is this literally true? Did the COO never read PRDs? Or did he read them but couldn't give useful feedback because the format was too abstract? The distinction matters.

- **The merchant pinning example** — I pulled it from the "Core Insight" section to illustrate "nothing concrete enough to disagree with." It works well here as a setup, but check whether using it here undercuts its impact later in the lesson. You may want to save it.

- **"50% of the time we got it wrong"** — This is a strong claim that appears in the "Why this matters" sub-section of "Core Insight." Pulling it into the opening problem statement makes the stakes clear immediately. But if you use it here, you may want to cut or rephrase it there to avoid repetition.

- **Last paragraph ("The problem wasn't that PRDs are bad")** — This is me drawing a line that you draw implicitly later ("Incremental improvements — a PRD might actually be faster") but never state in the problem section. If it's too concessive for the opening, cut it. But leaving it might strengthen the whole piece — it shows you're not making a blanket anti-PRD argument, which makes the rest more credible.

## Does This Sound Like You?

Read the draft aloud. Two sentences I'm least sure about:

1. "The PRD served a bureaucratic function" — this is your exact phrasing from the bullets, but in prose it might sound more dismissive than you mean. You could soften to "The PRD served a process function" or sharpen to "The PRD existed to check a box." Depends on how much heat you want.

2. "The problem was using a document full of assumptions as the primary artifact for complex features" — this is my synthesis, not your words. Does it match what you actually think, or am I over-rationalizing? The raw bullet ("The PRD is theater") is angrier and maybe more honest.
