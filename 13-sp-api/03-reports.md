---
id: 03-reports
title: { ru: "SP-API: Reports API и типы отчётов", en: "SP-API: Reports API & report types" }
block: 13-sp-api
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [sp-api, reports, report-types, sales-traffic, listings, inventory, fba]
updated: 2026-11-14
sources:
  - { url: "https://developer-docs.amazon.com/sp-api/docs/reports-api-v2021-06-30-reference", kind: official, note: "Reports API" }
---

# SP-API: Reports API и типы отчётов / Reports API & report types

Асинхронные отчёты: создать → опросить статус → скачать. Основной источник массовых данных (листинги, продажи, остатки).

Async reports: create → poll → download. Primary bulk-data source (listings, sales, inventory).

---

## 1. Пайплайн / Pipeline

1. **`createReport`** — запросить отчёт (указать `reportType`, `marketplaceIds`, период).
2. **`getReport`** — статус: `IN_QUEUE` → `IN_PROGRESS` → `DONE` / `CANCELLED` / `FATAL`.
3. **`getReportDocument`** — скачать результат (TSV/CSV/JSON).

---

## 2. Типы отчётов / Report types

### Листинги и каталог / Listings & catalog

| reportType | Что даёт |
|---|---|
| `GET_MERCHANT_LISTINGS_ALL_DATA` | все листинги: SKU, ASIN, цена, остаток, статус |
| `GET_MERCHANT_LISTINGS_DATA` | активные листинги |
| `GET_MERCHANT_LISTINGS_INACTIVE_DATA` | неактивные |
| `GET_FLAT_FILE_OPEN_LISTINGS_DATA` | открытые листинги |
| `GET_MERCHANT_CANCELLED_LISTINGS_DATA` | снятые |

### Продажи и трафик / Sales & traffic

| reportType | Что даёт |
|---|---|
| `GET_SALES_AND_TRAFFIC_REPORT` | продажи + трафик по ASIN (за период, по дням) |

### Заказы / Orders

| reportType | Что даёт |
|---|---|
| `GET_FLAT_FILE_ORDERS_DATA` | заказы (плоский) |
| `GET_FLAT_FILE_ALL_ORDERS_DATA_BY_LAST_UPDATE_GENERAL` | все заказы по дате обновления |
| `GET_XML_ALL_ORDERS_DATA_BY_ORDER_DATE_GENERAL` | заказы XML |
| `GET_FLAT_FILE_ACTIONABLE_ORDER_DATA_SHIPPING` | actionable заказы |

### FBA: остатки, поставки, компенсации / FBA inventory, reimbursements

| reportType | Что даёт |
|---|---|
| `GET_FBA_INVENTORY_AGED_DATA` | возраст остатков FBA (aged) |
| `GET_FBA_MYI_UNSUPPRESSED_INVENTORY_DATA` | неутаённые остатки |
| `GET_FBA_MYI_ALL_INVENTORY_DATA` | все остатки |
| `GET_AMAZON_FULFILLED_SHIPMENTS_DATA_GENERAL` | FBA-отгрузки |
| `GET_FBA_ESTIMATED_FBA_FEES_TXT_DATA` | оценка FBA-комиссий |
| `GET_FBA_REIMBURSEMENTS_DATA` | компенсации (возвраты/потери) |

### Финансы / Finances

| reportType | Что даёт |
|---|---|
| `GET_V2_SETTLEMENT_REPORT_DATA_FLAT_FILE_V2` | расчёты/выплаты (settlement) |

---

## 3. Пример (Python-клиент из `S:\US AMAZON API`) / Example

`fetch_listings_report.py` использует `GET_MERCHANT_LISTINGS_ALL_DATA` → TSV/Excel (`exports/listings_all.tsv`). Подробности в `13-sp-api/04-catalog-items.md` и реальном клиенте `spapi_client.py`.

---

## 4. Особенности / Notes

- Отчёты **асинхронные**: между createReport и DONE — от секунд до минут (большие — дольше).
- `dataStartTime`/`dataEndTime` — период; для продаж и заказов обязателен.
- Результат — TSV (по умолчанию) или CSV/JSON; большие файлы — через `getReportDocument` (URL для скачивания).
