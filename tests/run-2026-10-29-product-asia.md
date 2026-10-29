# Product-copy sample rewrites: Japanese, Korean and Simplified Chinese — 2026-10-29

## Method and limitations

A Codex subagent read the updated `SKILL.md`, `references/product-copy.md` and `references/languages.md` and performed the four synthetic rewrites below in one session, then reviewed its own outputs. The model version was not recorded. The test was **not blind**: the reviewer had previously seen the task, the relevant preservation guidance and related status-preservation concerns. These are isolated qualitative examples, not a controlled or multi-model benchmark. No native-speaker review has been completed; naturalness and local usage need independent review.

## 1. Japanese: approval and access

Request: 軽く校正。

Input:

> 公開日はまだ確定していません。決済の確認が完了するまでは、サービスは利用できません。

Output:

> 公開日はまだ確定していません。決済の確認が完了するまでは、サービスは利用できません。

Review: The output leaves the already concise original unchanged. It retains the date as not yet finalized, rather than asserting that no date exists, and preserves payment confirmation as a prerequisite for access. It does not promise that service activation will occur automatically once confirmation is complete. Polite register remains unchanged.

## 2. Korean: old value and stale source

Request: 간결하게 정리.

Input:

> 이전에 저장된 값입니다. 데이터 소스가 갱신되지 않아 실시간 값이 아닙니다.

Output:

> 이전에 저장된 값이며, 데이터 소스가 갱신되지 않아 실시간 값이 아닙니다.

Review: The value remains previously saved and is explicitly not real-time because the source has not updated. No current timestamp or live-data claim is added. The formal polite ending remains. Korean naturalness has not been independently reviewed.

## 3. Simplified Chinese: preview persistence and payment

Request: 请简化。

Input:

> 预览未保存到账号，刷新页面后会重置；付款回执已提交，权益仍待核验。

Output:

> 预览未保存到账号，刷新后会重置；付款回执已提交，权益仍待核验。

Review: Both account non-persistence and the refresh reset condition remain, as do the submitted receipt and pending entitlement verification. The output does not say payment was confirmed, entitlement was granted, or the preview was saved.

## 4. Japanese: uncertain write and existing UI label

Request: Simplify Japanese product copy and preserve the existing UI label 『再試行』.

Input:

> 写入が完了したか確認できません。再試行すると同じ依頼を確認します。

Output:

> 写入が完了したか確認できません。再試行すると同じ依頼を確認します。

Review: The original is retained because the meaning of checking the same request and the actor doing so are not fully specified. The label string 「再試行」, uncertainty about completion and stated retry consequence remain. The output does not infer that the first write failed, that another write is safe, or that retry necessarily prevents duplication. The source's unusual 「写入」 terminology is left unchanged; its appropriateness for the actual UI must be checked by a Japanese-speaking product reviewer. This case does not establish that retry behavior works as described.
