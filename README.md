# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->



---

## Community Pick and Candidate Distinctions

**Community:**
Nintendo Switch 2 gaming subreddit (Public)

**Candidate Distinction 1:**
Concrete detail vs. general impression – Some posts name something checkable, such as a game title with a specific setting, a frame rate, a price, a firmware version, a storage figure, or an attached screenshot or link. Others stay at the level of "it runs great" or "the screen looks nice." You can point at the detail, or at its absence.

**Candidate Distinction 2:**
A claim with a reason vs. reaction/annoucement – Some posts state a position and give a "because" ("handheld mode is worth it for X, since Y"). Others only express a feeling ("so hyped!!") or relay a fact ("new trailer dropped") with no argument attached. This works well in the Discussion category, where the range between the two is probably widest.

**Candidate Distinction 3:**
Self-contained vs. dependent on the reader to fill gaps – Some posts supply their own context: what the person already tried, what they're comparing against, what they're trying to decide. Others make you guess ("Is it worth it?" with no budget, no games, no comparison). This should matter most in Question posts, where a self-contained post is much easier to answer well. 

--- 

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### `label_one`

**Definition:**
Question – The poster lacks information or experience and is asking the community to supply it, so a natural reply answers.

**Example 1:**
>How was your experience with competitive games on Switch 2? (Rocket League, EA FC)

​Hi everyone,

​I’ve been a huge fan of the Switch from afar since 2017, even though I’ve never owned one myself. Lately, I’ve been researching options for a portable gaming setup to take with me during my studies for dorm room gaming. Among options like laptops and other consoles, the Switch 2 caught my eye with its amazing next-gen design.

​My gaming preferences mostly revolves around popular online competitive games that are fun both solo and with friends. I especially love Rocket League and EA FC.

​Other consoles are not only bulky themselves, but they also require a dedicated monitor, controller, and a bunch of extra accessories. The idea of playing my two favorite games natively in handheld mode on the Switch 2 sounds incredibly exciting!

​I know the Switch 2 has an amazing library of exclusive games offering a wide variety of experiences, but I’m really curious about how it performs for competitive games:

○ ​Handheld Experience & Ergonomics: Does playing in handheld mode get tiring or uncomfortable during long sessions? Do you run into issues like overheating or clumsy button layouts (e.g., fingers slipping or missed inputs)? If so, how do you fix them (grips, accessories, etc.)?

○ ​Handheld vs. Docked: Do you prefer playing competitive games handheld, or do you find yourself needing to dock it to a screen?

○ ​Overall Recommendation: Would you recommend the Switch 2 specifically for playing these types of competitive games under these conditions?

​From the gameplay videos I've seen, the graphical performance looks great and games seem to run super smoothly. I’d love to hear your personal experiences, tips, and honest thoughts!

​Thanks in advance, everyone!

P.S. Sorry if this is a frequently asked question, just wanted to get some direct input from the community!

**Example 2:**
>Why did Nintendo Store reduce the price of my pre-order?

So this was the pre-order prepayment processing email for my copy of the game, I bought the bundle, which includes the Ocarina Pin that totalled £61.98 and came with the spiritual stones as a bonus.

This email doesn't show the Ocarina pin, but even if that wasn't there due to being out of stock, the cost of the physical version should still be £58.99. Instead, it shows a total of £50.79.

Any ideas or anyone have the same thing happen?

### `label_two`

**Definition:**
Recommendation – The poster advises a choice or action based on judgment or preference, so a natural reply agrees or disagrees. 

**Example 1:**
>Any games you'd add or swap?

Heya guys! I'm getting a Switch 2 at the end of October, and these are my thoughts for what I should get as a lineup to last me till new year (at least)! Any you think I'm particularly missing? Or any here you'd get rid of? :))

**Example 2:**
>Animal Crossing or Fantasy life i?

Hello! I want to buy one of these. I tried with Pokopia, it is nice, but not for me, even if I like farming. I did a lot in TOTK. I sold Pokopia and now I want to get one of these. What do you recommend? Thanks!

### 'label_three'

**Definition:**
Analysis – The poster reports a finding or explanation whose central claim can be verified against something concrete, which ranges from a screenshot, a video, or a stat, so a natural reply checks or confirms it.

**Example 1:**
>The Legend of Zelda: Ocarina of Time Commercial-Gameplay: Battle Scene [ENG SUB]


**Example 2:**
>Witcher 3 Remastered, patch improved image quality.

Left is before patch 5.03 and right is with 5.03.

Sharpness is increased and they have added extra settings in the menu.

### The hardest boundary

**Which two labels:**
Question and Recommendation


**The decision rule I used every time:**
<!-- e.g. "If the post names a specific checkable fact, it's `analysis`, even
     if the tone is heated." -->
If the post names two or more specific options being weighed against each other, it’s recommendation, even if it is phrased as a question.

---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->

**Where the posts came from:**

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

**Counts per label:**

| Label | Count | Share |
|---|---|---|
|  |  |  |
|  |  |  |
|  |  |  |
| **Total** |  | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

**2.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

**3.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:**

**Settings:** <!-- epochs, learning rate, batch size, seed -->

**Anything I changed from the defaults, and why:**

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->



---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- *What I asked for:*
- *What came back:*
- *What I changed:*

**Moment 2**

- *What I asked for:*
- *What came back:*
- *What I changed:*

**Pre-labelling disclosure:**

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy |  |  |  |
| Macro F1 |  |  |  |
| F1 — `label_one` |  |  |  |
| F1 — `label_two` |  |  |  |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->



---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted |  |  |  |
|---|---|---|---|
| **** |  |  |  |
| **** |  |  |  |
| **** |  |  |  |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->



---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->



---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** ___ / 30 = ___%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**2.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**What the pattern in my disagreements tells me:**



---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->



**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->



<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
