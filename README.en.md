# Multilingual AI Writing Humanizer Skill

[繁體中文](README.md) · 去 AI 味 · 去 AI 话 · Natural writing

A writing skill for AI assistants that helps make prose clearer and more natural while keeping the original meaning. It focuses on Traditional Chinese for Hong Kong and Taiwan, with experimental guidance for Simplified Chinese, English, Japanese, Korean, Spanish, French and Portuguese.

Use it for product copy, announcements, reports or a requested rewrite. Provide the text, audience, region, desired tone and editing scope. For proofreading, say so: the skill should correct only what you request. It is a set of instructions for a compatible assistant, not a standalone application or a guarantee of a particular result.

## What changes?

Example in Traditional Chinese:

- Before:「值得一提的是，團隊在本季推出了三個版本，並且修正了十七個問題。」
- After:「團隊本季推出三個版本，修正了十七個問題。」

The edit removes a filler phrase while retaining the time and quantities. Useful repetition, personal voice, relevant qualifications and necessary disclosures should remain. The skill also protects links, code, UI labels and placeholders unless the user authorizes a change.

It does not identify who wrote a text or promise to bypass AI detectors. Its output still needs a human review and any appropriate fact-checking. Language profiles are initial guidance, not native-reviewed localization.

## Install and use in Codex

Clone this repository, enter its directory, then run:

```sh
skill_dir="${CODEX_HOME:-$HOME/.codex}/skills/clear-writing-multilingual"
if [ -e "$skill_dir" ] || [ -L "$skill_dir" ]; then
  printf 'Destination exists; inspect it first: %s\n' "$skill_dir"
else
  mkdir -p "$skill_dir"
  cp SKILL.md LICENSE "$skill_dir/"
  cp -R references third-party-licenses "$skill_dir/"
fi
```

Restart or open a new conversation as required by your tool. Other Agent Skills-compatible tools may use a different installation path. Example request:

> Use the clear writing skill to lightly edit this Hong Kong Traditional Chinese product notice. Preserve all facts, UI labels and the formal tone; return only the final copy.

[SKILL.md](SKILL.md) is the entry point; [references](references/) contain locale guidance.

## Testing and limitations

The [evaluation catalog](tests/evaluation.md) lists cases and expected checks. Dated records in [tests](tests/) contain the actual prompts and sample outputs, including a Japanese evidence-scope issue and a follow-up trial. These are limited model-assisted examples, not a controlled cross-model benchmark or native-speaker review. Do not infer automatic invocation or quality for all dialects from them.

## Credits and license

Inspired by [qu-ai-wei](https://github.com/LifelongLazyLearner/qu-ai-wei) by LifelongLazyLearner and [humanizer](https://github.com/blader/humanizer) by Siqi Chen. qu-ai-wei also credits [yage.ai](https://yage.ai/). This is an independent project, not an official Traditional Chinese edition. Upstream revisions: qu-ai-wei `1d32e803f091ec90808a69683ebf49e8a970a5e7`; humanizer `0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0`. Their notices are in [third-party-licenses](third-party-licenses/); new project content is [MIT licensed](LICENSE).
