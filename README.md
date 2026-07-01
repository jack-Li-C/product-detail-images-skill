# Product Detail Images for Codex

Generate source-faithful product detail image sets for ecommerce and B2B product pages with Codex.

This plugin helps Codex turn a product URL, product brief, specifications, and real product reference photos into an ordered image set such as `1.png` to `5.png`. It is designed for product marketers, ecommerce operators, manufacturers, and agencies who need feature posters without invented product details or unsupported claims.

If this helps your product-image workflow, please star the repo.

## Why Use It

- Locks product appearance from real reference photos.
- Uses confirmed features and specifications only.
- Plans one clear selling point per detail image.
- Avoids invented hardware, labels, certifications, materials, and use cases.
- Saves ordered outputs such as `1.png`, `2.png`, `3.png`, `4.png`, `5.png`.
- Works for ecommerce listings, B2B product pages, feature posters, and SKU image sets.

## Install As A Codex Plugin

Add this repository as a Codex plugin marketplace:

```bash
codex plugin marketplace add jack-Li-C/product-detail-images-skill
```

Then open Codex Plugins, choose the `Product Detail Images Skill` marketplace, and install `Product Detail Images`.

After installation, start a new Codex thread and ask:

```text
Use $product-detail-images to create detail images for this product URL:
https://example.com/product/example-product/
```

## Manual Skill Install

If you only want the raw skill folder, copy it into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R plugins/product-detail-images/skills/product-detail-images ~/.codex/skills/
```

Restart Codex or open a new thread so the skill can be discovered.

## Inputs It Expects

- Product URL, copied product page content, or product brief.
- Product reference photos for appearance locking.
- Confirmed features, specifications, materials, certifications, and use cases.
- Optional brand style, benchmark images, aspect ratio, language, or marketplace requirements.

## Example Requests

```text
Use $product-detail-images to make a 5-image detail set for this product page.
```

```text
Use $product-detail-images with these product photos and specs. Keep the product structure faithful.
```

```text
Use $product-detail-images to plan and generate ecommerce feature posters from this listing.
```

## Repository Layout

```text
.
├── .agents/plugins/marketplace.json
├── plugins/product-detail-images/
│   ├── .codex-plugin/plugin.json
│   └── skills/product-detail-images/
│       ├── SKILL.md
│       └── agents/openai.yaml
├── LICENSE
└── README.md
```

## Chinese Summary

这是一个 Codex 产品详情图生成插件。它会根据产品链接、产品资料、规格参数和真实产品参考图，规划并生成一组有顺序的详情图，例如 `1.png` 到 `5.png`。核心目标是保持产品外观真实、卖点来源可靠、不虚构结构、不乱加认证和参数。

安装后可以这样调用：

```text
Use $product-detail-images to create detail images for this product URL or brief.
```

## License

MIT
