---
name: product-detail-images
description: "Generate product detail-image sets for ecommerce and B2B product pages. Use when the user asks for product detail images, listing images, feature posters, SKU image sets, or says `详情图`, `产品详情图`, `主图详情页`, or `generate detail images` for a product URL, product brief, or product photos. This skill is for source-faithful image generation: lock product appearance from real reference photos, use confirmed features and specifications only, avoid invented product structure, and save ordered outputs such as `1.png` to `5.png`."
---

# Product Detail Images

## Overview

Generate a product detail-image set that stays faithful to real product photos and confirmed product facts. Build the set from reliable source content such as feature lists, specifications, product-page copy, user-provided briefs, and local reference photos. Do not invent claims, hardware, materials, certifications, performance numbers, or unsupported use cases.

Prerequisites:

1. A Codex environment with image generation support equivalent to `image2`.
2. A product URL, product ID, copied product content, or user-provided product brief.
3. User-provided product photos for appearance locking.
4. Optional brand, style, or benchmark images if the user has an established visual direction.

Default operational split:

1. First pass: collect the product facts, create a product-specific folder, and tell the user where to place appearance reference photos if they are missing.
2. Second pass: after reference photos are available, lock product appearance and generate the ordered detail-image set.

Before generating, inspect any accepted benchmark images or brand examples the user provides. If no benchmark exists, use the style rules in this skill instead of stopping.

## Workflow

1. Read the product page, product brief, or supplied source content.
2. Extract only confirmed features, specifications, materials, use cases, certifications, dimensions, and performance claims.
3. Create a product-specific folder in the current workspace immediately.
4. Tell the user to place product reference photos into that folder when they have not already done so.
5. Lock the authoritative product appearance from local product photos or the exact user-provided correction image.
6. Review any accepted benchmark set if available, then lock the target style direction before prompting.
7. Plan a distinct topic for each slide.
8. Generate the cover image first with `image2`.
9. Generate later slides one by one with `image2` as feature, benefit, detail, or application visuals.
10. Save the ordered set in the product-specific folder.
11. Skip long final QA by default; deliver the saved files after lightweight sanity checks.

## Gather Inputs

Collect these inputs before generating:

1. Product URL, product ID, copied product content, or product brief.
2. Product reference photos placed by the user into the product folder.
3. Confirmed product features.
4. Confirmed technical specifications or product attributes.
5. Any brand style direction, benchmark images, aspect ratio, language, image count, or marketplace requirements.
6. The exact appearance reference image if the user says `use this appearance`, `用这个外观`, or attaches a corrected product image.

Prefer user-provided source material over guesses. If the page has multiple content sections, use the most factual sections first: feature list, specification table, official product description, certification list, and product gallery captions.

## Fast Extraction Order

When the user gives only a product URL, use this fastest extraction order:

1. Fetch the product page HTML first instead of browsing manually.
2. Extract feature and benefit claims from factual page sections.
3. Extract technical specifications from tables, structured data, or clearly labeled attributes.
4. Extract the product name, model, SKU, or short slug and create the product folder in the current workspace.
5. Tell the user where to place product reference photos if no usable local photos exist.
6. Use a browser only when the page source and visible page seem inconsistent or the user already has the page open.

Do not treat vague marketing copy as a factual claim unless it is supported by specifications, product photos, or user confirmation.

## Default Execution Contract

When this skill is triggered by a request like `给这个产品做详情图` plus a product URL or product brief, treat the request as a direct production task.

Default behavior:

1. Do not stop after explaining the workflow.
2. Do not stop after listing extracted features and specifications.
3. Do not ask for confirmation just because the user provided only a URL or brief.
4. If no local product reference photos are available yet, create the folder, report the extracted content and folder path, and wait for the user to place photos there.
5. After reference photos are available, proceed from appearance lock to slide planning to image generation in the same turn whenever the source files are usable.
6. Default to exactly 5 output images unless the source material is weak or the user asked for a different count.
7. After generation, report the output folder. Do not include a long self-check unless the user asks for QA or points out a problem.

Only pause before generation when one of these is true:

1. Product appearance references are missing or insufficient.
2. Source facts are too thin to create a faithful detail-image set.
3. Reference photos conflict materially with a user-provided correction image.
4. The requested visual direction conflicts with the available product evidence.

## Optional Style Benchmark

If the user has accepted benchmark images, use them for layout, atmosphere, typography, color rhythm, and image pacing. If no benchmark is available, use these stable style traits:

1. Square or marketplace-appropriate poster format unless the user asks for another aspect ratio.
2. Clean commercial composition with high product readability.
3. Strong headline hierarchy with short, natural marketing copy.
4. One core selling point per feature slide.
5. Consistent typography, spacing, color accents, and icon style across the set.
6. Realistic usage, inspection, packaging, installation, service, lifestyle, or application context appropriate to the product.
7. No logo, brand mark, model number, SKU, certification badge, or marketplace badge unless the user explicitly asks and provides the asset or confirms the claim.

Use benchmark images for style only, never for copying product geometry, text, numbers, logos, or feature claims.

## Lock Product Fidelity

Apply these rules before planning slides:

1. Treat local product photos as the default highest-priority structure reference.
2. If the user supplies a corrected appearance image, treat it as higher priority than the folder defaults.
3. Keep the cover product depiction faithful to the real appearance.
4. Do not beautify, redesign, simplify, or upgrade the product.
5. Do not add unconfirmed screens, buttons, handles, panels, vents, ports, seams, accessories, labels, materials, colors, or variants.
6. If one local reference image conflicts with the user-provided correction image, follow the user-provided correction image.
7. Do not switch to manual cutout, pasted collage, or patch-edit assembly unless the user explicitly asks for image editing or compositing.

For physical products where structural accuracy matters, only `1.png` should show the full product body by default. Later slides should use verified partial details, contextual use scenes, safe feature visuals, process visuals, or application visuals. Show the full product again only when the user asks for marketplace gallery variants or when the product category naturally requires multiple full-product views.

## Plan The Slides

Default to 5 images unless the user asks for another count.

Use this slide structure:

1. `1.png`: cover image with the real product appearance and a strong product-category headline.
2. `2.png`: strongest confirmed feature or benefit.
3. `3.png`: second confirmed feature or benefit.
4. `4.png`: third confirmed feature, verified detail, or parameter-supported value point.
5. `5.png`: real-world application, service, packaging, installation, compatibility, or usage scenario grounded in the source facts.

Map slides `2.png` onward to confirmed points such as:

- material, finish, surface, or build quality
- capacity, size range, compatibility, adjustability, or fit
- safety, hygiene, protection, stability, locking, cooling, heating, sealing, or durability
- ease of cleaning, installation, maintenance, carrying, storage, or operation
- included accessories or verified components
- application scenarios supported by the source content

If the product only supports a few strong points, generate fewer images rather than padding the set.

Feature-priority rule:

1. Prefer confirmed feature lists and specification tables over generic promotional language.
2. Use specifications only to support wording or when a parameter directly strengthens a confirmed feature.
3. Do not turn random dimensions, power values, temperatures, capacities, or certifications into a slide unless they clearly support a real selling point.

## Style Rules

Match the selected product category and audience:

1. Use clean, commercial, high-contrast layouts.
2. Keep text short, readable, and natural in the requested language.
3. Use realistic product-relevant context rather than abstract effects when buyers need to understand real use.
4. Keep the full set visually consistent.
5. Prefer product-category-appropriate colors; use brand colors only when provided or confirmed.
6. Avoid logos, brand marks, product model names, SKU codes, badges, and certification icons unless explicitly confirmed.

Default visual direction:

- cover image: premium ecommerce poster with product-faithful appearance
- feature slides: clear headline, short support line, one main visual idea
- final slide: realistic application, service, installation, or usage scene

## Generation Method

Use `image2` or the available image generator as the default production method.

Execution rules:

1. Generate exactly one slide at a time.
2. Do not build the set through manual compositing, pasted cutouts, collage assembly, or patching old generated images unless the user explicitly asks for that workflow.
3. Do not treat the real product photo as a layer to paste onto a designed background by default.
4. When the cover slide fails, regenerate it from scratch with tighter structure constraints.
5. When a feature slide fails, regenerate that slide from scratch with a safer prompt.
6. Do not switch to editing-based repair unless the user explicitly asks for image editing.

## Later-Slide Restrictions

For `2.png` onward:

1. Do not invent product interiors, mechanisms, components, labels, ports, controls, or structural close-ups.
2. Partial-detail close-ups are allowed only when the exact detail is visible in local product photos, official gallery photos, or a user-provided correction image.
3. When verified detail photos exist, use those real details for relevant feature slides instead of replacing them with generic metaphors.
4. If a concrete product detail cannot be confirmed visually or textually, leave it out.
5. Use safe feature visuals, application scenes, material/process cues, usage context, packaging context, or verified partial details.
6. For products with specific safe-use rules, match the real usage shown or described by the source. Do not invent unsafe or unsupported use cases.

## Anti-Repetition Rules

During planning and generation, avoid repetition:

1. Do not reuse the same prop, background, angle, scene, or composition with only text changes.
2. Separate slides by topic, subject, perspective, mood, or use scenario.
3. If two slides feel interchangeable, regenerate one.

## Lightweight Sanity Checks

Before delivery, do only the minimum checks needed to avoid obvious mistakes:

1. Confirm files are saved with the requested numeric names.
2. Check for obvious misspellings, broken English, or awkward generated text.
3. Check that no image text includes unrequested logos, brand marks, model names, SKU codes, badges, or certifications.
4. Check that any concrete number, unit, material, compatibility claim, certification, capacity, or performance claim is confirmed in the current source material.

Do not perform or report a long final QA pass by default. If the user says a slide is wrong, reopen the relevant source image and generated image, compare them visually, and regenerate only the affected slide unless the user asks for a larger reset.

## Delivery

Save the set in a product-specific folder and use stable numeric names:

- `1.png`
- `2.png`
- `3.png`
- `4.png`
- `5.png`

If the user has an established workspace output folder, save there. Otherwise create a folder named after the product name, model, SKU, or short slug.

When helpful, also write a short `generation-notes.md` that records:

- source product URL or brief
- product name, model, or SKU
- confirmed features
- confirmed specifications or attributes
- image plan
- appearance-lock notes
- local reference files actually used

## Prompting Pattern

Generate one image at a time instead of asking for all slides in one prompt.

Before the first generation call, write a compact internal slide plan covering:

1. slide number
2. source feature
3. allowed visual subject
4. forbidden visual subject
5. headline text
6. support line text

For the cover image prompt:

1. State that the uploaded or referenced product photo is the exact appearance reference.
2. Call out critical structure constraints.
3. Describe the scene, typography, and copy layout.
4. Say what must not be changed.
5. Keep the composition aligned with any user-provided benchmark style, or with this skill's default commercial poster traits when no benchmark is available.
6. Explicitly say that this is a full image generation, not a composite edit.

For later slides:

1. Name the confirmed feature.
2. Describe a safe visual metaphor, application visual, process visual, or verified partial-detail close-up.
3. Define the headline, support line, and optional icon labels.
4. Prefer full new generation over edit-based repair.
5. Explicitly forbid unverified product interiors, invented hardware, unsupported use cases, and unconfirmed claims.
6. If using a product detail, name the exact local reference file that confirms it and instruct the generator to match that detail rather than improvising.

## Optional QA Gate

Use this full gate only when the user explicitly asks for QA, when a generated image appears structurally risky, or when fixing a user-reported problem:

1. The cover still matches the product reference photos used for this run.
2. Later slides map to distinct confirmed selling points, verified details, or application topics.
3. No slide repeats the same composition logic so closely that two slides feel interchangeable.
4. No copied numbers, units, specifications, or claims leaked from another product.
5. No broken English, misspellings, or awkward marketing phrases remain.
6. The set matches the selected style direction.
7. No generated image contains an unrequested logo, brand mark, model name, SKU code, badge, or certification.
8. Any later-slide product detail is visibly supported by reference photos and does not invent extra structure.

## Quick Response Pattern

When the user says something like:

- `给这个产品做详情图`
- `参考这个产品生成的图片`
- `用这个外观`
- `为这款产品生成详情图`
- `generate product detail images for this listing`

Do this:

1. Read the product page, brief, or supplied content and collect confirmed features and specifications.
2. Extract the product name, model, SKU, or slug and create the product folder in the current workspace.
3. Tell the user to place product reference photos into that folder if they are missing.
4. After the files are there, confirm the appearance source and any user correction image.
5. Review any accepted benchmark set if the user provides one; otherwise use this skill's default commercial poster traits.
6. Build the slide plan.
7. Generate and save the images one slide at a time.
8. Report the output folder without a long self-check. Let user feedback drive targeted fixes.

Do not stop after step 2 when the user has already placed the files. If the files are not there yet, stop after step 3 and wait for them.

## Stop Conditions

Stop and ask the user to redirect only when:

1. the product appearance reference is conflicting or unclear
2. product reference photos are missing or insufficient to lock the cover image
3. source facts are too weak to support a faithful image set
4. the user wants a visual direction that conflicts with available product evidence
