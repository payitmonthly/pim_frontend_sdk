# PayItMonthly Widget — Frontend SDK

A lightweight, zero-dependency embed widget that lets you display a **Buy Now, Pay Monthly** financing banner on any product page. When clicked, it opens a payment calculator modal so customers can explore instalment options before checkout.

---

## Quick Start

Add a placeholder `<div>` where you want the widget to appear, then load the script with your product price:

```html
<div data-acpim-widget></div>

<script async type="module"
  src="https://payitmonthly.github.io/pim_frontend_sdk/pim-widget.js"
  data-pim-price="1499"
  data-pim-max-instalments="12">
</script>
```

That's it. The widget mounts itself into the placeholder and is ready to use.

> **No placeholder?** If you omit the `<div data-acpim-widget></div>`, the widget inserts itself directly before the `<script>` tag instead.

---

## Configuration

All options are set as `data-*` attributes on the `<script>` tag.

| Attribute | Type | Default | Description |
|---|---|---|---|
| `data-pim-price` | number | `2985` | The product price in £. Drives the payment calculator. |
| `data-pim-max-instalments` | number | `24` | Maximum number of monthly instalments offered. |

### Example — custom instalment cap

```html
<div data-acpim-widget></div>

<script async type="module"
  src="https://payitmonthly.github.io/pim_frontend_sdk/pim-widget.js"
  data-pim-price="799"
  data-pim-max-instalments="6">
</script>
```

---

## Multiple Widgets on One Page

Each script tag is independent, so you can embed the widget multiple times on the same page — for example on a category listing page with different product prices.

```html
<!-- Product A -->
<div data-acpim-widget></div>
<script async type="module"
  src="https://payitmonthly.github.io/pim_frontend_sdk/pim-widget.js"
  data-pim-price="1200"
  data-pim-max-instalments="12">
</script>

<!-- Product B -->
<div data-acpim-widget></div>
<script async type="module"
  src="https://payitmonthly.github.io/pim_frontend_sdk/pim-widget.js"
  data-pim-price="3500"
  data-pim-max-instalments="24">
</script>
```

Each instance is scoped with a unique ID to prevent style or DOM conflicts.

---

## How It Works

1. **Banner** — A compact banner renders in place of the `[data-acpim-widget]` placeholder, showing the price split across the default number of instalments.
2. **Modal** — Clicking the banner opens a full-screen overlay with a payment calculator. Customers can drag the instalment slider to see how the monthly payment changes.
3. **Checkout prompt** — The modal reminds customers to select PayItMonthly in the Payment section at checkout.

---

## Browser Support

Works in all modern browsers (Chrome, Firefox, Safari, Edge). Uses ES modules (`type="module"`), so IE11 is not supported.

---

## Legal

PayItMonthly is unregulated credit. 18+, UK only. Credit subject to status. Late or missed payments may impact your ability to get credit in future. T&Cs apply — see [payitmonthly.uk/terms](https://payitmonthly.uk/terms).
