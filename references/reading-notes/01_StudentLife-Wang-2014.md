# Wang et al. (2014) – StudentLife

**In-text:** (Wang et al., 2014)

**Full reference (Harvard Anglia):** Wang, R., Chen, F., Chen, Z., Li, T., Harari, G., Tignor, S., Zhou, X., Ben-Zeev, D. and Campbell, A.T. (2014) 'StudentLife: assessing mental health, academic performance and behavioral trends of college students using smartphones', in *Proceedings of the 2014 ACM International Joint Conference on Pervasive and Ubiquitous Computing*. New York: ACM, pp. 3–14. Available at: https://doi.org/10.1145/2632048.2632054 (Accessed: DD Month 2026)

**Link:** https://dl.acm.org/doi/10.1145/2632048.2632054

**Date read:** 30 October 2026

**Priority:** Read fully

<br>

## Summary (own words, 2–3 sentences)

The paper notes that the stress of student life remains hidden, therefore the StudentLife study set up a continuous sensing app that assesses day-to-day impacts of stress, sleep, activity, mood, sociability, mental well-being, and academic performance on a single class of 48 students across a 10 week term at Dartmouth College. The study was conducted using Android phones.

The study resulted in a number of correlations between the sensor data from smartphones and mental health and academic performance of the students.

The study also noted that as the term progresses and workload increases, negative factors such as stress increased, while positive factors such as sleep, conversation, and activity plummets.

<br>

## Dataset and sample

The StudentLife dataset was used, which includes automatic sensor data, behavioral interferences, and self-reported EMA data.

52.6 GB of sensing data from startphones was collected over the 10 week period:

1. Activity data, including activity duration (total time duration the user moves per day), indoor mobility and the total traveled distance (i.e., outdoor mobility) per day.

2. Conversation data, including conversation duration and frequency per day.

3. Sleep data, including sleep duration, sleep onset and waking time.

4. Location data, including GPS, inferred buildings when the participant is indoors, and the number of co-located Bluetooth devices.

<br>

## Method

**Study type:** Observational and correlational. No predictive model was
trained. The paper describes data collection and reports correlations.

**Participants and recruitment (pp. 2–3)**
- Recruited from one class (CS65 Smartphone Programming), Dartmouth,
  Spring 2013. IRB approved.
- 75 enrolled in the class, 60 joined the study, 48 completed it.
- 30 undergraduates and 18 postgraduates; 38 male, 10 female.
- 11 used their own Android phone (primary users); 37 carried a study
  Nexus 4 alongside their own phone (secondary users).

**Data collection procedure (pp. 2–3)**
- Pre- and post-term surveys (PHQ-9, Perceived Stress Scale, flourishing,
  UCLA loneliness) via SurveyMonkey; exit interview at the end.
- 10 weeks of continuous sensing; data uploaded when phones charged on WiFi.
- EMAs averaged about 8 per day, with extra stress EMAs scheduled around
  deadlines.
- Researchers emailed students when data gaps were noticed; incentives
  (T-shirts, prize draws) used to boost compliance.
- Privacy: random user IDs, hashed call/SMS logs, encrypted upload.

**Compliance (p. 3)**
- Sensing compliance: 87% (primary), 81% (secondary).
- EMA compliance: 65% (primary), 72% (secondary).
- Both sensing hours and EMA responses decline as the term goes on.

**How behavioural features were inferred (pp. 3–4)**
- Activity: decision tree classifier on accelerometer data (~94% accuracy),
  a label every 2 seconds; 10-minute windows marked active above a
  threshold, summed into daily activity duration.
- Sleep: inferred from light, phone usage/lock, activity and sound;
  duration accurate to about ±32 minutes; bedtime checked against
  Jawbone UP devices for 10 students.
- Conversation: audio classifier detects being "around conversation"
  (no content recorded).
- Stress: single-item EMA delivered through the app, preceded by a
  photo-based mood check (PAM).

**Dataset produced (pp. 4–5)**
- 52.6 GB of sensing data; 35,295 EMA and PAM responses.
- Analysis split into epochs: day 9am–6pm, evening 6pm–12am,
  night 12am–9am.

**Analysis (p. 5 onwards)**
- Pearson correlations between sensing/EMA data and pre/post survey
  scores and GPA.
- Term-level trends shown with fitted curves ("Dartmouth term lifecycle").

<br>

## Key results

**Stress (Perceived Stress Scale) – Table 6, p. 6; Table 8, p. 7**
- Sleep duration was negatively correlated with pre-term perceived stress
  (r = −0.355, p = 0.024): students who slept more reported less stress.
- Conversation frequency/duration was negatively correlated with stress,
  strongest during the day epoch (r = −0.524, p = 0.001, pre-term).
- Daily stress EMA responses correlated with term-level perceived stress
  (pre r = 0.458, p = 0.003; post r = 0.412, p = 0.009), suggesting the
  single-item stress EMA tracks a validated stress measure.

**Depression (PHQ-9) – Table 3, p. 6**
- Less sleep was associated with higher depression scores
  (pre r = −0.360; post r = −0.382).
- Fewer conversations and fewer co-locations with others were associated
  with higher depression scores.
- Stress EMA correlated with post-term PHQ-9 (r = 0.412, p = 0.010).

**Other well-being (Tables 5, 7, 8)**
- Loneliness was associated with lower activity duration and mobility.
- Flourishing was associated with more conversation and co-location.

**Academic performance (Table 9, pp. 7–8)**
- More daytime conversation was associated with higher spring GPA;
  more indoor mobility was associated with lower GPA.

**Term lifecycle (Figure 5, pp. 8–9)**
- Stress rose through the midterm period (around days 22–36) and again
  at the end of term.
- Positive affect, sleep, activity and conversation all fell as
  workload increased; sleep was lowest at midterms and in the final week.
- Class attendance fell from about 75% to about 25% by the end of term.

<br>

## Relevance to my project

| CRISP-DM phase | How it informs my work |
| --- | --- |
| Business Understanding | Establishes the problem: student stress rises as workload increases and is largely hidden from staff. The authors note that deans, clinicians and faculty all care about student well-being, which supports support services as my intended user. |
| Data Understanding | Primary source for provenance: one CS class, 48 students, Dartmouth, Spring 2013, Android only, mostly male. Explains how the stress EMA was asked and that sleep/activity are classifier outputs with known error (e.g. sleep ±32 min). |
| Data Preparation | Compliance drops towards the end of term, so missing data is likely concentrated in later weeks, when stress is highest (not missing at random). The night epoch (12am–9am) suggests a "day" should not simply start at midnight, because sleep and late-night phone use span midnight. |
| Modelling | Sleep and activity have prior support as features (correlations with stress and depression). Phone usage does not appear in the reported results, so its inclusion needs support from other sources. Time in term (midterm/end of term) may be a useful contextual feature or a confounder. |
| Evaluation | Gives a reference point: the original study found associations, not causes, and only between students. My results can be compared against these. Limits generalisability (single institution, 2013, small sample). |

## Decisions this supports
- Including sleep and activity as features.
- Using associative wording ("associated with", "distinguish") rather than causal.
- Defining the day boundary deliberately, rather than defaulting to midnight.
- Treating missingness as potentially related to stress, and checking it
  by week of term.
- Stating generalisability limits in the evaluation and paper.

## Ethics notes
- Data was de-identified (random IDs, hashed call/SMS logs).
- The authors describe a professor using study data to intervene for two
  struggling students. This shows the potential benefit for support
  services, but also why access to this kind of data needs strict
  governance and human oversight. Useful for my deployment section.