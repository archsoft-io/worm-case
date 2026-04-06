# 🪱 Worm Case

[![pt-br](https://img.shields.io/badge/lang-pt--br-green)](README.pt-br.md)

**Worm Case** is a semantic naming convention designed to organize information with multiple dimensions. It uses a **Rhythmic Segmentation** structure to ensure clarity, scannability, and logical ordering.

The metaphor behind the name comes from the movement of a worm: it crawls along the **ground** and leaps in an **arc** to move forward. From this image, **Wormy** 🪱 was born — the official mascot of the convention. Just like him, Worm Case stretches to accommodate long names and contracts for short ones, always keeping its feet on the ground to know exactly where each piece of information begins and ends.

And that is precisely where the logic of the pattern lies:

| Character | Name | Role |
|-----------|------|------|
| `_` (Underscore) | **Ground** | The soil where Wormy crawls. Separates **Segments** — the transition between different contexts or metadata (categories, dates, scopes). |
| `-` (Hyphen) | **Arc** | Wormy's leap over the surface. Separates **Words** within the same segment, preserving the semantic unity of a phrase or title. |

## 🚀 Origin and Motivation

Worm Case was born from the need to catalog and organize files so that the **alphabetical sorting of the operating system** works in the user's favor.

### Why not `kebab-case` or `snake_case`?

In traditional conventions, all separators are identical — making it impossible to visually distinguish where one context ends and another begins:

```
kebab-case:   report-annual-sales-2025-final.pdf
snake_case:   report_annual_sales_2025_final.pdf
```

The eye has to **read the entire name** to understand its structure. There is no visual hierarchy — every separator looks the same.

With Worm Case, different separators create **distinct visual layers**, and the structure becomes immediately scannable:

```
worm_case:    report_annual-sales_2025_final.pdf
              ──┬──  ─────┬──── ──┬─  ──┬──
              Type    Subject   Year  State
```

When listing files, the system groups first by **Type**, then by **Subject**, and finally by **Version/Year** — all thanks to the visual rhythm between `_` and `-`.

## 📖 Anatomy of a Name

A Worm Case name is composed of **Segments** — the building blocks of information:

| Part | Name | Description | Example |
|------|------|-------------|---------|
| Segment 1 | **Context / Type** | Defines "The What" (main category) | `book`, `api`, `feat` |
| Segment 2 | **Subject / Body** | Defines "About What" (content) | `software-engineering` |
| Segment 3 | **Attribute / Tail** | Defines "The Detail" (version, date, state) | `2026`, `v1`, `final` |

## 🎨 Style Variations

Worm Case adapts to different coding conventions through three variations:

### 1. Lower Worm Case (Standard)

The original form, recommended for **file systems** (Windows/Linux/macOS). Uses only lowercase letters to avoid case-sensitivity conflicts.

```
book_software-engineering_2ed.pdf
```

### 2. Upper Worm Case (Scream)

Ideal for **programming constants**, **environment variables** (`.env`), and **global configurations**.

```
API_TIMEOUT_30-SECONDS
```

### 3. Pascal Worm Case (Mixed)

Maintains the elegance of Pascal Case within each segment while preserving the context separation of Worm Case.

```
Profile_Settings
```

## 🛠️ Technical Specification (Regex)

To validate or implement Worm Case in linters and automation tools:

```regex
^[a-z0-9]+(-[a-z0-9]+)*(_[a-z0-9]+(-[a-z0-9]+)*)*$
```

> **Note:** this regex validates **Lower Worm Case** (standard). Adapt accordingly for other variations.

## 📄 License

This project is licensed under the [MIT License](LICENSE).