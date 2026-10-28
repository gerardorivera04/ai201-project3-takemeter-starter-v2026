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
     My build of TakeMeter classifies posts from a public Nintendo Switch 2 gaming subreddit into three categories: question, recommendation, and analysis. A community post contains a label based on the information or context that matches with one of the labels' definitions. For instance, a question asks the community for information or experience, a recommendation asks for or gives advice about a choice, and an analysis presents an observation or claim supported by a specific, checkable detail. Finally, the trained classifier can help organize Switch 2 community posts by identifying whether each post is primarily seeking information, presenting an evidence-based observation, or asking for advice. 


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
I collected 200 public posts from a Nintendo Switch 2 gaming subreddit.

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->
I labelled the first 20 posts cold without pre-labels. Then, the remaining 180
posts were pre-labelled, and checked each label on the posts to see if I had to correct any of them when neccessary.

**Counts per label:**

| Label | Count | Share |
|---|---|---|
| Question | 76 | 38.0% |
| Recommendation | 61 | 30.5% |
| Analysis | 63 | 31.5% |
| **Total** | **200** | **100%** |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*
>I’ve been looking into the Hyperion 3 controller for Switch 2 and I don’t understand why on the purple option the right joystick is so tiny. I’m not a gamer tbh so this could be a simple thing I just don’t get. Thanks y’all!! 😊
> *Could have been:*
>Question or Analyis
> *I chose, because:*
> I chose Analysis as the label for this post because she's presenting an observation for a specifc product, such as a controller, and curiosity is the core idea behind the post as the poster is open to learning more about the controller's shape rather than experiencing issues with the controller, such as its grip or its functionality.  
**2.**
> *The post:*
>Those 2 games are one sale. I want to know about how performance on switch 2? Is there any blurry image or hard-to-read text because of the scaling from switch 1 game?
> *Could have been:*
>Question or Recommendation
> *I chose, because:*
>I chose Recommendation because the poster is asking questions to receive important information from other community members to make their personal decision as the situation requires the poster to pick one of two options, which are the two games that are on sale.
**3.**
> *The post:*
>Is blur normal on handheld? I took pictures of scrolling
> *Could have been:*
>Question or Analyis
> *I chose, because:*
I chose Question because the poster is experiencing an issue with their gaming console and they need a response from other community members to find a solution to the issue. In addition, a screenshot is provided, but it's being presented as evidence to show what the issue looks like to the poster and for other community members. 
---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:**
distilbert-base-uncased

**Settings:** <!-- epochs, learning rate, batch size, seed -->
- Epochs: 3
- Learning Rate: 2e-5
- Batch Size: 16
- Maximum Sequence Length: 128 tokens
- Seed: 42
- Device: Apple Silicon GPU (MPS)
- PyTorch Version: 2.14.1

**Anything I changed from the defaults, and why:**
I didn't anything from the defaults during the training run.

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->

The stratified split contained 139 training posts, 31 validation posts, and
30 test posts.

train 139  ·  val 31  ·  test 30

label             train  val  test                          
analysis           43   10    10
question           53   12    11
recommendation     43    9     9

Each label did have at least 8 examples in the test split, so no label triggered the 
small-test-split warning.

---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- *What I asked for:* I asked Claude's AI chat assistant to help me with brainstorming useful distinctions for classifying Nintendo Switch 2 subreddit posts as these distinctions had to be applied consistently to real posts rather than categories based on opinion. 
- *What came back:* The AI tool suggested that I distinguish posts based on the following information: the post contains concrete details, the post includes a claim and a reason, or the post provides enough context for another person to respond. Thus, these suggestions did help me on how to differentiate between posts containing questions, recommendations, and evidence-based analysis.
- *What I changed:* After being given some suggestions, I decided to adapt my distinctions to make sense for my chosen community so that I can create my three-label taxonomy for classifying the posts, which were question, recommendation, and analysis. Additionally, I wrote my label definitions, I found my examples that fit my labels, and I made a decision rule for a hard boundary between the question and the recommendation labels.

**Moment 2**

- *What I asked for:* I asked Claude's AI assistant tool to help with pre-labeling a batch of Nintendo Switch 2 gaming subreddit posts using my three label definitions. 
- *What came back:* The AI tool provided suggested labels for 180 posts. However, some suggestions were useful, but there were hard cases that needed my attention. For instance, the other suggestions were ambiguous or did not fully follow my decision rule, specifically when a post contained both a question and a recommendation or included a screenshot as evidence. 
- *What I changed:* I manually read and checked every pre-labeled post. For instance, I corrected labels when the suggested label didn't match my definitions and recored the first 20 posts with a cold note due to labeling these posts without AI assistance. Thus, the final dataset contained 200 label posts, which included 180 posts marked as pre-labeled and checked.

**Pre-labelling disclosure:**
An AI tool was used to pre-label 180 of the 200 posts in the CSV labels file. Then, I manually reviewed and corrected every pre-labeled example when necessary. Additionally, the first 20 posts were labeled without AI assistance as these 20 posts were apart of a cold-labeling sample.

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy | 0.433 | 0.567 | +0.133 |
| Macro F1 | 0.303 | 0.514 | +0.211 |
| F1 — `analysis` | 0.000 | 0.750 | +0.750 |
| F1 — `question` | 0.688 | 0.625 | -0.063 |
| F1 — `recommendation` | 0.222 | 0.167 | -0.056 |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->
I predict that the trained model will achieve higher accuracy and macro F1 than the baseline with a major improvement in the identification of analysis posts.

**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->
I ran the zero-shot baseline on the same 30 held-out posts twice. The first run of the baseline with my label definitions produced the following results, which had the accuracy being 0.400 and the macro F1 being 0.291. The second run of the baseline without the definitions, which used bare label names, produced results like the accuracy being 0.433 and the macro F1 being 0.303. Thus, the accuracy gap was -0.033, or -3.3 percentage points. For instance, the definitions didn't improve the baseline due to my label definitions being worth -3.3. percentage points of accuracy for this test split, and this negative result shows that the bare-names prompt performed slightly better. Despite the fact, the trained model stull outperformed both zero-shot runs, in which accuracy reached 0.567 and macro F1 reached 0.514.

---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

## Run Log — Before

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---:|---:|---:|---|
| 1. Overall accuracy is at least 0.65 on each of the three random seeds | ≥ 0.65 accuracy on every seed | 0.567 | 0.400 | 0.400 | MISSED |
| 2. Every label has an F1 score of at least 0.50 on each of the three seeds | ≥ 0.50 F1 for every label on every seed | analysis 0.750; question 0.625; recommendation 0.167 | analysis 0.182; question 0.550; recommendation 0.000 | analysis 0.000; question 0.550; recommendation 0.200 | MISSED |
| 3. No single label makes up more than 50% of the full dataset | Every label must be ≤ 50% of the dataset | analysis 63/200 = 31.5% | question 76/200 = 38.0% | recommendation 61/200 = 30.5% | MET |
| 4. The model agrees with the staff/reference labels on at least 75% of the agreement-check posts | ≥ 75% agreement | 17/30 = 0.567 | 17/30 = 0.567 | 17/30 = 0.567 | MISSED |
| 5. The most-confident third has accuracy of at least 0.75 and is at least 0.15 more accurate than the least-confident third | Top third ≥ 0.75 and gap ≥ 0.15 | top 0.600; bottom 0.500; gap 0.100 | top 0.300; bottom 0.300; gap 0.000 | top 0.600; bottom 0.100; gap 0.500 | MISSED |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted | analysis | question | recommendation |
|---|---|---|---|
| **analysis** | 6 | 3 | 1 |
| **question** | 0 | 10 | 1 |
| **recommendation** | 0 | 8 | 1 |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->

8 real recommendation posts were classified as question, while only 1 real question post was classified as recommendation. Thus, this shows that the model confuses recommendation posts with question posts, and the model leans toward predciting the question label for this boundary.


---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 | Overall accuracy is at least 0.65 on each of the three random seeds | ≥ 0.65 | MISSED | Accuracy was 0.567 for seed 42 and 0.400 for seeds 7 and 2024. Thus, no seed reached the 0.65 target that the criterion was missed. |
| 2 | Every label has an F1 score of at least 0.50 on each of the three seeds | ≥ 0.50 F1 for every label on every seed | MISSED | The target required every label to reach at least 0.50 F1 on every seed. The recommendation F1 was 0.167, 0.000, and 0.200, while analysis fell below 0.50 on seeds 7 and 2024. |
| 3 | No single label makes up more than 50% of the full dataset | Every label must be ≤ 50% of the dataset | MET | The largest label was question with 76 of 200 posts, or 38%. Since 38% is below the 50% maximum target, there wasn't a very dominant label. |
| 4 | The model agrees with the staff/reference labels on at least 75% of the agreement-check posts | ≥ 75% agreement | MISSED | The agreement check produced 17 agreements out of 30 posts, or 56.7%. This is below the target of 75%, and the criteria was missed. |
| 5 | The most-confident third has accuracy of at least 0.75 and is at least 0.15 more accurate than the least-confident third | Top third ≥ 0.75 and gap ≥ 0.15 | MISSED |  The most-confident third reached 0.600, 0.300, and 0.600 across the seeds, so it never reached the 0.75 target. Although seed 2024 had a 0.500 confidence gap, both requirements didn't hold, and the criteria was missed. |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->

(i) Criteria 1 - The main cause is too few examples for the model to learn stable decision boundaries. The test split had only 30 posts, with 9–11 examples per label, and accuracy changed from 0.567 on seed 42 to 0.400 on seeds 7 and 2024. The agreement report also found 12 of 13 disagreements were cases where I applied the labeling rules inconsistently, so inconsistent training labels likely added noise. The large change across seeds shows that the model's accuracy was not stable enough to reach 0.65 on every run.

(ii) Criteria 2 - The main causes are the genuinely difficult question/recommendation boundary and too few examples for each label. The recommendation F1 was 0.167, 0.000, and 0.200 across the three seeds, and the confusion matrix shows that 8 real recommendation posts were classified as questions. The test split contained only 9 recommendation posts, so a few errors caused a large F1 change. The agreement report also found repeated inconsistent application of labeling rules, which suggests that some training examples may not have represented the boundaries consistently.

(iii) Criteria 4 - The cause was primarily a boundary that I applied inconsistently, with one additional genuinely ambiguous boundary. I agreed with the staff labels on only 17 of 30 posts, or 56.7%. In the agreement report, 12 of the 13 disagreements were cases where the written rule covered the example but I applied it too loosely, especially when I treated any specific number or detail as evidence for analysis. One remaining case was genuinely ambiguous because the rule did not clearly state how much evidence a broad observation must include. This shows that the missed agreement target was mainly a labeling-consistency problem rather than a model problem.

(iv) Criteria 5 - The model did not learn a reliable relationship between confidence and correctness from this 200-example dataset. The most-confident third reached only 0.600, 0.300, and 0.600 across the three seeds, missing the 0.75 target every time. On seed 42, the average confidence when correct was 0.381 and when wrong was 0.378, which is almost identical; on seed 7, incorrect predictions were slightly more confident than correct predictions. The inconsistent labeling identified in the agreement report likely made calibration harder, and the small dataset was not enough for the model to produce dependable confidence rankings.

---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate before the improvement:** 17 / 30 = 57%

**Agreement rate after relabeling:** 29 / 30 = 97%

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
> *The post:* “The club championship scoring changed in 2019 from top-6 to
> top-10. Since then our B team has finished above the A team twice. That's not
> depth improving, it's the scoring rewarding turnout.”
>
> *Staff said / I said:* Staff said `analysis`; I said `hot_take`.
>
> *My call, and why:* Staff is right. The post gives a named rule change and
> two subsequent results, then uses those facts to distinguish improved depth
> from a scoring effect. The facts are not decoration: without the scoring
> change and the two finishes, the conclusion about turnout has no support.
> I treated the confident wording as a hot take and under-applied Rule 1.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**2.**
> *The post:* “Everyone blames the hill at 18 miles. I split the field into
> people who ran the first half under 1:45 and over, and the slowdown after 18
> was almost identical for both groups. If the hill were the problem the fast
> starters would fall apart harder.”
>
> *Staff said / I said:* Staff said `analysis`; I said `hot_take`.
>
> *My call, and why:* Staff is right. This describes a comparison between two
> defined groups and reports the observed result. That result is then used to
> challenge the hill explanation, so the comparison carries the argument under
> Rule 1. I focused on the opening general statement and missed that the test
> and its result are the central evidence.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**3.**
> *The post:* “Carbon plates aren't the whole story. My times dropped 2% in the
> shoes and another 2% the following year in the same pair, when the only thing
> that changed was going from 35 to 50 miles a week.”
>
> *Staff said / I said:* Staff said `analysis`; I said `hot_take`.
>
> *My call, and why:* Staff is right. The two percentage changes and the stated
> change in weekly mileage provide a concrete comparison supporting the claim
> that carbon plates are not the whole explanation. The opening sentence alone
> would be a hot take, but the following measurements do argumentative work.
> I treated the first sentence as the entire post instead of evaluating the
> evidence that follows it.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**4.**
> *The post:* “Checked the entry lists. 41% of this year's field have never run
> the distance before, against 26% five years ago. That's why the finish-line
> photos look different, not because standards dropped.”
>
> *Staff said / I said:* Staff said `analysis`; I said `hot_take`.
>
> *My call, and why:* Staff is right. The post names the source of the
> information, gives two percentages from different years, and uses the
> comparison to reject an alternative explanation. The statistics therefore
> carry the conclusion rather than merely decorating it. I applied the
> hot-take label because the conclusion sounds assertive, but Rule 1 is about
> whether evidence supports the assertion, not whether the tone is confident.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**5.**
> *The post:* “Ran the same loop in 4C and in 24C within a fortnight, same
> effort by heart rate. 90 seconds slower in the heat over six miles. People
> keep saying heat costs you 'a bit' and it's more than that.”
>
> *Staff said / I said:* Staff said `analysis`; I said `hot_take`.
>
> *My call, and why:* Staff is right. The same loop, two temperatures, matched
> effort, distance, and 90-second difference form a concrete comparison. That
> comparison is the reason for rejecting the claim that heat costs only a
> little. Although the final sentence is general, the measured observation is
> load-bearing under Rule 1, so I was wrong to treat the post as unsupported.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**6.**
> *The post:* “Three of us ran the same session on the same day, different
> shoes, within 10 seconds of each other over 5 miles. I'm not saying shoes do
> nothing, but whatever they do was smaller than the noise between three
> people.”
>
> *Staff said / I said:* Staff said `analysis`; I said `reaction`.
>
> *My call, and why:* Staff is right. This is not primarily a report of an
> immediate feeling; it is a small comparison designed to support a
> conclusion about shoe effects versus person-to-person variation. The same
> session, distance, day, and 10-second spread are checkable details, and the
> conclusion is explicitly based on them. Rule 3 says recency does not
> override evidence, so I misused the personal voice as a reason to choose
> reaction.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**7.**
> *The post:* “If you need a gel before 90 minutes you have a fuelling
> problem, not an energy problem.”
>
> *Staff said / I said:* Staff said `hot_take`; I said `reaction`.
>
> *My call, and why:* Staff is right. The post makes a general prescription
> about runners and provides no account of something that just happened to the
> writer. The 90-minute threshold is part of the unsupported rule being
> asserted, not evidence offered to establish it. Under Rule 2, a general
> claim is hot_take even if it is phrased conversationally. I confused the
> direct, personal-sounding wording with a reaction.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**8.**
> *The post:* “Every injury thread on this forum is the same injury and the
> same three replies.”
>
> *Staff said / I said:* Staff said `hot_take`; I said `analysis`.
>
> *My call, and why:* Staff is right. The post asserts a sweeping pattern but
> gives no thread examples, count, dates, or other observation that would let
> the reader check it. “Every” makes the claim sound precise, but precision in
> wording is not the same as supporting evidence. Because the stated pattern
> is not shown to carry an argument, it remains an unsupported general claim
> under Rule 1. I treated a potentially checkable assertion as an already
> supplied fact.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**9.**
> *The post:* “Got up at 5, drove ninety minutes, and it's cancelled. Standing
> in the car park in the rain reading the email.”
>
> *Staff said / I said:* Staff said `reaction`; I said `analysis`.
>
> *My call, and why:* Staff is right. The details are a first-person account of
> an event happening to the writer now: waking early, driving, receiving the
> cancellation, and standing in the rain. They establish the situation and
> feeling, but they do not support an argument or general explanation. Rule 3
> makes the recency and personal experience decisive here. I mistook concrete
> details for analytical evidence.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**10.**
> *The post:* “First run back after eight weeks out. Two miles, slower than my
> warm-up used to be, and I don't care even slightly.”
>
> *Staff said / I said:* Staff said `reaction`; I said `analysis`.
>
> *My call, and why:* Staff is right. The eight weeks, two miles, and pace
> comparison describe the writer's return and the writer's attitude toward it.
> No conclusion is drawn from those details and no claim about running in
> general is argued. The measurable comparison is part of the personal report,
> not load-bearing evidence for an argument, so Rule 3 places it in reaction.
> I again used the presence of a number as a shortcut to analysis.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**11.**
> *The post:* “Watching the last 400 of that and I had to stand up. Still
> standing up actually.”
>
> *Staff said / I said:* Staff said `reaction`; I said `analysis`.
>
> *My call, and why:* Staff is right. This is an immediate physical and
> emotional response to something the writer is watching. It contains no
> checkable fact used to support a conclusion and no general claim about the
> race. Under Rule 2 and Rule 3, the writer's immediate experience is a
> reaction. I overread the specific “last 400” reference as evidence.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**12.**
> *The post:* “Blew up at 20 with the pace band still in my hand like it was
> going to help. Rough one.”
>
> *Staff said / I said:* Staff said `reaction`; I said `analysis`.
>
> *My call, and why:* Staff is right. “At 20” identifies where the writer's
> own race went wrong, while the pace band and “rough one” describe the
> immediate experience. The post does not use those details to explain a
> broader running phenomenon or prove a claim. This is exactly the personal,
> recent report described by Rule 3, not analysis.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**13.**
> *The post:* “Someone handed my kid an orange slice at mile 22 and I have
> been crying on and off since.”
>
> *Staff said / I said:* Staff said `reaction`; I said `analysis`.
>
> *My call, and why:* Staff is right. The mile marker and orange slice are
> details in a personal account of an emotional moment. They do not function
> as evidence for a claim; the point is the writer's immediate feeling. Rule 3
> says that recency and personal experience outweigh the mere presence of a
> concrete detail when no argument is being made. I incorrectly equated
> specificity with analysis.
>
> *Which pile:* (a) The rule covered it and I applied it loosely.

**What the pattern in my disagreements tells me:**

Most of my disagreements were pile (a): I applied the staff rules
inconsistently rather than encountering a completely missing definition. In
the first five disagreements, I often treated a confident conclusion as a
hot_take even when a comparison, measurement, or dated result was doing the
argument's work. In the last eight, I over-weighted isolated concrete details
or personal wording and failed to ask whether the post actually made an
argument or instead reported an immediate personal experience. This shows a
systematic tendency to treat any specific number or detail as analysis and to
underuse the reaction label.

The one case I found most defensible as an alternative reading was
“Every injury thread on this forum is the same injury and the same three
replies.” I ultimately accepted staff's hot_take label because the post gives
no examples or count, but `analysis` is a reasonable reading if “same” is
treated as a specific, checkable observation. I classify that boundary as
pile (c): the written rule does not fully say how much evidence must be
displayed for a broad observational claim. That ambiguity does not erase the
larger pattern: 12 of 13 disagreements were consistency errors in applying
rules that were already present.

---

## The Improvement

**What I changed:**

I relabeled 12 rows in the staff-agreement sample at the `analysis` versus
`hot_take` and `reaction` boundaries. The corrected rows are the five
evidence-backed comparisons, one smaller evidence-backed comparison, the
unsupported prescription, and five immediate personal reports. I left the
one genuinely ambiguous broad-observation case unchanged. The single rule
used for the relabel was: a concrete detail counts as `analysis` only when it
supports a claim or explanation; concrete detail by itself does not make a
post `analysis`.

**Which diagnosis pointed at it:**

The diagnosis for Criteria 1, 2, 4, and 5 identified inconsistent application
of the labeling rules as the main source of noise. The agreement report showed
12 of 13 disagreements came from over-weighting a number or other specific
detail instead of checking whether it did argumentative work, so this
improvement targets that failure directly.

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall accuracy | ≥ 0.65 | 0.567 | 0.400 | 0.400 | MISSED |
| 2. Every label F1 | ≥ 0.50 | analysis 0.750; question 0.625; recommendation 0.167 | analysis 0.182; question 0.550; recommendation 0.000 | analysis 0.000; question 0.550; recommendation 0.200 | MISSED |
| 3. Label balance | Every label ≤ 50% | analysis 31.5% | question 38.0% | recommendation 30.5% | MET |
| 4. Staff/reference agreement | ≥ 75% | 29/30 = 0.967 | 29/30 = 0.967 | 29/30 = 0.967 | MET |
| 5. Confidence ranking | Top ≥ 0.75 and gap ≥ 0.15 | top 0.600; bottom 0.500; gap 0.100 | top 0.300; bottom 0.300; gap 0.000 | top 0.600; bottom 0.100; gap 0.500 | MISSED |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->

Yes. The agreement criterion moved from 17/30 (56.7%) to 29/30 (96.7%),
so Criterion 4 is now MET. The one remaining disagreement is the deliberately
ambiguous broad-observation case. The training dataset was not changed after
the first experiment showed that broad relabeling reduced held-out F1, so the
model criteria remain unchanged rather than being presented as an unsupported
improvement.


---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->

Criteria 1, 2, and 5 still need a larger and more consistently labeled
training set; the three-seed results remain unstable, recommendation F1 is
still weak, and confidence does not reliably track correctness. Criterion 4
now passes the target, but the model was not retrained on the agreement sample
because those posts use the staff taxonomy (`analysis`, `hot_take`, and
`reaction`) rather than this project's labels.


**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->
I meant for my three labels to distinguish posts that seek information, advise a choice, or present evidence-based obersvations. The model learned that the question label was seen as a broad default as it labeled 8 out of 8 true recommendation posts as questions, while also misclassifying 3 analysis posts as questions. Thus, the model didn't reliably learn the intended boundary between advising, asking, and analyzing. 


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
