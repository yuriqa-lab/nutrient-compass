# 栄養コンパス — Nutrient Compass

**Live site:** <https://yuriqa-lab.github.io/nutrient-compass/>

![栄養コンパス](./docs/screenshot.png)

A Japanese-first, local-first food-and-nutrition exploration tool. Select one or
more wellness themes to see related nutrients, reference food portions, and
rotating ingredient and dish ideas.

気になるテーマを選ぶと、関連する栄養素、食品に含まれる量の目安、
日替わりの食材・料理アイデアを確認できる、ローカル完結の探索ツールです。

## Features

- 18 selectable food and wellness themes
- 27 nutrient and food-reference entries
- Multi-theme ingredient matching
- Date-seeded daily rotation
- Shareable theme presets via URL, for example `?goals=gray,skin,eyes`
- Local-only preference storage
- No AI API, account, analytics, or tracking

## How the matching works

The app encodes relationships between themes, nutrients, and foods as editorial
data. Values from 1–3 indicate relative relevance inside this prototype; they
are **not** clinical effect sizes, diagnoses, treatment recommendations, or
personalized nutrition advice.

1. Selected themes contribute relevance weights to related nutrients.
2. Foods are ranked by how many of those nutrient themes they overlap with.
3. A date-seeded rotation varies the displayed ideas without changing on reload.

The scoring is intentionally inspectable and rule-based.

## Reference basis and limitations

Where public daily-reference values are established, the app uses general
references informed by the
[Dietary Reference Intakes for Japanese (2025)](https://www.mhlw.go.jp/stf/seisakunitsuite/bunya/kenkou_iryou/kenkou/eiyou/syokuji_kijyun.html).
Food composition values are approximate and informed by the
[Standard Tables of Food Composition in Japan](https://www.mext.go.jp/a_menu/syokuhinseibun/mext_01110.html).

Values vary by age, sex, product, variety, portion, and preparation. The app
does not diagnose deficiencies or account for allergies, medications,
pregnancy, or medical conditions. It provides general food information, not
medical advice. See also the
[Consumer Affairs Agency guidance on health-food information](https://www.caa.go.jp/policies/policy/consumer_safety/food_safety/food_safety_portal/health_food/).

## Privacy and storage

Selections are stored only in this browser's `localStorage`. The app has no
backend, accounts, analytics, advertising, or tracking and makes no application
network requests.

## Technology and development

Plain HTML, CSS, and JavaScript. No build step or runtime dependencies.

Open `index.html` in a browser, or serve the directory statically:

```bash
python3 -m http.server 8000
```

## Development provenance

Implementation used AI-assisted pair programming. Yuriqa Lab directed the
product, reviewed the code and content, and performed release testing.

## License

[MIT](./LICENSE) © Yuriqa Lab
