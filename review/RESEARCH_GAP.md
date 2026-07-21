# EduScamSense — Research Gap Analysis

*Synthesised from the 25 reviewed papers (2021–2026) in the literature-review matrix. Each cluster summarises what prior work covers, then the gaps identify what is missing and where EduScamSense contributes.*

---

## 1. How the gap was identified

The 25 papers were grouped into seven thematic clusters, and each was reviewed across research problem, methodology, model/framework, dataset, results, explainability, external evaluation, and limitations. The gap is defined as the intersection of capabilities that **no single reviewed work delivers together**, cross-checked against EduScamSense's design goals (a bilingual Bangla–English, educator-focused scam-awareness platform).

---

## 2. What prior work already covers (thematic synthesis)

| Cluster | Papers | What is well covered | What it does *not* do |
|---|---|---|---|
| **Phishing detection & awareness** | P01–P05 | High-accuracy ML/LLM phishing/email detection (up to 99.7%), explainable LLM reasoning, adversarial robustness | English-centric; research-grade detectors, not learner-facing education; no teacher focus |
| **Cyber scams & human behaviour** | P06–P09 | Susceptibility predictors, dual-process (heuristic vs systematic) theory, overconfidence/social-influence drivers | Explanatory only — no intervention/tool; repeatedly shows *knowledge alone is insufficient* |
| **Voice cloning & audio deepfakes** | P10–P12 | Generalizable, partly interpretable clone detection; large adversarial benchmarks (ASVspoof 5) | Pure technical detection for experts; no lay-user/educator awareness layer |
| **Visual deepfakes & media literacy** | P13–P15 | Human detection limits, media-information-literacy framing, individual-difference predictors | Passive strategy lists proven **ineffective** (P14); calls for interactive, feedback-driven training |
| **Teacher cybersecurity training** | P16–P19 | Validated awareness instruments (SEM, KAB), competence indicators, documented awareness gaps | **Assessment, not intervention** — no evaluated training system; region-specific; no Bangla |
| **AI-supported education & feedback** | P20–P22 | Intelligent tutoring, explainable automated feedback (transformers), Socratic LLM tutoring | Applied to essays/math — never to cyber-scam recognition |
| **Multilingual / Bangla NLP** | P23–P25 | Bangla classification (ensembles), balanced dataset curation, LLM prompting evaluation | Applied to sentiment/violence/generic text — **never to phishing/scam**; no scam corpus |

---

## 3. Cross-cutting observations

- **Fragmentation by threat type.** Phishing (P01–P05), voice cloning (P10–P12), and visual deepfakes (P13–P15) are studied in *separate* literatures; no reviewed work trains users against all three in one place.
- **Detection ≠ education.** Technical detectors (P01–P05, P10–P12) achieve high accuracy but are not designed as learning tools; conversely, education/behaviour work (P06–P09, P16–P22) rarely embeds a working classifier.
- **Knowledge alone fails; active, explainable practice works.** P07/P08/P09 show susceptibility persists despite awareness; P14 shows static tip-lists do not help; P03/P10/P21/P22 show explainable, feedback-driven approaches do.
- **Language divide.** State-of-the-art scam detection is English-centric (P01–P05), while Bangla NLP capability (P23–P25) has never been pointed at scams.
- **Weight vs deployability.** Best detectors lean on heavy proprietary LLMs (P02–P05, P25); low-resource, deployable classifiers for education settings are under-explored.

---

## 4. Identified research gaps

- **G1 — No integrated multi-threat platform.** Phishing, voice-cloning, and deepfake awareness are never combined in a single evaluated system.
- **G2 — No bilingual Bangla–English scam education.** Bangla NLP work exists (P23–P25) but is never applied to phishing/scam text; phishing work ignores Bangla.
- **G3 — Teachers are assessed, not trained.** Pre-service/in-service teacher studies (P16–P19) measure awareness but provide no evaluated intervention tool.
- **G4 — Behavioural theory not operationalised.** Findings that active, systematic-processing practice beats passive knowledge (P07–P09, P14) are rarely built into an actual training product.
- **G5 — Explainable feedback pedagogy not applied to scams.** Explainable-feedback and Socratic tutoring methods (P20–P22, P03) are not used for scam-recognition learning.
- **G6 — No curated, expert-validated bilingual educator-scam dataset.** Balanced-dataset curation methods (P24) have not produced a Bangla–English educator-scenario scam corpus.
- **G7 — Deployability gap.** Reliance on heavy LLMs (P02–P05, P25) leaves lightweight, low-resource-friendly classifiers for education under-explored.

---

## 5. How EduScamSense addresses each gap

| Gap | EduScamSense contribution |
|---|---|
| G1 | Single platform uniting phishing analysis + voice-cloning awareness + deepfake awareness modules |
| G2 | Bilingual **Bangla–English** scenarios, classifier, and interface |
| G3 | An *intervention* for educators (scenarios, quizzes, pre/post-test) — not just measurement |
| G4 | Scenario-based, interactive practice that pushes learners toward systematic evaluation, with explanatory feedback |
| G5 | Explainable, content-specific feedback on why a message is a scam (adapts P03/P21 ideas) |
| G6 | A curated, **expert-reviewed** bilingual educator-scenario dataset (adapts P24's balanced-curation + multi-annotator validation) |
| G7 | A **lightweight** TF-IDF + classical-ML classifier suitable for low-resource deployment (Gradio / Hugging Face Spaces) |

---

## 6. Positioning statement (drop-in for Related Work / Introduction)

> Existing research investigates phishing detection, scam susceptibility, audio/visual deepfake detection, AI-supported educational feedback, and Bangla NLP **as separate strands**. High-accuracy detectors are English-centric and research-oriented rather than educational; behavioural studies repeatedly show that awareness alone does not reduce victimisation and that passive tip-lists are ineffective; teacher-focused work measures awareness but offers no evaluated intervention; and Bangla language technology has not been applied to scams. **No prior system combines lightweight bilingual (Bangla–English) phishing classification, expert-validated educator scam scenarios, and explainable, interactive awareness training for phishing, voice-cloning and deepfake threats within a single evaluated platform.** EduScamSense targets exactly this intersection.

---

## 7. Evidence-to-gap traceability (quick map)

- G1 ← siloed P01–P05 / P10–P12 / P13–P15
- G2 ← P01–P05 (English) vs P23–P25 (Bangla, non-scam)
- G3 ← P16–P19 (assessment only)
- G4 ← P07, P08, P09, P14
- G5 ← P03, P10, P20, P21, P22
- G6 ← P24 (method exists, corpus does not)
- G7 ← P02–P05, P25 (heavy LLM reliance)
