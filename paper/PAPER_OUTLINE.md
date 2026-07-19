# EduScamSense — Paper Outline

**Full title:** EduScamSense: Development and Preliminary Evaluation of a Bangla–English Cybersecurity Education Platform for Educators
**Extended title:** …for Educator Awareness of Phishing, Voice-Cloning, and Deepfake Scams
**Target format:** 8-page IEEE conference paper
**Status:** Outline (fill sections with real content only after results exist)

---

## Research questions

- **RQ1 — Phishing classification:** How accurately can lightweight ML models (rule-based, TF-IDF + Naive Bayes / Logistic Regression / Linear SVM) classify Bangla–English phishing vs. legitimate text?
- **RQ2 — Dataset quality:** Are the educator-focused scenarios correct, realistic, appropriate and safe, per two independent reviewers (agreement, Cohen's kappa, four quality scores)?
- **RQ3 — Platform design:** How can phishing analysis, scenario-based learning and AI-scam awareness be integrated into one bilingual educator platform?
- **RQ4 — Preliminary usability:** How usable and relevant is the prototype (task completion, usability questionnaire, clarity, interface issues, qualitative feedback)?
- **RQ5 (optional) — Learning improvement:** Only with ethics approval + informed consent + pre/post-test + approved recruitment.

---

## Section structure (IEEE, 8 sections)

### I. Introduction  (~0.75–1 page)
- Growth of AI-enabled scams (phishing, voice cloning, deepfakes)
- Why educators/teachers are a vulnerable, high-impact group
- Gaps in existing work (no single bilingual, educator-focused, evaluated platform)
- The proposed system: EduScamSense
- RQ1–RQ4 and the paper's contributions (list ~5)

### II. Related Work  (~1–1.5 pages)
- Phishing detection & cybersecurity awareness education
- Cyber scams & human behaviour / scam vulnerability
- Voice cloning & audio-deepfake risk
- Visual deepfakes & media literacy / deepfake awareness
- Teacher professional learning & cybersecurity training
- AI-supported education & feedback systems
- Bangla / multilingual cybersecurity NLP
- **End with the research gap** (below)

### III. Methodology  (~2 pages)
- Overall research design
- Secondary dataset selection (BanglaBarta, UCI SMS Spam)
- Synthetic educator-scenario development
- Translation & back-translation procedure
- Human (expert) validation process
- Data preprocessing (dedup, PII removal, URL defanging, Bangla Unicode normalisation)
- Train/validation/test splitting by `template_family_id` (70/15/15) + leakage check
- Models (rule-based → TF-IDF+NB → LR → SVM) and evaluation metrics
- System development (Gradio) and architecture
- Ethics & safety

### IV. System Architecture  (~0.5 page)
- Flow diagram (input → preprocessing → classifier → awareness/learning modules → output)
- Modules: phishing analysis, voice-cloning awareness, deepfake awareness, scenario quiz, pre/post-test, results

### V. Results  (~1–1.5 pages)
- Dataset composition & statistics
- Reviewer agreement & Cohen's kappa
- Model comparison (validation → selected model → single test evaluation)
- Confusion matrix; accuracy, precision, recall, F1
- Bangla vs. English and class-wise results
- Error analysis (false positives / false negatives)
- Prototype / usability results (pre/post if available)

### VI. Discussion  (~1 page)
- Meaning of results; Bangla vs. English performance gap
- Implications for educator cybersecurity education
- Relation to prior work; practical value

### VII. Limitations  (~0.5 page)
- Dataset size; partly synthetic data; two languages only
- Few reviewers (2); small/absent pilot
- No full audio/video deepfake detection (awareness only)
- Possible bias; generalisability constraints

### VIII. Conclusion & Future Work  (~200–300 words)
- What was built and evaluated
- Main findings and contribution
- Next steps

### Abstract  (150–220 words — write LAST)
### Keywords  (write last)

---

## Draft research gap
> Existing studies investigate phishing awareness, scam vulnerability, deepfake detection and AI-supported education separately. However, limited research combines Bangla–English cybersecurity education, educator-focused scam scenarios, lightweight phishing classification and structured awareness training for phishing, voice-cloning and deepfake threats within one evaluated system.

---

## Recommended writing order (NOT top-to-bottom)
Methodology → Dataset Development → System Architecture → Evaluation Method (experiment setup) → Results → Error analysis → Discussion → Limitations → Related Work → Introduction → Conclusion → Abstract → Title / Keywords.

---

## Planned tables & figures

**Tables**
- T1 — Dataset sources & licences
- T2 — Final scenario distribution
- T3 — Human-validation results (agreement, kappa, quality scores)
- T4 — Model comparison
- T5 — Bangla / English performance
- T6 — Error categories / prototype results

**Figures**
- F1 — System architecture
- F2 — Dataset development workflow
- F3 — Confusion matrix
- F4 — Gradio interface screenshot
- F5 — User learning flow

---

## Abstract template (fill only once results exist)
> Educators are increasingly targeted by AI-enabled scams, yet accessible bilingual cybersecurity education is limited. This paper presents **EduScamSense**, a Bangla–English platform that combines lightweight phishing-text classification, expert-reviewed educator scenarios, and awareness modules for voice-cloning and deepfake scams. We describe [dataset development], [human validation with N reviewers, kappa = __], and [model comparison], with the best model achieving [__ F1 / recall] on a held-out test set. A preliminary [usability/expert] evaluation indicates [__]. Results represent a preliminary technical and educational evaluation rather than evidence of effectiveness across all educator populations or real-world attacks.

---

## Required platform disclaimer (cite in paper + app)
> EduScamSense is an educational and awareness-support platform. Its classifications, scores, and recommendations may be incorrect and should not replace independent verification, institutional cybersecurity procedures, or professional security advice. The voice-cloning and deepfake components provide awareness training only and do not technically detect manipulated audio or video.

**Wording rule:** use "AI-enabled scams," never "AI-powered scam-detection system." Confidence output must read *"The model estimates that this message may be phishing. Verify the sender and request independently before taking action."* — never *"This message is definitely phishing."*
