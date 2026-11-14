---
id: 02-fba-fees
title: { ru: "Логистика: FBA-комиссии детально", en: "Logistics: FBA fees in detail" }
block: 10-logistics
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [fba, fees, referral, fulfillment, storage, aged-inventory, removal, inbound-placement, low-inventory]
updated: 2026-11-14
---

# FBA-комиссии детально / FBA fees in detail

Полная структура комиссий Amazon при FBA. **Все ставки меняются — сверяй с FBA Revenue Calculator перед расчётом маржи.**

Full FBA fee structure. **All rates change — verify with the FBA Revenue Calculator before margin calc.**

---

## 1. Виды комиссий / Fee types

| Комиссия | Когда | Основа расчёта |
|---|---|---|
| **Referral fee** | с каждой продажи | % от цены (по категории, обычно 8–15%) |
| **Fulfillment fee** | за хранение/упаковку/доставку | размерный тир (size tier) + вес |
| **Monthly storage** | за хранение на складе | $ за куб. фут в месяц (Q4 дороже) |
| **Aged inventory surcharge** | товар > 180 дней | доп. за куб. фут |
| **Removal / disposal** | вывод/утилизация | за единицу |
| **Inbound placement** | распределение по складам | за единицу (новая схема) |
| **Low-inventory-level fee** | низкий остаток | за единицу (новая) |
| **Returns processing fee** | возвраты (некоторые категории) | за возврат |

---

## 2. Размерные тиры (fulfillment) / Size tiers

- Тир зависит от **размера + веса** упакованного товара.
- Крупные тиры: small standard → large standard → small oversize → medium/large oversize → special oversize.
- **Dimensional weight** применяется для крупных/лёгких.

---

## 3. Сезонность хранения / Storage seasonality

- **Q4 (октябрь–декабрь)** storage дороже (обычно ~×2.4 к январю–сентябрю).
- **Aged (>180 дней)** — доп. надбавка сверху базового storage.

---

## 4. Новая схема inbound placement / Inbound placement

- Amazon предлагает **«минимальный split»** (дороже, меньше складов) или **«оптимизированный split»** (дешевле, больше складов).
- Комиссия зависит от выбора split и объёма. `[unverified]`

---

## 5. Экономика (реальный ориентир) / Real economics

- `[forum 2026]` Селлеры сообщают: **FBA fees ≈ 40–48%** от цены + **реклама ≈ 20%** → **60–68% уходит Amazon**. Прибыль — при массовых продажах, высокой марже или FBM/своей логистике.

---

## 6. Расчёт / Calculation

- **FBA Revenue Calculator** (Seller Central) — точный расчёт на SKU: введи цену + размеры/вес → полная комиссия + маржа.
- Свои формулы: `shared/amazon/pricing_engine.py` и `margin_calc.py` в репо `Agents`.
