# skills

Open render skills for turning product photos into best-in-class 3D renders.

Each skill is a short, category-specific brief that [easyrender.ai](https://easyrender.ai) adds to the angle-sheet prompt. It tells the image model what usually goes wrong for that kind of product (invented details, lost reflections, flattened materials) and to keep what the photo shows. Use them with any image model or agent; they are plain Markdown.

| Skill | For |
| --- | --- |
| `general` | Fallback for anything else |
| `furniture` | Chairs, sofas, tables, lamps, rugs |
| `jewelry` | Rings, necklaces, watches |
| `apparel` | Clothing, footwear, hats |
| `bags` | Bags, wallets, leather goods |
| `electronics` | Phones, speakers, laptops, cameras |
| `glass` | Glass, ceramics, bottles |

## Layout

- `skills.json` is the index the app reads: `id`, `label`, `keywords` (English and Spanish, matched against the product name and note) and the path of the skill file.
- `skills/<id>/SKILL.md` holds the guidance as the body, under a small front matter block.

The app fetches `skills.json` and the files at runtime and caches them for five minutes. If this repo cannot be reached, it uses the copy bundled in the app, so edits here go live without a deploy and an outage here stops nothing.

## Contributing

Add a folder under `skills/`, add it to `skills.json`, and keep the guidance to two or three sentences that name what must be preserved. Skills describe products only; the turnaround layout, model settings and quality checks live elsewhere.

MIT licensed.
