---
id: tools-code
title: { ru: "РљРѕРґ / MCP / РґР°С€Р±РѕСЂРґС‹ (РёРЅРІРµРЅС‚Р°СЂСЊ РёР· txt)", en: "Code / MCP / dashboards (inventory from txt)" }
block: 14-tools
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [tools, mcp, calculator, scraper, dashboard, seo-tool, inventory]
updated: 2026-11-15
---

# РљРѕРґ / MCP / РґР°С€Р±РѕСЂРґС‹ вЂ” РёРЅРІРµРЅС‚Р°СЂСЊ / Code / MCP / dashboards inventory

РРЅРІРµРЅС‚Р°СЂСЊ СЂРµРїРѕР·РёС‚РѕСЂРёРµРІ РёР· `Amazon skills.txt` **Р±РµР· СЃРєРёР»Р»РѕРІ** (РєРѕРґ/С‚СѓР»Р·С‹/MCP/РґР°С€Р±РѕСЂРґС‹). РСЃС…РѕРґРЅРёРєРё вЂ” `C:\Users\adria\AMAZON\txt-repos\`. РЎРєРёР»Р»С‹ СѓР¶Рµ СЂР°Р·РЅРµСЃРµРЅС‹ РїРѕ Р°РіРµРЅС‚Р°Рј (`DEEP-Amazon-Agents`, `DEEP-Marketplace-Agents`).

Inventory of the non-skill repos from `Amazon skills.txt`. Sources in `C:\Users\adria\AMAZON\txt-repos\`.

---

## 1. MCP-СЃРµСЂРІРµСЂС‹ / MCP servers (РІС‹СЃРѕРєР°СЏ С†РµРЅРЅРѕСЃС‚СЊ)

| Р РµРїРѕ | Р§С‚Рѕ СЌС‚Рѕ | РљР°Рє РёСЃРїРѕР»СЊР·РѕРІР°С‚СЊ |
|---|---|---|
| **amazon-ads-mcp** (ppcprophet) | MCP-СЃРµСЂРІРµСЂ Рє Amazon Ads: РєР°РјРїР°РЅРёРё, wasted spend, РјРµС‚СЂРёРєРё С‡РµСЂРµР· РµСЃС‚РµСЃС‚РІРµРЅРЅС‹Р№ СЏР·С‹Рє | **Hosted** (PPC Prophet): РЅСѓР¶РµРЅ Р°РєРєР°СѓРЅС‚ + API-РєР»СЋС‡ в†’ РїСЂРѕРїРёСЃР°С‚СЊ РІ MCP-РєРѕРЅС„РёРіРµ Р°РіРµРЅС‚Р° (СЃРј. `07-advertising`) |
| **amazon-omniscient** (Umair706) | Self-hosted full-stack РёСЃСЃР»РµРґРѕРІР°РЅРёРµ С‚РѕРІР°СЂРѕРІ (Р°РЅР°Р»РѕРі Helium 10/Jungle Scout): niche/РєРѕРЅРєСѓСЂРµРЅС‚С‹/РїРѕСЃС‚Р°РІС‰РёРєРё/РјР°СЂР¶Р°/BSR/52-РЅРµРґ. РїСЂРѕРіРЅРѕР· | Р•СЃС‚СЊ `.mcp.json` + `docker-compose.yml`. Р Р°Р·РІРµСЂРЅСѓС‚СЊ Р»РѕРєР°Р»СЊРЅРѕ (РЅСѓР¶РЅС‹ API-РєР»СЋС‡Рё Amazon/Keepa) |

## 2. РРЅСЃС‚СЂСѓРјРµРЅС‚С‹ Рё РєР°Р»СЊРєСѓР»СЏС‚РѕСЂС‹ / Tools & calculators

| Р РµРїРѕ | РЎС‚РµРє | Р§С‚Рѕ РґРµР»Р°РµС‚ |
|---|---|---|
| **amazon-fba-calculator** | Next.js 14 | FBA-РєР°Р»СЊРєСѓР»СЏС‚РѕСЂ **2026 US**: referral + fulfillment + fuel surcharge + storage + PPC + РІРѕР·РІСЂР°С‚С‹ в†’ РјР°СЂР¶Р°/ROI/break-even |
| **Amazon-FBA-Profit-Calculator---Complete-Source-Code** | Next.js | FBA-СЂРµРЅС‚Р°Р±РµР»СЊРЅРѕСЃС‚СЊ: fee-СЂР°СЃС‡С‘С‚, batch-РѕР±СЂР°Р±РѕС‚РєР°, Р°РЅР°Р»РёС‚РёРєР° |
| **amazon-seo-tool** | Streamlit/Python | Р“Р»СѓР±РѕРєРёР№ SEO-Р°СѓРґРёС‚ Р»РёСЃС‚РёРЅРіР° (8 СЃРµРєС†РёР№, Helium 10-style) |
| **ecommerce-seo-optimizer** | Streamlit/Pandas | РњР°СЃСЃРѕРІС‹Р№ Р°СѓРґРёС‚+РѕРїС‚РёРјРёР·Р°С†РёСЏ Р»РёСЃС‚РёРЅРіРѕРІ (title/description/image/price) СЃ СЌРєСЃРїРѕСЂС‚РѕРј |
| **aiamazonseo** | Python | РЎРєСЂРµРїРµСЂ Amazon РґР»СЏ SEO/РјР°СЂРєРµС‚-РёСЃСЃР»РµРґРѕРІР°РЅРёСЏ + РїРѕС‡РёРЅРєР° СЃСЃС‹Р»РѕРє |
| **amazon-searchterm-249-optimizer** | HTML | РћРїС‚РёРјРёР·Р°С‚РѕСЂ backend search terms (249 Р±Р°Р№С‚), РѕС‚РєСЂС‹С‚СЊ РІ Р±СЂР°СѓР·РµСЂРµ |
| **RankGap** | РїСЂРѕРјРїС‚С‹ | Multi-agent AI: СЂР°Р·СЂС‹РІ СЂР°РЅР¶РёСЂРѕРІР°РЅРёСЏ, РєР°РєРёРµ Р·Р°РїСЂРѕСЃС‹ СѓРїСѓС‰РµРЅС‹ (РїСЂРѕРјРїС‚С‹ РґР»СЏ Claude) |
| **kdp-scout** | Python | KDP (Kindle/РєРЅРёРіРё): РєР»СЋС‡Рё + РєРѕРЅРєСѓСЂРµРЅС‚С‹ + BSR/РїСЂРѕРґР°Р¶Рё + Amazon Ads (РЅРµ FBA) |

## 3. РЎРїСЂР°РІРѕС‡РЅС‹Рµ / Reference

| Р РµРїРѕ | Р§С‚Рѕ СЌС‚Рѕ |
|---|---|
| **awesome-amazon-ec-skills** | РљСѓСЂРёСЂСѓРµРјС‹Р№ СЃРїРёСЃРѕРє AI-СЃРєРёР»Р»РѕРІ РґР»СЏ Amazon (CN) вЂ” РєР°С‚Р°Р»РѕРі СЃСЃС‹Р»РѕРє |
| **seo-tool-claude-seo** | РЈРєР°Р·Р°С‚РµР»СЊ РЅР° РїР»Р°РіРёРЅ Claude SEO (СЃР°Рј РїР»Р°РіРёРЅ СѓР¶Рµ РІ `DEEP-Marketplace-Agents/web-seo/claude-seo-skills`) |

## 4. Р”Р°С€Р±РѕСЂРґС‹ (Excel/PowerBI/EDA) / Dashboards

РћР±СЂР°Р·РѕРІР°С‚РµР»СЊРЅС‹Рµ/Р°РЅР°Р»РёС‚РёС‡РµСЃРєРёРµ РїСЂРѕРµРєС‚С‹ (РЅРµ С‚СѓР»Р·С‹ РґР»СЏ РїСЂРѕРґР°Р¶Рё) вЂ” РёСЃРїРѕР»СЊР·РѕРІР°С‚СЊ РєР°Рє СЂРµС„РµСЂРµРЅСЃ РјРµС‚РѕРґРёРєРё/РІРёР·СѓР°Р»РёР·Р°С†РёРё:

| Р РµРїРѕ | РўРёРї |
|---|---|
| Amazon-Sales-Analysis-Excel | Excel-РґР°С€Р±РѕСЂРґ |
| Amazon_Sales_Data_Analysis | Excel-РґР°С€Р±РѕСЂРґ |
| Amazon_Sales_Product_-_Revenue_Analysis_Excel | Excel (2 РґР°С‚Р°СЃРµС‚Р° 2025, STAR-СЂРµР·СЋРјРµ) |
| Amazon-Sales-Analysis-in-Excel | Excel-РґР°С€Р±РѕСЂРґ (xlsm) |
| Amazon-Global-Sales | Power BI |
| amazon-data-analysis | Power BI (2012вЂ“2015 global) |
| Amazon-Power-BI-Dashboard | Power BI |
| Amazon-Sales-Analysis-Dashboard-Power-BI | Power BI |
| PowerBi-Amazon-E-Commerce-Sales-Performance-Analysis | Power BI |
| Amazon-Sales-Data-Analytics | Python EDA (Jupyter) |
| data-analytics-excel-case-study | Excel РєРµР№СЃ |

## 5. РњС‘СЂС‚РІС‹Рµ / Dead

- **ecommerce-reviews-RAG** вЂ” РїСѓСЃС‚РѕР№ СЂРµРїРѕ (РЅРµС‚ README Рё С„Р°Р№Р»РѕРІ).

---

## Р РµРєРѕРјРµРЅРґР°С†РёРё / Recommendations

1. **MCP**: РїРѕРґРєР»СЋС‡РёС‚СЊ `amazon-ads-mcp` (РєРѕРіРґР° Р±СѓРґРµС‚ Ads-РґРѕСЃС‚СѓРї) Рё СЂР°Р·РІРµСЂРЅСѓС‚СЊ `amazon-omniscient` РєР°Рє self-hosted РёСЃСЃР»РµРґРѕРІР°РЅРёРµ.
2. **РљР°Р»СЊРєСѓР»СЏС‚РѕСЂС‹**: `amazon-fba-calculator` вЂ” Р°РєС‚СѓР°Р»СЊРЅР°СЏ РјРѕРґРµР»СЊ 2026 (СЃ fuel surcharge), СЃРІРµСЂСЏС‚СЊ СЃ РјРѕРёРј `10-logistics/02-fba-fees.md`.
3. **SEO-С‚СѓР»Р·С‹**: `amazon-seo-tool` Рё `ecommerce-seo-optimizer` вЂ” Р·Р°РїСѓСЃРєР°С‚СЊ Р»РѕРєР°Р»СЊРЅРѕ (Streamlit), РґРѕРїРѕР»РЅСЏСЋС‚ `03-seo`.
4. **Р”Р°С€Р±РѕСЂРґС‹** вЂ” С‚РѕР»СЊРєРѕ РєР°Рє СЂРµС„РµСЂРµРЅСЃ РјРµС‚РѕРґРѕР»РѕРіРёРё (РЅРµ РґР»СЏ РїСЂРѕРґР°РєС€РµРЅР°).

> РџРѕР»РЅС‹Р№ СЃС‹СЂРѕР№ РґР°РјРї РѕРїСЂРѕСЃР° вЂ” `txt-repos\CODE_INVENTORY.txt`.
