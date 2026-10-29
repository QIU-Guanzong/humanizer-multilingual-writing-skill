# Multilingual product-copy sample run — 2026-10-29

An independent Codex subagent read the updated `SKILL.md` and `references/product-copy.md`, then executed and reviewed the four synthetic prompts below. The prompts were supplied by another agent; the executing agent also performed the review. This is one model-assisted qualitative run, not a blind study, cross-model benchmark, product verification or native-speaker review. The exact model version was not recorded. The text is synthetic and does not describe a real customer's account, data feed or agreement.

## 1. Compare two supplied language versions

**Request:** What substantive element differs between these versions? Do not presume the contents of the actual agreement.

**Input:**

- English: “Fees, benefits and cancellations depend on the service agreement.”
- Traditional Chinese: 「費用與取消安排以服務協議為準。」

**Output:**

The English version includes **benefits**, while the Traditional Chinese version mentions fees and cancellation arrangements but does not mention benefits. The wording alone does not establish what the service agreement covers; check the authoritative terms before changing either version.

**Review:** Pass on the specified checks: identifies the omitted item and does not invent agreement contents or claim either version is authoritative. No changes to a real product were made.

## 2. Recorded value and unavailable feed

**Request:** Edit this English product notice concisely while preserving its status and meaning.

**Input:** “The value was recorded yesterday. The feed is unavailable, so the display is not live.”

**Output:** “The value was recorded yesterday; the feed is unavailable, so the display is not live.”

**Review:** Pass on the specified checks: yesterday remains the observation time, the feed remains unavailable, and the display is not presented as live. No refresh time, source recovery or next step was invented. This small edit shows preservation, not broad proof of style quality.

## 3. Payment and access verification

**Request:** Lightly edit this English support message while retaining each status.

**Input:** “The payment processor reported success; account access is awaiting confirmation and remains inactive.”

**Output:** “The payment processor reported success. Account access is still awaiting confirmation and remains inactive.”

**Review:** Pass on the specified checks: processor report, pending confirmation and inactive access remain distinct. The output does not assert that account access is active or introduce a refund or remedy.

## 4. Portuguese missing and failed image states

**Request:** Simplify this Portuguese product message while preserving the two distinct states.

**Input:** “A imagem não foi fornecida. Outra imagem não pôde ser carregada.”

**Output:** “Uma imagem não foi fornecida; outra não pôde ser carregada.”

**Review:** Pass on the specified checks: one image was not supplied, while another could not be loaded; the output does not conflate them or assert why loading failed. Portuguese naturalness and regional suitability have not been reviewed by a native speaker.

## Limitations

These cases exercise supplied instructions and factual distinctions in a small set of examples. The same agent produced and reviewed the outputs, so the result is subject to self-assessment bias. They do not establish performance on unseen material, automatic skill activation, specific product behavior, or naturalness for all readers and locales. No failure was observed on the checks listed above; that is not evidence that the skill is generally failure-free.
