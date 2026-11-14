---
id: 01-auth-lwa
title: { ru: "SP-API: авторизация (LWA) и RDT", en: "SP-API: auth (LWA) & RDT" }
block: 13-sp-api
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [sp-api, auth, lwa, refresh-token, access-token, rdt, restricted-data-token, endpoint, sigv4]
updated: 2026-11-14
sources:
  - { url: "https://developer-docs.amazon.com/sp-api/docs/authorization", kind: official, note: "авторизация SP-API" }
  - { url: "https://developer-docs.amazon.com/sp-api/docs/restricted-data-token", kind: official, note: "RDT" }
---

# SP-API: авторизация (LWA) и Restricted Data Token / Auth & RDT

Как устроен доступ к SP-API: LWA-токен, refresh-токен, эндпоинты регионов, Restricted Data Token для PII.

SP-API auth: LWA token, refresh token, regional endpoints, Restricted Data Token for PII.

---

## 1. Схема авторизации / Auth flow

```
Refresh token (долгоживущий, от продавца)
        │  POST /auth/o2/token  (grant_type=refresh_token)
        ▼
Access token (LWA, ~1 час)
        │  заголовок x-amz-access-token
        ▼
SP-API запросы (x-amz-date + SigV4)
```

- **Refresh token** — получает продавец при авторизации приложения (продавец вставляет вручную, напр. `.env`).
- **Access token** — короткоживущий (~1 ч), обновляется автоматически из refresh token.
- **Client credentials** (`grant_type=client_credentials`) — для **grantless** операций (без продавца, напр. определение marketplace по ASIN).

---

## 2. LWA token URL / LWA token endpoint

`POST https://api.amazon.com/auth/o2/token`

Поля (form-encoded):
- `grant_type=refresh_token` → `refresh_token` + `client_id` + `client_secret`
- `grant_type=client_credentials` → `client_id` + `client_secret` + `scope`

---

## 3. Эндпоинты регионов / Regional endpoints

| Регион | Базовый URL | Рынки |
|---|---|---|
| **NA** | `sellingpartnerapi-na.amazon.com` | US, CA, MX, BR |
| **EU** | `sellingpartnerapi-eu.amazon.com` | UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, **AE, SA**, IN, EG, IE, ZA |
| **FE** | `sellingpartnerapi-fe.amazon.com` | SG, AU, JP |

> ⚠️ UAE и Saudi — на **EU**-эндпоинте (не FE). FE = только SG/AU/JP.

---

## 4. Заголовки запроса / Request headers

- `x-amz-access-token` — LWA access token.
- `x-amz-date` — дата (ISO8601).
- AWS **SigV4** подпись (для части операций) — `Authorization` + `host`.
- `x-amzn-RateLimit-Limit` — в ответе: актуальный rate limit.

---

## 5. Restricted Data Token (RDT) — PII / Restricted data

- PII (имя/адрес покупателя) по умолчанию **недоступна**.
- Нужен **RDT**: `POST /tokens/2021-03-01/restrictedDataToken` с `targetApplication` и `restrictedResources` (путь+метод).
- Доп. роль: **Direct-to-Consumer Shipping (Restricted)** — после одобрения переавторизовать приложение и вставить новый refresh token.
- RDT живёт ~1 ч, обновляется при обращении.

---

## 6. Настройка `.env` (паттерн из `S:\US AMAZON API`) / `.env` pattern

```
LWA_APP_ID=...
LWA_CLIENT_SECRET=...
SP_API_REFRESH_TOKEN=...
SELLER_ID=...
MARKETPLACE_ID=ATVPDKIKX0DER
SP_API_REGION=NA
SP_API_ENDPOINT=https://sellingpartnerapi-na.amazon.com
LWA_TOKEN_URL=https://api.amazon.com/auth/o2/token
# Ads (отдельный доступ, когда будет):
ADS_CLIENT_ID=... ADS_CLIENT_SECRET=... ADS_REFRESH_TOKEN=... ADS_PROFILE_ID=...
```

> Никогда не выводить токены/ключи в логи; хранить в `.env` (в gitignore).

---

## 7. Роли приложения / App roles

Доступные разделы зависят от **ролей**, выбранных при регистрации приложения и подтверждённых продавцом: Orders, Listings, Feeds, Reports, Pricing, Inventory, FBA, Catalog, Notifications и т.д. Проверка: `GET /authorization/v1/authorizationCode` / список доступных — в `11-account` и `02-api-domains`.
