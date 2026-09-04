# iPhone Candid Photo Skill

A Codex skill for turning short scene descriptions and reference images into believable iPhone-style candid photographs. It packages a structured mobile-photography prompt workflow into a one-step experience: install the skill, describe the scene, and let Codex generate the image.

## What it improves

- Chooses an appropriate 13mm, 24mm, or 77mm phone-camera perspective.
- Uses mobile computational-photography cues without drifting into DSLR or movie-poster aesthetics.
- Adds restrained, situation-specific imperfections.
- Handles reference images with explicit identity, pose, and edit invariants.
- Supports direct image generation, JSON-only output, and auditable strict-source tests.
- Includes anti-plastic-skin guidance learned from real generation failures.

## Install

Copy the complete `iphone-candid-photo` folder into your Codex skills directory:

```text
$CODEX_HOME/skills/iphone-candid-photo/
```

On a default Windows installation this is commonly:

```text
C:\Users\<you>\.codex\skills\iphone-candid-photo\
```

Start a new Codex session after copying it so the skill can be discovered.

## Use

Direct generation:

```text
用 iPhone 随手拍风格生成：夜晚消防现场，一名救援者抱着伤员跑出建筑，路人手机抓拍。
```

With references:

```text
参考我上传的两张图：第一张控制人物身份，第二张控制姿势。生成真实版 iPhone 合影。
```

JSON only:

```text
只输出可复用的 JSON 提示词，不要生成图片：雨夜便利店门口的朋友合影。
```

Explicit invocation:

```text
Use $iphone-candid-photo to generate a 9:16 candid phone photo of two friends leaving a concert.
```

## Repository contents

- `SKILL.md` — behavior and generation workflow.
- `agents/openai.yaml` — Codex UI metadata.
- `references/schema.md` — JSON contract for prompt-only and audit modes.
- `NOTICE.md` — inspiration and attribution.
- `LICENSE` — MIT license for this implementation.

## Attribution

The workflow was inspired by a public mobile-photography meta-prompt shared by Machina (`@EXM7777`). This repository is an independent rewrite and extension; it does not reproduce the source prompt verbatim and is not affiliated with or endorsed by the original author. See [NOTICE.md](NOTICE.md).

## License

MIT. The license covers this independently written skill implementation. It does not grant rights to third-party trademarks, reference images, characters, or other user-supplied material.
