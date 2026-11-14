---
id: 02-api-domains
title: { ru: "SP-API: домены и rate limits", en: "SP-API: domains & rate limits" }
block: 13-sp-api
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [sp-api, domains, api, rate-limit, listings-items, feeds, orders, reports, catalog-items, fba, notifications]
updated: 2026-11-14
sources:
  - { url: "https://developer-docs.amazon.com/sp-api/docs", kind: official, note: "SP-API docs" }
---

# SP-API: домены и rate limits / Domains & rate limits

Обзор всех API-доменов SP-API (по состоянию на 2026) и принцип лимитов.

Overview of SP-API domains (as of 2026) and the rate-limit model.

---

## 1. Домены / Domains

| Домен (API) | Версия | Назначение |
|---|---|---|
| **Listings Items** | 2021-08-01 | читать/писать листинги (put/patch/delete/get) |
| **Product Type Definitions** | 2020-09-01 | схемы атрибутов (PTD) для типа товара |
| **Feeds** | 2021-06-30 | массовые загрузки (`JSON_LISTINGS_FEED`) |
| **Product Pricing** | v0 | цены: `getPricing`, `getCompetitivePricing`, `getListingOffers`, `getItemOffers` |
| **Orders** | v0 | заказы и позиции |
| **Reports** | 2021-06-30 | отчёты (listings, sales & traffic, inventory) |
| **Catalog Items** | 2022-04-01 | каталог: EAN/UPC/ASIN → товар (поиск, атрибуты, вариации) |
| **FBA Inventory** | v1 | остатки FBA, aged inventory |
| **FBA Inbound** | 2024-03-20 | создание поставок на склады |
| **FBA Outbound** | 2020-10-01 | вывод/removal |
| **Merchant Fulfillment** | v0 | FBM: метки, доставка |
| **Sales** | v1 | сводки продаж (order metrics) |
| **Finances** | 2024-06-19 | финансовые события/выплаты |
| **Notifications** | v1 | подписки на события (подписка на изменения) |
| **Tokens** | 2021-03-01 | **RDT** (Restricted Data Token для PII) |
| **Authorization** | v1 | проверка доступных разделов/ролей |

---

## 2. Rate limits / Лимиты

- Каждый operation имеет **rate** (запросов/сек) и **burst**.
- Фактический лимит возвращается в заголовке `x-amzn-RateLimit-Limit`.
- 429 → превышение; клиент делает retry с backoff.

**Проверенные лимиты (из официальных моделей):**

| Операция | Rate / Burst |
|---|---|
| `getListingsItem` | 5 / 10 |
| `putListingsItem` | 5 / 10 |
| `patchListingsItem` | 5 / 5 |
| `deleteListingsItem` | 5 / 5 |
| `getPricing` | 0.5 / 1 |
| `getCompetitivePricing` | 0.5 / 1 |

> Остальные — `[unverified]`, сверять с `x-amzn-RateLimit-Limit` или официальным Usage Plans (высокие лимиты можно запросить под бизнес-потребность).

---

## 3. Типичный стек для твоих задач / Typical stack for your needs

| Задача | Домен |
|---|---|
| Выгрузка заказов | Orders → `getOrders` + `getOrderItems` |
| Выгрузка листингов с ценами/остатками | Reports (`GET_MERCHANT_LISTINGS_ALL_DATA`) или Listings Items |
| Обновление цены/остатков/текстов | Listings Items `patchListingsItem` / Feeds |
| Parent/child вариации | Listings Items `putListingsItem` (relationship) |
| EAN → ASIN | Catalog Items `searchCatalogItems` |
| Цены конкурентов | Product Pricing `getCompetitivePricing` |
| PII (имя/адрес) | Orders + **RDT** (Tokens) |
| Реклама | **Ads API** (отдельный доступ, см. `07-advertising`) |

---

## 4. Ошибки и повторы / Errors & retries

- **429** — лимит → backoff + retry.
- **5xx** — Amazon временно → retry.
- **403** — доступ запрещён (роль/scope).
- **400** — невалидный запрос (код `BAD_REQUEST`).
- **401** — невалидный токен (обновить access token).
