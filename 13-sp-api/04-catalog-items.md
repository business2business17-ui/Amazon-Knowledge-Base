---
id: 04-catalog-items
title: { ru: "SP-API: Catalog Items (EAN→ASIN, атрибуты)", en: "SP-API: Catalog Items (EAN→ASIN, attributes)" }
block: 13-sp-api
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [sp-api, catalog-items, ean, upc, asin, gtin, attributes, variations, search]
updated: 2026-11-14
sources:
  - { url: "https://developer-docs.amazon.com/sp-api/docs/catalog-items-api-v2022-04-01-reference", kind: official, note: "Catalog Items API v2022-04-01" }
---

# SP-API: Catalog Items (EAN→ASIN, атрибуты) / Catalog Items

Поиск товара в каталоге Amazon по GTIN/ASIN/ключевым словам, чтение атрибутов и вариаций. Нужен для резолва EAN→ASIN и brand→ASIN.

Catalog search by GTIN/ASIN/keywords, read attributes and variations. Needed for EAN→ASIN and brand→ASIN resolution.

---

## 1. Операции / Operations

| Операция | Назначение |
|---|---|
| `searchCatalogItems` | поиск по **идентификаторам** (EAN/UPC/ISBN/ASIN) или ключевым словам |
| `getCatalogItem` | получить товар по **ASIN** (атрибуты, изображения, вариации, salesRanks) |

---

## 2. Резолв EAN → ASIN / EAN → ASIN resolution

```
POST /catalog/2022-04-01/items?marketplaceIds=ATVPDKIKX0DER&identifiersType=EAN
{
  "identifiers": ["EAN-13-номер"],
  "includedData": ["summaries", "attributes", "images", "relationships"]
}
```

Ответ: `items[].asin` — искомый ASIN (+ атрибуты, вариации, изображения).

- `identifiersType`: `ASIN` | `EAN` | `GTIN` | `UPC` | `ISBN` | `SKU`.
- `includedData`: `attributes`, `identifiers`, `images`, `productTypes`, `salesRanks`, `summaries`, `relationships`, `dimensions`, `vendorDetails`.

---

## 3. Brand → ASIN (несколько ASIN) / Brand → ASIN

- `searchCatalogItems` с `keywords=<brand>` + фильтры → несколько ASIN.
- ⚠️ Не выбирать первый результат вслепую: сверять `brand`, `itemName`, атрибуты. Неоднозначности — помечать, не подставлять автоматически (правило из `Parser-AMZ-Company`).

---

## 4. Вариации из каталога / Variations from catalog

- `includedData=relationships` → `relationships` с `type=VARIATION` и `childAsins` / `parentAsins`.
- Полезно для сверки parent/child (см. `08-variations`).

---

## 5. Использование в твоём стеке / Use in your stack

- `Parser-AMZ-Company` помечает EAN→ASIN как **не реализовано** — этот API закрывает пробел.
- Для надёжности: `EAN → searchCatalogItems` → сверить `brand`/`itemName` → только потом связывать.
- Пример намерения: в `config.json` парсера или новом скрипте на базе `spapi_client.py`.
