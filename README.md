```
██████╗ ███╗   ███╗ █████╗ ██╗  ██╗
██╔══██╗████╗ ████║██╔══██╗╚██╗██╔╝
██████╔╝██╔████╔██║███████║ ╚███╔╝
██╔══██╗██║╚██╔╝██║██╔══██║ ██╔██╗
██████╔╝██║ ╚═╝ ██║██║  ██║██╔╝ ██╗
╚═════╝ ╚═╝     ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝

     a health-focused LLM, built in the open,
     never to be sold.
```

# bmax-core

BMax is a research artifact: a language model fine-tuned on health literature, published for reproducibility, with no medical claims and no warranty. It runs locally. It is not a product. It will never be a product.

This repository is, today, a manifesto and a call for contributors. There is no model yet. There is a direction, a set of commitments, and a seat at the table for people who want to help build it.

---

## why this exists

The frontier models are already extraordinary at medical reasoning — far better than most published critiques acknowledge, because those critiques keep benchmarking models that are eighteen months stale. That is a kind of malpractice in itself. The models still need careful supervision; they skip steps, they jump to conclusions, they need re-steering. But used well, they are a different species of tool than what was available two years ago.

And yet none of them are built for this. The good ones are general-purpose, trained cautiously, aligned toward refusal on anything that smells clinical. The health-specific ones are either locked behind hospital APIs or built by companies with an exit in mind.

BMax is the other path. A model fine-tuned for health reasoning, released as a research artifact, owned by no one, sold by no one, improved by whoever shows up — and guarded by someone with no incentive to sell out.

---

## the long vision

Most open projects drift. They start idealistic, attract capital, get captured. The founder takes a board seat somewhere, the license quietly shifts, the mission statement gets rewritten in the third year. Health tooling drifts faster than most, because the money in health is enormous and patient.

BMax is being built to resist that specifically.

```
  ┌────────────────────────────────────────────────────────┐
  │  resistant to money                                    │
  │  → no commercial license, ever                         │
  │  → no contributors paid, so no one can be bought       │
  │  → no funding round, no tokens, no "sustainable        │
  │    business model" pivot in year three                 │
  │                                                        │
  │  resistant to pressure                                 │
  │  → no institutional dependencies                       │
  │  → no hosting provider holding the keys                │
  │  → decentralized by nature — if one node falls,        │
  │    the weights are already on ten thousand machines    │
  │                                                        │
  │  a gift, not a product                                 │
  │  → health is too precious to treat as a market         │
  │  → the long bet: if BMax becomes useful enough         │
  │    for real people, it creates societal pressure       │
  │    on a system that has earned some                    │
  └────────────────────────────────────────────────────────┘
```

That last point is the long game, and we are honest that it is a long game. Today BMax is for technical users only. If — *if* — the project reaches a point where a non-technical person could meaningfully use it, the existence of a free, local, uncapturable health reasoning tool is the kind of fact that reshapes the conversation around what health tooling *should* cost and *should* look like. We are not promising that day arrives. We are building so it could.

---

## governance: a dictatorship, stated plainly

BMax is run as a benevolent dictatorship. One person — Oussama Ammar — decides who contributes, what gets merged, and what the project is about. There is no committee, no DAO, no voting. There will not be.

This is not hidden and it is not negotiable. It is the structure, and the structure is the point.

```
  why a dictatorship?
  ──────────────────

  ▸ corpus curation needs a single editorial voice.
    health content with no curator becomes a supplement forum.

  ▸ committees drift. a single person with a stated mission
    and no paycheck on the line is harder to move.

  ▸ consensus-driven open source projects in contested
    domains get captured by whoever shows up most.
    that is not a filter for quality.

  ▸ the fork is the release valve. if you disagree with
    a decision, the license permits you to take the whole
    thing and run it your way. that right is real and
    intentional. it is the honest version of democracy
    in open source.
```

Nobody is paid. Not the dictator, not the contributors, not the translators, not the reviewers. This is deliberate. The moment someone draws a salary, the project has a stakeholder with an interest in the project's continuation beyond the project's usefulness. BMax should exist for exactly as long as it is useful and not one day longer.

If you need to be paid for your time — and that is a perfectly reasonable thing to need — this is not the project for you, and no offense is taken.

---

## what BMax is and is not

```
┌─────────────────────────────────────────────────────────┐
│  BMax IS                                                │
│  → a research artifact                                  │
│  → a local-first tool for technical users               │
│  → an experiment in open health reasoning               │
│  → a curated synthesis across medical traditions        │
│                                                         │
│  BMax IS NOT                                            │
│  → a medical device                                     │
│  → a diagnostic tool                                    │
│  → a replacement for a clinician                        │
│  → a commercial product, now or ever                    │
└─────────────────────────────────────────────────────────┘
```

BMax does not diagnose. It does not prescribe. It does not treat. It reasons over literature and helps a technically capable user think. The user is responsible for what they do with that reasoning. If you are not comfortable with that framing, this project is not for you — and that is fine.

---

## the corpus: why this is the hard part

The fine-tune is the easy part. The corpus is the project.

Most health-focused models are trained on a narrow slice of the literature: English-language peer-reviewed journals, mostly American and Western European, mostly from the last two decades, mostly filtered through the assumptions of pharma-funded research. That slice is excellent. It is also incomplete.

BMax aims to build a broader synthesis, deliberately and carefully, across:

```
  ┌── Western peer-reviewed medical literature
  │
  ├── Russian clinical and pharmacological research
  │     (an enormous body of work, largely untranslated,
  │      with strong traditions in adaptogens, peptides,
  │      and rehabilitation medicine)
  │
  ├── Chinese medical research
  │     (both modern clinical work and the classical
  │      TCM corpus, treated as distinct epistemic sources)
  │
  ├── Functional and integrative medicine literature
  │
  ├── Genetics, epigenetics, nutrigenomics
  │
  ├── Peptide research
  │     (clinical literature, not gray-market forums)
  │
  └── Ancestral and traditional health practices
        (where documented and studied)
```

These sources are not epistemically equivalent, and BMax will not pretend they are. A randomized controlled trial and a classical TCM text are both useful inputs to a reasoning system, but they carry different weights and different kinds of evidence. Part of what this project has to figure out is how to encode that distinction into the model's outputs — so that BMax, when it draws on TCM or on a Russian peptide study, says so, and says what kind of evidence it is drawing on.

This is a research problem. We do not have the answer yet. Anyone who tells you they do is selling something.

### the methodology we are working toward

```
  [1] source acquisition    → what goes in, where from, licensing
  [2] quality stratification → evidence tiering, not filtering
  [3] translation pipeline   → RU/ZH/other → EN, with provenance
  [4] provenance preservation → every claim traceable to source
  [5] red-team review        → clinicians, researchers, skeptics
  [6] reasoning scaffolds    → force the model to show its work
  [7] eval harness           → how do we even measure "good"
```

Every one of these steps is an open problem. Every one of them is a place a contributor can own a piece.

---

## architecture (early thinking, open to argument)

```
   ┌──────────────────────────────────────┐
   │  local web UI  (fork Open WebUI or   │
   │  similar — not rebuilding this)      │
   └────────────────┬─────────────────────┘
                    │
   ┌────────────────▼─────────────────────┐
   │  inference layer  (llama.cpp /       │
   │  Ollama / vLLM — user's choice)      │
   └────────────────┬─────────────────────┘
                    │
   ┌────────────────▼─────────────────────┐
   │  bmax model weights  (fine-tuned     │
   │  on permissively-licensed base)      │
   └────────────────┬─────────────────────┘
                    │
   ┌────────────────▼─────────────────────┐
   │  dedicated local filesystem          │
   │  (user's corpus, notes, sessions —   │
   │  never leaves the machine)           │
   └──────────────────────────────────────┘
```

Local-first, no telemetry, no cloud. If you want to run it on a server you rent, that is your business, and the license permits it as long as you are not selling access.

---

## licensing

```
  ┌───────────────────────────────────────────────────────┐
  │  CODE     →  AGPL-3.0                                 │
  │  WEIGHTS  →  OpenRAIL-M  +  PolyForm Noncommercial    │
  └───────────────────────────────────────────────────────┘
```

Strictly speaking this makes BMax **source-available**, not "open source" by the OSI definition, because we forbid commercial use. We are being honest about that. The intent is clear:

- anyone can read it, fork it, modify it, run it
- anyone can contribute to it
- no one can sell it, wrap it in a paid service, or use it to make money
- derivatives must remain under the same terms

### on enforcement

The license is not decoration. Everything here is published so the world can read it, run it, improve it, and fork it. None of it is published so someone can wrap it in a SaaS and charge for it.

If you use BMax commercially, we will pursue it. Not as a threat — as a fact. The project has no revenue to protect, which means the cost of enforcement is a question of principle rather than economics, and on this principle there is no flexibility. Commercial users should assume they will be found and they will be contested.

Some things are better when no one has an incentive to profit from them. This is one of them.

---

## who we are looking for

Everyone, honestly. But concretely, the project needs:

```
  ▸ ML engineers          fine-tuning infra, evals, inference
  ▸ data curators         corpus building, source vetting
  ▸ translators           RU → EN, ZH → EN (medical literature)
  ▸ clinicians & MDs      red-teaming outputs, reality checks
  ▸ researchers           geneticists, pharmacologists, TCM scholars
  ▸ frontend devs         local app shell, UX for technical users
  ▸ writers & editors     documentation, methodology papers
  ▸ skeptics              people who will tell us we are wrong
```

That last one matters as much as any of the others. A project like this fails quietly if no one is willing to push back.

No contributor is paid. Contribution is its own reward or it is not for you. Being named in the project's history as one of the people who built this is a real thing, and for some people it is enough. For others it is not, and that is fine.

---

## contributing

There is no code yet. What there is: this README, a direction, and an inbox.

If you want in, write to **hi@oussamaammar.com** with:

- who you are
- what you would want to work on
- anything you have built or written that is relevant

Short is fine. Long is fine. What is not fine is a generic LinkedIn-flavored pitch. Tell me what you actually want to do.

Not everyone who writes will get in. This is not a rejection of you; it is a filter for the project. If it is not a fit, fork the repo when there is one to fork and build the version you want.

---

## a note on who this is for

Today, BMax is for technically capable users who can run a local model, read a README, and think critically about output. It is not for a general audience. It may never be. The project does not owe anyone a friendly onramp, and pretending otherwise is how health tools hurt people.

If you are technical, curious, and willing to treat a language model as a tool rather than an oracle — welcome.

---

## disclaimer

BMax is a research artifact. It does not provide medical advice. It is not a medical device. It is not intended to diagnose, treat, cure, or prevent any disease. It is provided without warranty of any kind. Use at your own risk. Consult a qualified healthcare professional for medical concerns.

---

```
     contact   →  hi@oussamaammar.com
     license   →  AGPL-3.0  /  OpenRAIL-M  +  PolyForm NC
     status    →  pre-alpha, manifesto stage
     governed  →  BDFL, Oussama Ammar
```
