# Amazon Seller Knowledge Base
# База знаний селлера Amazon

**Единый источник правил, лимитов, API-контрактов и лайфхаков для продажи на Amazon** — US · UK · EU · MENA (13 маркетплейсов). Для человека и для AI-агентов (Claude, Codex, Cursor, Gemini, ChatGPT).

**A single source of truth for Amazon selling rules, limits, API contracts, and lifehacks** — US · UK · EU · MENA (13 marketplaces). For humans and AI agents.

---

## Что это / What this is

- Структурированная MD-база по доменам: листинги, цены, SEO, PPC, фиды, промо, реклама, вариации, дизайн, логистика, аккаунт, лайфхаки.
- `index.json` — машинный манифест: все блоки, рынки, теги, статусы, ссылки. Точка входа для любого агента.
- Контент двуязычный (RU + EN), термины и названия полей API — в оригинале (англ.).

---

## Структура / Structure

```
amazon-knowledge-base/
├─ index.json                 ← манифест (машиночитаемый). Читай первым.
├─ README.md                  ← этот файл
├─ 00-global/                 ← 13 рынков, глоссарий, сквозные правила
│   ├─ 00-markets.md
│   └─ 01-glossary.md
├─ 01-listings/               ← ЯДРО · структура листинга, атрибуты, правила
├─ 02-pricing/                ← ЯДРО · градации цен: Min/Max, Sale, UVP, List, MAP, Buy Box
├─ 03-seo/                    ← ЯДРО · title/bullets/backend, A9/COSMO/Rufus, индексация
├─ 04-ppc/                    ← ЯДРО · SP/SB/SD, биды, ставки, ACOS/TACOS/ROAS
├─ 05-feeds/                  ← ЯДРО · форматы, заполнение, ошибки и их решение
├─ 06-promotions/             ← coupons, deals, vouchers, vine, Subscribe & Save
├─ 07-advertising/            ← все типы рекламы + биды (углублённо)
├─ 08-variations/             ← parent/child, атрибуты, темы вариаций
├─ 09-design/                 ← карусель, видео, A+ (базовый/премиум), Brand Store, размеры
├─ 10-logistics/              ← FBA, FBM, LTL, SPD, AWD, SFP
├─ 11-account/                ← support, vendor, программы, account health
└─ 12-lifehacks/              ← лайфхаки 2026, форум-опыт (с пометками достоверности)
```

---

## Как пользоваться / How to use

**Человеку / Human:** README → `00-global/` → нужный блок по оглавлению.

**Агенту / Agent:**
1. Прочитай `index.json` — там блоки, теги, рынки, статусы.
2. Найди нужный блок по `id` или `tags`.
3. Открой MD-файлы блока. Каждый файл самодостаточен и содержит front-matter с метаданными.

---

## Соглашения / Conventions

### Front-matter (в каждом MD)

```yaml
---
id: 00-markets
title: { ru: "Рынки", en: "Marketplaces" }
block: 00-global
status: done            # done | draft | todo
markets: [US, UK, ...]  # к каким рынкам применимо
tags: [marketplace, ids, vat]
updated: 2026-11-14
sources:                # список ссылок на первоисточники
  - { url: "...", kind: official, note: "..." }
---
```

### Теги достоверности источников / Source reliability tags

| Тег | Значение |
|---|---|
| `official` | Официальная документация Amazon (SP-API / ADS API / Seller Central help) |
| `forum-lifehack` | Seller Forums, опыт селлеров — неофициально, проверять перед применением |
| `third-party` | Сторонние сервисы / блоги |
| `verified` | Проверено вживую (через SP-API / Seller Central / парсер) |
| `unverified` | Не проверено, требует сверки с актуальным источником |

### Язык / Language
- Термины, названия полей API, коды — всегда на английском (оригинал).
- Пояснения — на русском и английском.
- US — эталон (максимальная детализация); UK/EU/MENA — как дельты (отличия), без дублирования общего.

---

## Метод исследования / Research method

- База: официальная документация Amazon (SP-API, ADS API, Seller Central help).
- Дополнительно: Seller Forums, опыт селлеров, лайфхаки 2026 — с пометкой `forum-lifehack`.
- Каждый факт, критичный для продакшена, помечается `verified` / `unverified`.

---

## Дорожная карта / Roadmap

| Фаза | Блоки | Статус |
|---|---|---|
| **0. Фундамент** | `00-global` (рынки + глоссарий) | ✅ сейчас |
| **1. Ядро** | `01-listings` · `02-pricing` · `03-seo` · `04-ppc` · `05-feeds` | ⏭ следующая |
| **2. Рост** | `06-promotions` · `07-advertising` · `08-variations` | ⏳ |
| **3. Полный охват** | `09-design` · `10-logistics` · `11-account` · `12-lifehacks` | ⏳ |

---

## Как встроить в агентов / How to plug into your agents

Блоки спроектированы агент-независимыми и самодостаточными. Чтобы встроить в существующие агенты (`business2business17-ui/Agents`):

| Блок | Куда положить |
|---|---|
| `01-listings` + `02-pricing` | `amazon-seo-listings` → `knowledge/` |
| `03-seo` | `amazon-seo-listings` → `knowledge/` |
| `04-ppc` + `07-advertising` | `amazon-ppc` → `knowledge/` |
| `05-feeds` | `amazon-feeds` → `knowledge/` |
| `09-design` | `amazon-creative-studio` → `knowledge/` |

Каждый MD читается как есть (`system-prompt.md` в `dist/` агентов уже умеет брать `knowledge/`).

---

## Рынки / Marketplaces (сводка)

13 маркетплейсов. Полная таблица — `00-global/00-markets.md`.

| Код | Рынок | marketplaceId | Эндпоинт SP-API |
|---|---|---|---|
| US | США | `ATVPDKIKX0DER` | NA |
| UK | Великобритания | `A1F83G8C2ARO7P` | EU |
| DE / FR / IT / ES / NL / SE / PL / BE / TR | Европа | (см. таблицу) | EU |
| AE / SA | ОАЭ / Саудовская Аравия | `A2VIGQ35RCS4UG` / `A17E79C6D8DWNP` | EU |

---

## Лицензия / License

Создаётся как рабочий справочник. Источники данных принадлежат их владельцам; факты помечаются тегом достоверности.
