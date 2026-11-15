# Статус проекта Amazon (база знаний + агенты)

Дата снимка: 2026-11-14. Как возобновить: скажи «продолжаем Amazon» — читай этот файл.

---

## Где что лежит

| Путь | Что это | Git |
|---|---|---|
| `C:\Users\adria\Amazon-Knowledge-Base` | **База знаний** (14 блоков, 25 MD + index.json) | ✅ init, 10 коммитов, готов к push |
| `C:\Users\adria\Amazon-Agents` | **Агенты** (128 скиллов + 22 блока базы) | ✅ init, 3 коммита, готов к push |
| `C:\Users\adria\Marketplace-Agents` | **Мультимаркетплейс-агент** (274 скилла: sealeap + веб-SEO) | ✅ init, 1 коммит, готов к push |
| `C:\Users\adria\txt-repos` | **Исходники из `Amazon skills.txt`** (36 клонов) | — (просто клоны) |
| `C:\Users\adria\agents-embed` | временный клон твоего `Agents` | можно удалить |
| `S:\US AMAZON API` | твой SP-API проект (MOBILIUS) | только чтение, не менять |

---

## Сделано

### 1. База знаний (Amazon-Knowledge-Base)
- **14 блоков**: `00-global` (13 рынков + глоссарий), `01-listings`, `02-pricing` (+Pricing Health), `03-seo`, `04-ppc`, `05-feeds` (обзор + **полный каталог ошибок ~38 кодов** + **JSON-схема JSON_LISTINGS_FEED**), `06-promotions`, `07-advertising`, `08-variations`, `09-design`, `10-logistics` (+FBA fees), `11-account` (+compliance/B2B/Global Selling), `12-lifehacks` (лайфхаки + **forum-2026**), `13-sp-api` (auth/domains/reports/catalog-items).
- Формат: MD двуязычный (RU+EN) + `index.json` манифест. US — эталон, 12 рынков — дельты.
- Источники: офиц. доки (developer-docs.amazon.com + JSON-схемы amzn/selling-partner-api-models) + Seller Forums (obscura).

### 2. Seller Forums через obscura
- Форум **глобальный** (страновые поддомены редиректят). Скрейп 4 категорий → `12-lifehacks/02-forum-2026.md`.
- Сырые дампы + карта категорий/стран — `scraped/`.

### 3. Агенты (Amazon-Agents)
- Твои 4 агента (`amazon-seo-listings`, `amazon-ppc`, `amazon-feeds`, `amazon-creative-studio`) + **22 блока базы** в `references/kb/`.
- **+33 импортированных Amazon-скилла** (см. `IMPORTED_SKILLS.md`): amzn/selling-partner-agentic-toolkit (12), sellerstack (12), zach22 (7), Rufus/Cosmo (1), AI-shopping-CN (1).
- Итого 128 скиллов.

---

## Осталось (план)

### A. Push в GitHub — ✅ СДЕЛАНО (2026-11-15)
Запушены 3 репо в `business2business17-ui`:
- `Amazon-Knowledge-Base`, `Amazon-Agents`, `Marketplace-Agents` (все — ветка `main`).

### B. Отдельный мультимаркетплейс-агент — ✅ СДЕЛАНО (2026-11-15)
Собран в `C:\Users\adria\Marketplace-Agents` (274 скилла, 1 коммит):
- `marketplaces/` — sealeap (eBay/Etsy/MercadoLibre/Ozon/Shopify/TikTokShop/Walmart/Wayfair, 195 скиллов).
- `web-seo/` — chatgpt-seo (27), claude-seo (26+extensions), seo-skills (3), ecommerce-seo-geo (12), ai-seo-skill, ecommerce-seo-audit-skill.
- Готов к push (нужен пустой репо `Marketplace-Agents`).

### C. Код/дашборды/MCP — ✅ инвентарь готов (2026-11-15)
Инвентарь в `14-tools/README.md` (в базе знаний): 2 MCP-сервера (amazon-ads-mcp, amazon-omniscient), 8 тулзов/калькуляторов, 2 справочных, 11 дашбордов, 1 мёртвый (ecommerce-reviews-RAG — пустой).
Дальше по желанию: развернуть `amazon-omniscient` (self-hosted) и подключить `amazon-ads-mcp` (нужен Ads-доступ).

---

## Как возобновить

1. «продолжаем Amazon» → прочитать этот файл.
2. Сверить, какие репо уже созданы на GitHub (если создал — сразу push).
3. Если созданы — push A; затем B (мультимаркетплейс-агент) или C (код/MCP).

## Инструменты окружения
- `obscura` (`C:\Users\adria\tools\obscura-bin\obscura.exe`) — headless-браузер для скрейпа.
- `websearch` в этой сессии был недоступен → источники тянул через `webfetch` официальных доков + JSON-схем.
- Git identity: `Keos` <business2business17@gmail.com>; `gh` CLI **не установлен**.
