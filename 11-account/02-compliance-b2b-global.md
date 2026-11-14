---
id: 02-compliance-b2b-global
title: { ru: "Аккаунт: compliance, B2B, Global Selling", en: "Account: compliance, B2B, Global Selling" }
block: 11-account
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [compliance, epr, weee, ukca, ce, saber, ecas, vat, oss, ioss, b2b, amazon-business, global-selling, bil]
updated: 2026-11-14
---

# Compliance, Amazon Business (B2B), Global Selling / Compliance, B2B, Global Selling

Углубление по соответствию требованиям по рынкам + две крупные программы.

Compliance deep-dive by market + two major programs.

---

## 1. Compliance по рынкам / Compliance by market

| Рынок | Требования |
|---|---|
| **US** | sales tax (Amazon собирает), FTC-маркировка, CPSC/CPSIA (детские/игрушки) |
| **UK** | **UKCA** (вместо CE для ряда товаров), GB VAT |
| **DE** | CE + **EPR** (упаковка/LUCID, WEEE, батарейки/BattG) + OSS VAT |
| **FR** | CE + EPR (упаковка/Triman, WEEE, текстиль, мебель) + OSS |
| **IT/ES/NL/SE/PL/BE** | CE + EPR (по стране) + OSS/IOSS |
| **TR** | местный KDV (VAT 20%), местная маркировка `[unverified]` |
| **AE** | GCC-маркировка, VAT 5% `[unverified]` |
| **SA** | **SABER/ECAS** сертификация, GCC-маркировка, VAT 15% `[unverified]` |

**EPR** (Extended Producer Responsibility) — регистрация производителя/импортёра по упаковке, электронике (WEEE), батарейкам. Жёстче всего в **DE** и **FR** (без номера — блокировка листингов).

**VAT:** EU — регистрация по каждой стране хранения + **OSS** (one-stop) для трансграничных продаж; **IOSS** для импортных посылок ≤150 EUR. MENA — свой VAT (AE 5%, SA 15%).

---

## 2. Amazon Business (B2B) / Amazon Business

- Продажа **бизнес-покупателям** (не только розница).
- Возможности: **Business Price** (отдельная B2B-цена), **quantity discounts** (PERCENT/FIXED), business-only offers, VAT-инвойсы (EU).
- В API: offer `offerType=B2B`, `businessPrice`, `quantityDiscountPlan` (см. `02-pricing`, `07-advertising`).
- Требует: Professional-план + включение B2B-предложения.

---

## 3. Global Selling / Build International Listings (BIL) / Глобальные продажи

- **Global Selling** — выход на другие рынки из одного аккаунта (US → UK/EU/MENA).
- **BIL (Build International Listings)** — автоматическая **синхронизация листингов** между marketplaces (перевод title/bullets, общие SKU).
- Локализация: перевод ключей/текста на локальный язык (не транслит) — см. `03-seo`, `00-markets`.
- Нюансы: VAT/EPR регистрация по каждой стране, локальная валюта, локальные требования (SA SABER и т.д.).

---

## 4. Сводка «что проверить перед выходом на рынок» / Pre-entry checklist

1. VAT-регистрация (EU/MENA) или налоговая настройка (US).
2. EPR/упаковка (DE/FR обязательно).
3. Compliance товара (CE/UKCA/SABER/CPSC — по категории).
4. Локализация листинга (язык, ключи).
5. FBA-склад в стране (для Prime) или FBM/EFN.
6. Brand Registry (для A+/Store/SB).
