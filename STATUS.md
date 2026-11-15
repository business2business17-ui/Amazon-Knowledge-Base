# РЎС‚Р°С‚СѓСЃ РїСЂРѕРµРєС‚Р° Amazon (Р±Р°Р·Р° Р·РЅР°РЅРёР№ + Р°РіРµРЅС‚С‹)

Р”Р°С‚Р° СЃРЅРёРјРєР°: 2026-11-14. РљР°Рє РІРѕР·РѕР±РЅРѕРІРёС‚СЊ: СЃРєР°Р¶Рё В«РїСЂРѕРґРѕР»Р¶Р°РµРј AmazonВ» вЂ” С‡РёС‚Р°Р№ СЌС‚РѕС‚ С„Р°Р№Р».

---

## Р“РґРµ С‡С‚Рѕ Р»РµР¶РёС‚

| РџСѓС‚СЊ | Р§С‚Рѕ СЌС‚Рѕ | Git |
|---|---|---|
| `C:\Users\adria\AMAZON\Amazon-Knowledge-Base` | **Р‘Р°Р·Р° Р·РЅР°РЅРёР№** (14 Р±Р»РѕРєРѕРІ, 25 MD + index.json) | вњ… init, 10 РєРѕРјРјРёС‚РѕРІ, РіРѕС‚РѕРІ Рє push |
| `C:\Users\adria\AMAZON\Amazon-Agents` | **РђРіРµРЅС‚С‹** (128 СЃРєРёР»Р»РѕРІ + 22 Р±Р»РѕРєР° Р±Р°Р·С‹) | вњ… init, 3 РєРѕРјРјРёС‚Р°, РіРѕС‚РѕРІ Рє push |
| `C:\Users\adria\AMAZON\Marketplace-Agents` | **РњСѓР»СЊС‚РёРјР°СЂРєРµС‚РїР»РµР№СЃ-Р°РіРµРЅС‚** (274 СЃРєРёР»Р»Р°: sealeap + РІРµР±-SEO) | вњ… init, 1 РєРѕРјРјРёС‚, РіРѕС‚РѕРІ Рє push |
| `C:\Users\adria\AMAZON\txt-repos` | **РСЃС…РѕРґРЅРёРєРё РёР· `Amazon skills.txt`** (36 РєР»РѕРЅРѕРІ) | вЂ” (РїСЂРѕСЃС‚Рѕ РєР»РѕРЅС‹) |
| `C:\Users\adria\agents-embed` | РІСЂРµРјРµРЅРЅС‹Р№ РєР»РѕРЅ С‚РІРѕРµРіРѕ `Agents` | РјРѕР¶РЅРѕ СѓРґР°Р»РёС‚СЊ |
| `S:\US AMAZON API` | С‚РІРѕР№ SP-API РїСЂРѕРµРєС‚ (MOBILIUS) | С‚РѕР»СЊРєРѕ С‡С‚РµРЅРёРµ, РЅРµ РјРµРЅСЏС‚СЊ |

---

## РЎРґРµР»Р°РЅРѕ

### 1. Р‘Р°Р·Р° Р·РЅР°РЅРёР№ (Amazon-Knowledge-Base)
- **14 Р±Р»РѕРєРѕРІ**: `00-global` (13 СЂС‹РЅРєРѕРІ + РіР»РѕСЃСЃР°СЂРёР№), `01-listings`, `02-pricing` (+Pricing Health), `03-seo`, `04-ppc`, `05-feeds` (РѕР±Р·РѕСЂ + **РїРѕР»РЅС‹Р№ РєР°С‚Р°Р»РѕРі РѕС€РёР±РѕРє ~38 РєРѕРґРѕРІ** + **JSON-СЃС…РµРјР° JSON_LISTINGS_FEED**), `06-promotions`, `07-advertising`, `08-variations`, `09-design`, `10-logistics` (+FBA fees), `11-account` (+compliance/B2B/Global Selling), `12-lifehacks` (Р»Р°Р№С„С…Р°РєРё + **forum-2026**), `13-sp-api` (auth/domains/reports/catalog-items).
- Р¤РѕСЂРјР°С‚: MD РґРІСѓСЏР·С‹С‡РЅС‹Р№ (RU+EN) + `index.json` РјР°РЅРёС„РµСЃС‚. US вЂ” СЌС‚Р°Р»РѕРЅ, 12 СЂС‹РЅРєРѕРІ вЂ” РґРµР»СЊС‚С‹.
- РСЃС‚РѕС‡РЅРёРєРё: РѕС„РёС†. РґРѕРєРё (developer-docs.amazon.com + JSON-СЃС…РµРјС‹ amzn/selling-partner-api-models) + Seller Forums (obscura).

### 2. Seller Forums С‡РµСЂРµР· obscura
- Р¤РѕСЂСѓРј **РіР»РѕР±Р°Р»СЊРЅС‹Р№** (СЃС‚СЂР°РЅРѕРІС‹Рµ РїРѕРґРґРѕРјРµРЅС‹ СЂРµРґРёСЂРµРєС‚СЏС‚). РЎРєСЂРµР№Рї 4 РєР°С‚РµРіРѕСЂРёР№ в†’ `12-lifehacks/02-forum-2026.md`.
- РЎС‹СЂС‹Рµ РґР°РјРїС‹ + РєР°СЂС‚Р° РєР°С‚РµРіРѕСЂРёР№/СЃС‚СЂР°РЅ вЂ” `scraped/`.

### 3. РђРіРµРЅС‚С‹ (Amazon-Agents)
- РўРІРѕРё 4 Р°РіРµРЅС‚Р° (`amazon-seo-listings`, `amazon-ppc`, `amazon-feeds`, `amazon-creative-studio`) + **22 Р±Р»РѕРєР° Р±Р°Р·С‹** РІ `references/kb/`.
- **+33 РёРјРїРѕСЂС‚РёСЂРѕРІР°РЅРЅС‹С… Amazon-СЃРєРёР»Р»Р°** (СЃРј. `IMPORTED_SKILLS.md`): amzn/selling-partner-agentic-toolkit (12), sellerstack (12), zach22 (7), Rufus/Cosmo (1), AI-shopping-CN (1).
- РС‚РѕРіРѕ 128 СЃРєРёР»Р»РѕРІ.

---

## РћСЃС‚Р°Р»РѕСЃСЊ (РїР»Р°РЅ)

### A. Push РІ GitHub вЂ” вњ… РЎР”Р•Р›РђРќРћ (2026-11-15)
Р—Р°РїСѓС€РµРЅС‹ 3 СЂРµРїРѕ РІ `business2business17-ui`:
- `Amazon-Knowledge-Base`, `Amazon-Agents`, `Marketplace-Agents` (РІСЃРµ вЂ” РІРµС‚РєР° `main`).

### B. РћС‚РґРµР»СЊРЅС‹Р№ РјСѓР»СЊС‚РёРјР°СЂРєРµС‚РїР»РµР№СЃ-Р°РіРµРЅС‚ вЂ” вњ… РЎР”Р•Р›РђРќРћ (2026-11-15)
РЎРѕР±СЂР°РЅ РІ `C:\Users\adria\AMAZON\Marketplace-Agents` (274 СЃРєРёР»Р»Р°, 1 РєРѕРјРјРёС‚):
- `marketplaces/` вЂ” sealeap (eBay/Etsy/MercadoLibre/Ozon/Shopify/TikTokShop/Walmart/Wayfair, 195 СЃРєРёР»Р»РѕРІ).
- `web-seo/` вЂ” chatgpt-seo (27), claude-seo (26+extensions), seo-skills (3), ecommerce-seo-geo (12), ai-seo-skill, ecommerce-seo-audit-skill.
- Р“РѕС‚РѕРІ Рє push (РЅСѓР¶РµРЅ РїСѓСЃС‚РѕР№ СЂРµРїРѕ `Marketplace-Agents`).

### C. РљРѕРґ/РґР°С€Р±РѕСЂРґС‹/MCP вЂ” вњ… РёРЅРІРµРЅС‚Р°СЂСЊ РіРѕС‚РѕРІ (2026-11-15)
РРЅРІРµРЅС‚Р°СЂСЊ РІ `14-tools/README.md` (РІ Р±Р°Р·Рµ Р·РЅР°РЅРёР№): 2 MCP-СЃРµСЂРІРµСЂР° (amazon-ads-mcp, amazon-omniscient), 8 С‚СѓР»Р·РѕРІ/РєР°Р»СЊРєСѓР»СЏС‚РѕСЂРѕРІ, 2 СЃРїСЂР°РІРѕС‡РЅС‹С…, 11 РґР°С€Р±РѕСЂРґРѕРІ, 1 РјС‘СЂС‚РІС‹Р№ (ecommerce-reviews-RAG вЂ” РїСѓСЃС‚РѕР№).
Р”Р°Р»СЊС€Рµ РїРѕ Р¶РµР»Р°РЅРёСЋ: СЂР°Р·РІРµСЂРЅСѓС‚СЊ `amazon-omniscient` (self-hosted) Рё РїРѕРґРєР»СЋС‡РёС‚СЊ `amazon-ads-mcp` (РЅСѓР¶РµРЅ Ads-РґРѕСЃС‚СѓРї).

---

## РљР°Рє РІРѕР·РѕР±РЅРѕРІРёС‚СЊ

1. В«РїСЂРѕРґРѕР»Р¶Р°РµРј AmazonВ» в†’ РїСЂРѕС‡РёС‚Р°С‚СЊ СЌС‚РѕС‚ С„Р°Р№Р».
2. РЎРІРµСЂРёС‚СЊ, РєР°РєРёРµ СЂРµРїРѕ СѓР¶Рµ СЃРѕР·РґР°РЅС‹ РЅР° GitHub (РµСЃР»Рё СЃРѕР·РґР°Р» вЂ” СЃСЂР°Р·Сѓ push).
3. Р•СЃР»Рё СЃРѕР·РґР°РЅС‹ вЂ” push A; Р·Р°С‚РµРј B (РјСѓР»СЊС‚РёРјР°СЂРєРµС‚РїР»РµР№СЃ-Р°РіРµРЅС‚) РёР»Рё C (РєРѕРґ/MCP).

## РРЅСЃС‚СЂСѓРјРµРЅС‚С‹ РѕРєСЂСѓР¶РµРЅРёСЏ
- `obscura` (`C:\Users\adria\tools\obscura-bin\obscura.exe`) вЂ” headless-Р±СЂР°СѓР·РµСЂ РґР»СЏ СЃРєСЂРµР№РїР°.
- `websearch` РІ СЌС‚РѕР№ СЃРµСЃСЃРёРё Р±С‹Р» РЅРµРґРѕСЃС‚СѓРїРµРЅ в†’ РёСЃС‚РѕС‡РЅРёРєРё С‚СЏРЅСѓР» С‡РµСЂРµР· `webfetch` РѕС„РёС†РёР°Р»СЊРЅС‹С… РґРѕРєРѕРІ + JSON-СЃС…РµРј.
- Git identity: `Keos` <business2business17@gmail.com>; `gh` CLI **РЅРµ СѓСЃС‚Р°РЅРѕРІР»РµРЅ**.
