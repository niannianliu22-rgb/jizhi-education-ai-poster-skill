---
name: jizhi-education-ai-poster
description: Generate branded education posters and image-generation prompts for 极致Essay, DP-Distinction Pass, and 极致AI留学生陪跑. Use when Codex needs to turn a poster brief, product information, case material, or revision request into a finished poster or a structured positioning, copywriting, visual direction, material plan, prompt, and QA result while enforcing product accuracy, brand isolation, original-material rules, and compliance boundaries.
---

# Jizhi Education AI Poster

## Overview

Use this skill to produce a complete, reviewable poster or poster plan. When the user asks for the final poster, generate the actual poster rather than stopping at copy or a proposal.

Treat product facts as higher priority than creative expression. Keep the three brands separate in value proposition, tone, visual direction, logo, and IP assets. Never fabricate products, prices, promises, screenshots, feedback, results, or logos.

## Global hard rules

- All brands and all posters default to no CTA. Do not add buttons, contact prompts, reservation prompts, QR guidance, keyword prompts, or conversion endings unless the user explicitly overrides this rule.
- Use original logos whenever available. Never redraw, restyle, or AI-generate a logo.
- Resolve every bundled path relative to this skill directory. Never emit or depend on a machine-specific home or temporary-directory path.
- Use the bundled asset inventory in [references/asset-manifest.md](references/asset-manifest.md). Do not guess asset ownership from filename, color, or pose.
- Use the approved poster reference library in `assets/examples/` as visual grammar, not as a source of current product facts, copy, CTA, prices, promises, or customer data.
- Use only brand-IP assets explicitly identified or approved by the user for the active brand.
- A `DP` chest mark belongs only to DP. An `AI` chest mark belongs only to 极致AI留学生陪跑. Never mix, replace, redraw, or infer ownership from color or pose.
- If the correct brand IP is unavailable, omit the IP instead of substituting another brand variant.
- Prefer an approved transparent PNG for free-standing logo or IP placement. Never leave an accidental rectangular source background floating over the poster background. If a source has a deliberate background, place the complete image as an intentional card or omit it; do not fake transparency by regenerating the IP.
- For case posters, every user-provided evidence image must remain the original image. Never redraw, regenerate, beautify, rewrite, clean up, fake, crop away key content, or synthesize a replacement.
- Evidence treatment is limited to placement-level scaling, spacing, stacking, framing, border, shadow, and positioning. Preserve aspect ratio and keep the evidence comfortably readable.
- If private information is visible, pause and request an already-redacted original from the user. Do not alter evidence to redact it inside the poster workflow.
- Poster height follows actual content volume and evidence count. A case poster is not automatically a long poster. Use the shortest canvas that preserves hierarchy and proof readability without clipping, crowding, or excessive empty space.
- Do not compress evidence to satisfy a predetermined canvas. Increase height or simplify supporting copy first.

## Minimum input

Start work when the brief includes:

- Brand
- Product or subject
- Poster type
- Usage goal

Accept optional channel, audience, ratio, selling points, campaign details, real materials, reference posters, and compliance constraints.

Ask at most 1-3 high-impact questions at a time. Do not ask for information that can be resolved from provided material. If a low-risk field is inferable, continue and label it as inferred.

## Hard gates

Pause or complete only the safe parts when any gate fails:

- Brand is missing and cannot be uniquely inferred.
- Product cannot be matched to source material.
- A case poster lacks required real evidence.
- Price, discount, guarantee, compensation, refund, or time-sensitive offer is unconfirmed.
- The request asks for fake evidence, altered evidence, regenerated logos, or privacy leakage.
- The only available mascot belongs to another brand.
- The requested result would require modifying an evidence image instead of placing the original.

When blocked, output `待补资料 / 修改项` and do not invent a workaround.

## Source priority

Resolve conflicts in this order:

1. Current user request, if legal and compliant
2. Latest official product material
3. Brand positioning and visual/copy rules
4. Case-material rules and approved historical structures
5. General model knowledge

If equal-priority sources conflict and recency is unclear, omit the disputed field and request confirmation.

## Workflow

### 1. Parse the brief

Normalize brand, product, poster type, usage goal, channel, audience, ratio, and material status. Label each as user-provided, matched, inferred, or pending.

### 2. Build the product fact card

Extract only verifiable positioning, audience, service content, delivery flow, advantages, price, and promise boundaries. Do not strengthen guarantees or add nonexistent steps.

### 3. Lock the brand expression

Choose exactly one brand system:

- `极致Essay`: practical academic problem-solving, clear service feeling, younger and direct marketing energy.
- `DP-Distinction Pass`: risk control, responsibility boundary, reassurance, restrained premium trust.
- `极致AI留学生陪跑`: planning, push, check, review, human-AI collaboration, light-tech systematic tone.

Cross-brand promise or IP mixing is a blocking error.

### 4. Lock the visual direction

Read [references/brand-guidelines.md](references/brand-guidelines.md) and [references/asset-manifest.md](references/asset-manifest.md). Select 2-4 approved examples matching the active brand, poster type, information density, and canvas proportion. Use them to anchor headline scale, spacing, card rhythm, graphic language, and IP balance; never copy their factual content or obsolete conversion elements. Then define brand colors, supporting colors, atmosphere, graphic language, layout temperament, logo handling, IP handling, and evidence handling.

Reference sources:

- `极致Essay`: `assets/examples/essay/`
- `DP-Distinction Pass`: `assets/examples/dp/`
- `极致AI留学生陪跑`: may borrow layout grammar from `assets/examples/dp/`, but must keep AI-companion positioning, logo, and AI chest-mark IP.

### 5. Choose one production logic

- Marketing poster: pain point -> scenario -> value
- Product poster: positioning -> audience -> content -> process -> advantage
- Case poster: background -> problem -> process -> result -> original proof
- Comparison poster: comparison premise -> side-by-side differences -> conclusion
- Process poster: positioning -> numbered stages -> outcome

Do not reserve a CTA ending by default.

### 6. Create the strategy and copy

Determine user segment, core pain point, trigger, trust barrier, information threshold, and reading path. Write layout-ready title, subtitle, selling points, service content, trust proof, and necessary boundary statements.

Translate features into concrete user value. Avoid unsupported fear or outcome claims.

### 7. Create the visual and material plan

Specify ratio, visual center, hierarchy, density, materials, and placement of logo, IP, screenshots, and proof images. Choose canvas height from copy length and minimum readable evidence size.

For case posters, preserve every evidence image exactly and use the evidence as proof, not as decoration. Do not create fake chat bubbles or reconstructed score panels.

### 8. Produce the image

When generating a new illustration, use the image-generation tool. When composing a case poster, prefer deterministic layout/compositing so supplied evidence, logos, and IP remain original.

Separate any AI-generated base background from post-production placement of original logo, IP, evidence, and Chinese text. Resolve bundled assets from `assets/` relative to this skill directory. Do not substitute files from another local folder when a bundled original is available.

When the image tool accepts visual references, pass the selected approved examples as style references while reserving original logo, IP, and evidence for deterministic post-production placement. Do not ask the model to recreate a bundled logo or mascot from a reference poster.

### 9. Run QA

Check:

- Product truth
- Brand isolation
- Copy accuracy
- Visual hierarchy
- Material originality
- Evidence readability
- Privacy and compliance
- No-CTA default
- Canvas fit

Assign `通过`, `有条件通过`, or `不通过`.

Immediate `不通过` red lines:

- Invented product or service
- Fake case evidence
- Edited factual screenshot
- Redrawn or regenerated evidence
- AI-generated logo
- Cross-brand IP use
- Privacy leakage
- Unsupported result promise

## Prompt structure

When a prompt is requested, include:

1. Task definition
2. Canvas
3. Brand visual
4. Composition and layout
5. Image elements
6. Text plan
7. Original-material placement plan
8. Negative constraints

## Fixed planning output

When the user requests a plan rather than a finished poster, output these sections in order:

### 1. 海报定位

- 品牌
- 产品
- 类型
- 使用场景
- 目标
- 目标用户
- 信息来源状态

### 2. 营销策略

- 用户
- 核心痛点
- 购买动机
- 传播角度
- 信任阻力
- 阅读路径

### 3. 文案方案

- 标题
- 副标题
- 核心卖点
- 服务内容
- 信任证明
- 必要免责声明 / 边界说明

### 4. 视觉方案

- 比例
- 颜色
- 风格
- 第一视觉中心
- 布局
- 素材
- Logo、IP 与截图处理

### 5. 图片生成 Prompt

- 完整 Prompt
- 负向约束
- 后期合成说明

### 6. 检查结果

- 产品
- 品牌
- 文案
- 视觉
- 素材
- 合规
- 最终状态
- 待补资料 / 修改项

## Revision tasks

Preserve valid parts first. Regenerate the whole solution only when brand, product, poster type, usage goal, or real-material set changes. For a local change, update only affected areas and rerun QA.

Read [references/qa-checklist.md](references/qa-checklist.md) during execution, use [references/brand-guidelines.md](references/brand-guidelines.md) as the visual source of truth, and use [references/asset-manifest.md](references/asset-manifest.md) as the asset-ownership source of truth.
