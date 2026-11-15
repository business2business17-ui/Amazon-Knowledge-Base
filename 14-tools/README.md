---
id: tools-code
title: { ru: "Код / MCP / дашборды (инвентарь из txt)", en: "Code / MCP / dashboards (inventory from txt)" }
block: 14-tools
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [tools, mcp, calculator, scraper, dashboard, seo-tool, inventory]
updated: 2026-11-15
---

# Код / MCP / дашборды — инвентарь / Code / MCP / dashboards inventory

Инвентарь репозиториев из `Amazon skills.txt` **без скиллов** (код/тулзы/MCP/дашборды). Исходники — `C:\Users\adria\txt-repos\`. Скиллы уже разнесены по агентам (`Amazon-Agents`, `Marketplace-Agents`).

Inventory of the non-skill repos from `Amazon skills.txt`. Sources in `C:\Users\adria\txt-repos\`.

---

## 1. MCP-серверы / MCP servers (высокая ценность)

| Репо | Что это | Как использовать |
|---|---|---|
| **amazon-ads-mcp** (ppcprophet) | MCP-сервер к Amazon Ads: кампании, wasted spend, метрики через естественный язык | **Hosted** (PPC Prophet): нужен аккаунт + API-ключ → прописать в MCP-конфиге агента (см. `07-advertising`) |
| **amazon-omniscient** (Umair706) | Self-hosted full-stack исследование товаров (аналог Helium 10/Jungle Scout): niche/конкуренты/поставщики/маржа/BSR/52-нед. прогноз | Есть `.mcp.json` + `docker-compose.yml`. Развернуть локально (нужны API-ключи Amazon/Keepa) |

## 2. Инструменты и калькуляторы / Tools & calculators

| Репо | Стек | Что делает |
|---|---|---|
| **amazon-fba-calculator** | Next.js 14 | FBA-калькулятор **2026 US**: referral + fulfillment + fuel surcharge + storage + PPC + возвраты → маржа/ROI/break-even |
| **Amazon-FBA-Profit-Calculator---Complete-Source-Code** | Next.js | FBA-рентабельность: fee-расчёт, batch-обработка, аналитика |
| **amazon-seo-tool** | Streamlit/Python | Глубокий SEO-аудит листинга (8 секций, Helium 10-style) |
| **ecommerce-seo-optimizer** | Streamlit/Pandas | Массовый аудит+оптимизация листингов (title/description/image/price) с экспортом |
| **aiamazonseo** | Python | Скрепер Amazon для SEO/маркет-исследования + починка ссылок |
| **amazon-searchterm-249-optimizer** | HTML | Оптимизатор backend search terms (249 байт), открыть в браузере |
| **RankGap** | промпты | Multi-agent AI: разрыв ранжирования, какие запросы упущены (промпты для Claude) |
| **kdp-scout** | Python | KDP (Kindle/книги): ключи + конкуренты + BSR/продажи + Amazon Ads (не FBA) |

## 3. Справочные / Reference

| Репо | Что это |
|---|---|
| **awesome-amazon-ec-skills** | Курируемый список AI-скиллов для Amazon (CN) — каталог ссылок |
| **seo-tool-claude-seo** | Указатель на плагин Claude SEO (сам плагин уже в `Marketplace-Agents/web-seo/claude-seo-skills`) |

## 4. Дашборды (Excel/PowerBI/EDA) / Dashboards

Образовательные/аналитические проекты (не тулзы для продажи) — использовать как референс методики/визуализации:

| Репо | Тип |
|---|---|
| Amazon-Sales-Analysis-Excel | Excel-дашборд |
| Amazon_Sales_Data_Analysis | Excel-дашборд |
| Amazon_Sales_Product_-_Revenue_Analysis_Excel | Excel (2 датасета 2025, STAR-резюме) |
| Amazon-Sales-Analysis-in-Excel | Excel-дашборд (xlsm) |
| Amazon-Global-Sales | Power BI |
| amazon-data-analysis | Power BI (2012–2015 global) |
| Amazon-Power-BI-Dashboard | Power BI |
| Amazon-Sales-Analysis-Dashboard-Power-BI | Power BI |
| PowerBi-Amazon-E-Commerce-Sales-Performance-Analysis | Power BI |
| Amazon-Sales-Data-Analytics | Python EDA (Jupyter) |
| data-analytics-excel-case-study | Excel кейс |

## 5. Мёртвые / Dead

- **ecommerce-reviews-RAG** — пустой репо (нет README и файлов).

---

## Рекомендации / Recommendations

1. **MCP**: подключить `amazon-ads-mcp` (когда будет Ads-доступ) и развернуть `amazon-omniscient` как self-hosted исследование.
2. **Калькуляторы**: `amazon-fba-calculator` — актуальная модель 2026 (с fuel surcharge), сверять с моим `10-logistics/02-fba-fees.md`.
3. **SEO-тулзы**: `amazon-seo-tool` и `ecommerce-seo-optimizer` — запускать локально (Streamlit), дополняют `03-seo`.
4. **Дашборды** — только как референс методологии (не для продакшена).

> Полный сырой дамп опроса — `txt-repos\CODE_INVENTORY.txt`.
