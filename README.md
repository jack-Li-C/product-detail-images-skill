# Product Detail Images Skill

Codex skill for generating source-faithful product detail-image sets for ecommerce and B2B product pages.

## What It Does

- Extracts product selling points from confirmed features, specifications, and product-page content.
- Uses product photos as appearance references.
- Generates an ordered detail-image set such as `1.png` to `5.png`.
- Keeps the cover product-faithful and avoids invented product details on later slides.
- Supports optional benchmark images or brand style direction.

## Install

Clone this repository, then copy the skill folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R product-detail-images ~/.codex/skills/
```

Restart Codex or open a new thread so the skill can be discovered.

## Use

In Codex, ask for the skill by name:

```text
Use $product-detail-images to create detail images for this product URL:
https://example.com/product/example-product/
```

The workflow expects the user to provide product facts and place product reference photos into the product folder that Codex creates before image generation begins.

## Requirements

- Codex with image generation support equivalent to `image2`.
- A product URL, copied product page content, or product brief.
- Product reference photos for the target item.
- Optional benchmark images if you want to match a specific house style.

## Repository Layout

```text
.
├── README.md
└── product-detail-images/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```

Only the `product-detail-images/` folder is the installable Codex skill.

## License

Choose and add a license before publishing as a public reusable project. For broad reuse, MIT is a common lightweight choice.
