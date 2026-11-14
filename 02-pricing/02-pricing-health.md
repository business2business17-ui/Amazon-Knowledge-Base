---
id: 02-pricing-health
title: { ru: "Цены: Pricing Health и бенчмарки", en: "Pricing: Pricing Health & benchmarks" }
block: 02-pricing
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [pricing, pricing-health, reference-price, featured-offer, automate-pricing, sale-price, benchmark]
updated: 2026-11-14
source: { kind: forum+official, note: "из официального поста Amazon на Seller Forums (ноябрь 2026)" }
---

# Pricing Health и бенчмарки / Pricing Health & benchmarks

Инструмент **Pricing Health** (Seller Central) и эталонные цены, по которым Amazon принимает решения о Featured Offer и деактивации. Источник — официальный пост Amazon на Seller Forums (ноябрь 2026).

The **Pricing Health** tool and the reference prices Amazon uses for Featured Offer and deactivation decisions.

---

## 1. Три сигнала Pricing Health / Three signals

| Сигнал | Смысл | Действие |
|---|---|---|
| **Deactivated offers** | листинг снят из-за ценовой ошибки (напр. цена упала ниже заданного минимума) | пересмотреть цену → реактивировать |
| **Featured Offer disqualified** | total price (цена+доставка) выше конкурентной внешней цены ИЛИ заметно выше недавних цен | снизить total price |
| **Offers close to Featured Offer** | в пределах **5%** от Featured Offer | малое изменение → выигрыш Buy Box |

---

## 2. Reference prices (эталоны) / Reference prices

Pricing Health показывает несколько бенчмарков:

- **Featured Offer price** — текущая цена Featured Offer.
- **60-day average selling price** — средняя цена продажи за 60 дней.
- **Typical price (90-day median)** — типичная цена (медиана за 90 дней).
- Конкурентная **внешняя** цена (другие маркетплейсы) — причина disqualified.

---

## 3. Dispute reference price / Оспаривание эталона

- Если эталон устарел/неверен → **dispute через Seller Assistant** (Seller Central).
- **Авто-разрешение ~30 минут** (раньше — только эскалация через кейс).
- Ключевой лайфхак при волне «Potential High Pricing Error» (см. `12-lifehacks/02-forum-2026.md`).

---

## 4. Automate Pricing / Автоматизация цен

- Правило **«competitive price»**: автоматически держит `min(конкурентная внешняя цена, Featured Offer цена)`.
- Ты задаёшь только **floor** (нижнюю границу); остальное — Amazon.
- Полезно на BFCM при быстрых сдвигах цен.

---

## 5. Sale Price в новом UI / Sale Price in new UI

- `[forum 2026]` В новом Seller Central **убрана секция Sale Price** — задавай `sale_price` через **фид / SP-API** (`sale_price` со `schedule`), пока Amazon не вернёт поле.

---

## 6. Featured Offer percentage / Доля Featured Offer

- Отслеживай в **Business Reports → Detail Page Sales and Traffic (by Child Item)** → график Featured Offer % по времени.

---

## 7. Итог / Summary

Градации цен (Min/Max/Sale/List/MAP) — `01-price-gradients.md`; здоровье цены и Featured Offer — здесь. Формула корректной прогрузки:

```
minimum_price ≤ sale_price ≤ your_price ≤ list_price
your_price ≥ minimum_advertised_price (MAP)
your_price ≤ maximum_price
+ следи за Pricing Health (deactivated / disqualified / within 5%)
```
