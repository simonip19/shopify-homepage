## Overview

The implementation includes custom sections for the header, hero banner, promotional columns, overlapping image/text content, and USP content. Each section is designed to be reusable and configurable through the Shopify theme editor wherever appropriate.

The main development approach was to avoid hardcoded content, keep styling modular, and use Shopify section schema settings so merchants can manage images, text, links, layout options, and spacing without needing code changes.

## New Sections and CSS Files

| Section file | Associated CSS file | Purpose |
| --- | --- | --- |
| `sections/custom-header.liquid` | `assets/section-custom-header.css` | Custom store header with logo, navigation, search, account links, cart, mobile hamburger menu, and highlighted menu item support. |
| `sections/custom-hero-banner.liquid` | `assets/section-hero-banner.css` | Full-width hero banner with page-width aligned content, responsive image behavior, CTA button blocks, and mobile overlapping content card. |
| `sections/custom-promo-columns.liquid` | `assets/section-custom-promo-columns.css` | Promotional image columns with merchant-editable blocks, image, heading, text, links, and mobile stacking behavior. |
| `sections/custom-overlapping-image-text.liquid` | `assets/section-overlapping-image-text.css` | Full-width image section with overlapping page-width aligned content on desktop and relative stacked content on mobile. |
| `sections/custom-usp.liquid` | `assets/section-custom-usp.css` | USP/content section for highlighting key value propositions or supporting marketing content. |


## Development Notes

### Section Architecture

Each major design block has been developed as a standalone Shopify section. This keeps the theme modular and easier to maintain. Instead of creating one large static template, the page can be assembled from reusable sections in the theme editor.

### CSS Organization

CSS has been separated into dedicated files under the `assets` directory. This keeps Liquid files cleaner and makes each section easier to debug or modify.

Example:

```liquid
{{ 'section-custom-hero-banner.css' | asset_url | stylesheet_tag }}
