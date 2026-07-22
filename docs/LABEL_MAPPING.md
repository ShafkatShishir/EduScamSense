# EduScamSense — Label Mapping (Stage 6)

Maps each secondary dataset's **original labels** to the **EduScamSense classifier scheme**. The first phishing classifier is **binary** (`phishing` vs `legitimate`); `promotional_spam` and `uncertain` are held out of the binary model (optional 3-class experiment only).

---

## 1. BanglaBarta (SRC02) — direct mapping
Balanced 3-class set (924 each). Mapping is unambiguous:

| Original label | Count | → EduScamSense label | In binary model? |
|---|---|---|---|
| `smish` | 924 | `phishing` | ✅ Yes |
| `normal` | 924 | `legitimate` | ✅ Yes |
| `promo` | 924 | `promotional_spam` | ❌ Held out (3-class only) |

---

## 2. UCI SMS Spam (SRC01) — `ham` direct, `spam` needs manual review
`spam` ≠ always phishing, so it must be examined (Stage-6 requirement).

| Original label | Count | → EduScamSense label |
|---|---|---|
| `ham` | 4,827 | `legitimate` (direct) |
| `spam` | 747 | **manual_review** → split into `phishing` / `promotional_spam` / `uncertain` |

### UCI `spam` first-pass triage (heuristic — REQUIRES human verification)
Auto-tagged, to be confirmed in `data/interim/uci_spam_triage_for_review.csv` (fill the `verified_tag` column):

| Auto tag | Count | Rule used |
|---|---|---|
| `phishing` | 346 | URL present, or credential/account/verify/bank terms, or prize-claim + call/text-to-number fraud |
| `promotional_spam` | 202 | offers/discounts/free/subscribe/ringtone with no credential or fraud lure |
| `uncertain` | 199 | quizzes, competitions, ambiguous — decide case-by-case |

> ⚠️ These counts are a **machine first pass**, not final. Two reviewers must confirm each `spam` record before it enters the corpus.

---

## 3. Final target label set (Dataset 1)
- **Binary model:** `phishing`, `legitimate`
- **Held out of binary model:** `promotional_spam`, `uncertain`
- **Never in Dataset 1 (Dataset 2 only):** `voice_cloning`, `deepfake`

## 4. Language tagging
- BanglaBarta → `language = bn`
- UCI → `language = en`
