# EarlyLore catalog snapshot

A small, dated snapshot of the product catalog behind [EarlyLore](https://earlylore.com) (中文: <https://earlylore.com/zh/>). EarlyLore helps founders and independent makers research real SaaS products before they build, and keeps the source and observation date next to each fact.

EarlyLore is in research preview. This repository holds **data and method only**. The EarlyLore product source is not published here.

## What is in it

- `data/snapshots/2026-07-28.json` holds **76 products in 7 categories**, observed on **2026-07-28**.
- `data/latest.json` is the newest snapshot (currently the same file).
- [docs/methodology.md](docs/methodology.md) explains how records are built and what they can and cannot support.
- [CHANGELOG.md](CHANGELOG.md) lists dataset changes.

**Freshness:** every record was observed on 2026-07-28 and has **not been re-verified since**. Websites and pricing may have changed. Check the product's official site before relying on a field.

## Categories

| slug | name (zh) | products |
|---|---|---|
| `assistants` | AI 助手 | 17 |
| `research` | 搜索与研究 | 15 |
| `developer` | 编程与开发 | 24 |
| `design` | 图像与设计 | 20 |
| `audio-video` | 音频与视频 | 17 |
| `productivity` | 效率与协作 | 32 |
| `automation` | 自动化 | 16 |

A product can be in more than one category, so the counts add up to more than 76.

## Record fields

| Field | Type | Meaning |
|---|---|---|
| `id` | string | Stable EarlyLore catalog ID, e.g. `earlylore:claude` |
| `slug` | string | URL-safe name |
| `name` | string | Product name |
| `maker` | string | Company or brand that makes the product (no individuals) |
| `summary` | string (zh) | One-line description written by EarlyLore |
| `description` | string (zh) | Short description written by EarlyLore |
| `websiteUrl` | string | Official product website |
| `domain` | string | Host of `websiteUrl` |
| `pricing` | string (zh) | Pricing model label (see below), not a price |
| `categorySlugs` | string[] | Category slugs from the table above |
| `addedAt` | date | Date the product entered the catalog |
| `verifiedAt` | date | Date the record was last checked against its official source |
| `observedAt` | date | Observation date of the record (latest `sourceRecords[].observedAt`) |
| `sourceRecords` | object[] | `kind` (`official_website`), `url`, `observedAt` |

Pricing labels: `免费` = free, `免费增值` = freemium, `免费试用` = free trial, `付费` = paid. Counts in this snapshot: freemium 64, paid 5, free trial 5, free 2.

Example record:

```json
{
  "id": "earlylore:claude",
  "slug": "claude",
  "name": "Claude",
  "maker": "Anthropic",
  "summary": "适合长文本、代码与复杂推理的通用 AI 助手。",
  "description": "Claude 覆盖对话、文档理解、写作和代码任务，并以 Projects、Artifacts 等能力承接持续工作。",
  "websiteUrl": "https://claude.ai/",
  "domain": "claude.ai",
  "pricing": "免费增值",
  "categorySlugs": [
    "assistants",
    "research",
    "developer"
  ],
  "addedAt": "2026-07-28",
  "verifiedAt": "2026-07-28",
  "observedAt": "2026-07-28",
  "sourceRecords": [
    {
      "kind": "official_website",
      "url": "https://claude.ai/",
      "observedAt": "2026-07-28"
    }
  ]
}
```

## License and attribution

The data and text in this repository are licensed under [CC BY 4.0](LICENSE). Please attribute **"EarlyLore (earlylore.com)"** and link to <https://earlylore.com>. Product names and trademarks belong to their owners.

## 中文

这是 [EarlyLore](https://earlylore.com/zh/) 产品目录的一份带日期快照：7 个分类共 76 个产品，观察日期均为 **2026-07-28**，之后**没有重新核验**，使用前请以产品官网为准。每条记录都附官方来源和观察日期，`pricing` 只是定价模式标签，不是价格。数据与文字按 CC BY 4.0 授权，引用时请注明 "EarlyLore (earlylore.com)" 并链接回 <https://earlylore.com/zh/>。EarlyLore 产品源码不在本仓库。

— Kai
