---
id: 09-design
title: { ru: "Дизайн: главное фото, карусель, видео, A+, Brand Story, Brand Store", en: "Design: main image, carousel, video, A+, Brand Story, Brand Store" }
block: 09-design
status: done
markets: [US, UK, DE, FR, IT, ES, NL, SE, PL, BE, TR, AE, SA]
tags: [design, images, carousel, main-image, video, a-plus, premium-a-plus, brand-story, brand-store, sizes, safe-zone, moderation]
updated: 2026-11-16
sources:
  - { url: "https://sellercentral.amazon.com/help/hub/reference/external/G200498950", kind: official, note: "Product image requirements" }
  - { url: "https://sellercentral.amazon.com/help/hub/reference/external/G202102930", kind: official, note: "A+ Content: Basic vs Premium" }
  - { url: "https://sellercentral.amazon.com/help/hub/reference/external/GLG4RQK2Y2RJADU4", kind: official, note: "A+ Content технические требования, Brand Story" }
  - { url: "https://advertising.amazon.com/resources/ad-specs/stores", kind: official, note: "Stores creative guidelines / ad specs" }
  - { url: "github:business2business17-ui/Agents", kind: own, note: "amazon-creative-studio → knowledge/references/amazon-specs.md, brand-store-playbook.md, carousel-strategy.md" }
  - { url: "file:///S:/Чехлы/Дизайн/ТЗ дизайнеру Brand Story, Brand Store, A+ Premium — MOBILIUS.pdf", kind: own, note: "рабочее ТЗ MOBILIUS, 26.10.2026" }
---

# Дизайн: главное фото, карусель, видео, A+, Brand Story, Brand Store / Design

Всё, что дизайнер отдаёт по визуалу листинга: главное фото, галерея (карусель), видео, A+ Content (Basic и Premium), Brand Story и Brand Store. Здесь — карта блока, сквозные правила и сводка размеров; детали — в трёх отдельных файлах.

Everything the designer delivers for listing visuals: main image, gallery (carousel), video, A+ Content (Basic and Premium), Brand Story, and Brand Store. This file is the map, the cross-cutting rules, and the size summary; details live in three companion files.

```text
09-design/
├─ 01-design.md          ← этот файл: MAIN, галерея, видео, сводка размеров, комплаенс, QA
├─ 02-carousel.md        ← карусель листинга: 7 кадров, раскадровка, инфографика, mobile, локализация
├─ 03-a-plus-premium.md  ← A+ Basic vs Premium, модули, Brand Story, сравнение, Q&A, hotspots
├─ 04-brand-store.md     ← Brand Store: страницы, баннеры, safe zones, видео, shoppable, мобильный
└─ 05-video-specs.md     ← видео: листинг, A+ Premium, Store, Sponsored Brands (лимиты по площадкам)
```

> **Статус источников.** Размеры ниже взяты из официальных страниц Amazon (Seller Central Help, Amazon Ads) и из проектного `amazon-specs.md`. Всё, что помечено `[verify]`, обязательно проверяется в живом Seller Central / Store Builder / Content Manager на день вёрстки: Amazon меняет лимиты, а часть модулей зависит от аккаунта и категории. `[forum-lifehack]` — практика, не правило Amazon.

---

## 1. Карта решений: что рисовать в каком слое / Which layer to design in

| Слой | Где виден | Кто собирает | Что делает дизайнер | Файл |
|---|---|---|---|---|
| MAIN + галерея | Карточка товара, верх | Продавец загружает файлы | 7 кадров карусели | `02-carousel.md` |
| Видео листинга | Слот в галерее | Продавец загружает MP4 | Ролик + обложка | §4 ниже `[verify]` |
| A+ Basic / Premium | Под bullets | Контент-менеджер собирает модули | Баннеры модулей | `03-a-plus-premium.md` |
| Brand Story | Блок «From the brand» | Отдельный тип A+ | Шапка + 4 карточки | `03-a-plus-premium.md` §7 |
| Brand Store | Отдельный магазин | Store Builder, страницы вручную | Баннеры, плитки, shoppable | `04-brand-store.md` |

Правило приоритета: **сначала товар, потом бренд**. Если бюджет ограничен — MAIN и карусель закрывают конверсию карточки, A+ даёт +, Brand Store работает на трафик с рекламы и соцсетей. Не начинать со Store, пока карточки слабые.

> Order of work: main image and carousel first (they convert), A+ second, Brand Store last (it monetises external traffic).

---

## 2. Главное фото (MAIN) / Main image

| Требование | Значение | Статус |
|---|---|---|
| Фон | чистый белый `#FFFFFF` / RGB 255,255,255 | REQUIRED |
| Заполнение кадра | товар ≥ **85%** площади | REQUIRED |
| Текст, лого, водяные знаки, рамки, реквизит | запрещены | REQUIRED |
| Минимальный размер | ≥ **1000 px** по стороне (включает zoom) | REQUIRED |
| Рекомендуемый размер | **2000×2000 px**, 1:1 | RECOMMENDED |
| Продакшн-пресет проекта | **4000×4000 px**, sRGB, JPG/PNG | PRESET |
| Вес файла | до **10 МБ** (проектный лимит; жать качеством, не пикселями) | PRESET |
| Цвет товара | совпадает с тем, что получает покупатель | REQUIRED |
| Обрезка товара краем кадра | недопустима | REQUIRED |

Нарушение MAIN → ошибка `18027` → `SEARCH_SUPPRESSED`. Проверять на белом фоне в самом Seller Central, а не только в Photoshop: полупрозрачные чехлы и стекло дают серый ореол и проваливают проверку фона.

`[forum-lifehack]` Полупрозрачный товар на белом: снимать на просвет и подкладывать белую подложку внутри силуэта, иначе MAIN выглядит грязно-серым на белом фоне карточки.

---

## 3. Галерея / карусель / Gallery (carousel)

- **MAIN + до 7 дополнительных**, итого до 8 кадров; сколько слотов реально доступно — зависит от категории и шаблона `[verify]`.
- Порядок и есть стратегия: кадр 2 продаёт выгоду, кадр 3 — сценарий, кадр 4 — размер, кадр 5 — материал, кадр 6 — комплект, кадр 7 — доверие/упаковка.
- Инфографика с текстом разрешена **только на вторичных** кадрах.
- Полная раскадровка, техспека и чек-лист — в `02-carousel.md`.

---

## 4. Видео в карточке / Listing video

Слот видео живёт **внутри галереи**; загрузка — Seller Central → Upload and manage your product videos. Полная матрица по всем четырём площадкам — `05-video-specs.md`.

| Параметр | Листинг (shoppable video) |
|---|---|
| Формат | MOV или MP4 |
| Максимальный вес | 5 ГБ |
| Разрешение | до 1080p |
| Пропорции | 16:9 или 9:16 |
| Длительность | **1–12 минут** |
| Обложка | JPEG/PNG/GIF/BMP, до 5 МБ |

- Условия: аккаунт активен >3 месяцев, ASIN создан, видео привязано минимум к одному ASIN.
- Фотореалистичные люди, сгенерированные ИИ, требуют метки `contains-synthetic-performer` в XMP `dc:subject`.
- Что снимать: товар в руке, работу механизма/крепления, материал в макро, упаковку и комплект. Первые 5 секунд решают, досмотрят ли; логотип — в конце, не в начале.
- Видео не заменяет кадры: покупатель без звука должен понять товар по первому кадру.
- Для A+ Premium и Store — **отдельные файлы**: другие контейнеры, длительность и пропорции. Один ролик между площадками не переставлять.

---

## 5. A+, Brand Story, Brand Store — в двух словах / In one line each

| Формат | Одна мысль | Файл |
|---|---|---|
| A+ Basic | 5 модулей, 970 px, до 14 шаблонов — закрывает «подходит ли мне и из чего сделано» | `03-a-plus-premium.md` §1–3 |
| A+ Premium | 7 модулей, 1464 px, до 19 шаблонов, видео, карусель, hotspots, Q&A | `03-a-plus-premium.md` §4–6 |
| Brand Story | одна на весь бренд, до 19 карточек в карусели, видна на всех ASIN | `03-a-plus-premium.md` §7 |
| Brand Store | многостраничная витрина: путь «тип → модель → принт → ASIN» | `04-brand-store.md` |

---

## 6. Сводка размеров / Size summary

### 6.1. Карточка товара / PDP

| Элемент | Требование |
|---|---|
| MAIN | ≥1000 px, реком. 2000×2000, белый фон, ≥85% |
| Вторичные кадры | ≥1000 px, реком. 2000×2000 (пресет 4000×4000) |
| Видео листинга | MOV/MP4, ≤5 ГБ, до 1080p, 1–12 мин, 16:9 или 9:16 |

### 6.2. A+ / Brand Story

| Элемент | Размер / лимит | Статус |
|---|---|---|
| Basic A+ — общий размер картинки в сравнении Amazon | 970×300 px | официальное сравнение |
| Premium A+ — общий размер картинки в сравнении Amazon | 1464×600 px | официальное сравнение |
| A+ изображение | до 2 МБ, JPG/PNG/BMP, RGB, ≥72 dpi | REQUIRED |
| Comparison chart — картинка товара в столбце | 150×300 px | PRESET |
| Brand Story — фон секции | 1464×625 px | `[verify]` |
| Brand Story — карточка/фокус | 362×453 px | `[verify]` |
| Safe margin текста в модуле | ≥80 px от края | PRESET |
| Минимальный кегль | ~28 px на ширине 1464 (~19 px на 970) | PRESET |

### 6.3. Brand Store

| Элемент | Минимум | Лимит файла |
|---|---|---|
| Header Hero | 3000×600 px | 5 МБ |
| Brand logo | 400×400 px | 5 МБ |
| Full-width tile | 1500×20 px (реком. ширина 3000) | 5 МБ |
| Large tile | 1500×1500 px | 5 МБ |
| Medium tile | 1500×750 px | 5 МБ |
| Small tile | 750×750 px | 5 МБ |
| Custom mobile tile | 1680×20 px (реком. 1680×H) | 5 МБ |
| Shoppable full | 1500×750 (реком. 3000×1500) | 5 МБ |
| Gallery | 1500×750 px, до 8 кадров | 5 МБ |
| Video tile, full | обложка 3000×1500, видео 1280×640, 6:4–8:3 | MP4/H.264 |
| Background video, full | 1280×640, 2–20 с, без звука | MP4/H.264 |

Полные таблицы по типам плиток, видео и safe zones — в `04-brand-store.md`.

---

## 7. Комплаенс: что отклоняют на модерации / Moderation red lines

Действует для карусели, A+, Brand Story и Store одинаково.

**Нельзя:**

1. Цены, скидки, «free shipping», гарантии, отзывы, рейтинги, цитаты покупателей.
2. Превосходные степени: «best», «#1», «top», «лучший» — и сравнение с чужими брендами.
3. Логотипы и визуалы Apple, чужие торговые знаки, лицензируемые персонажи.
4. Утверждения о прочности с цифрами (высота падения, MIL-STD) без протокола испытаний.
5. Временные фразы: «new», «2026», «holiday», «Black Friday» — A+ живёт годами.
6. Водяные знаки, QR-коды, внешние ссылки в графике A+.
7. Несуществующая функциональность: конструктор «загрузи своё фото», если его нет в карточке.

**Обязательно:**

- «MagSafe®» — только в форме «compatible with MagSafe», не «MagSafe case».
- Дисклеймер мелкой строкой: «Not affiliated with Apple Inc. iPhone, AirPods and MagSafe are trademarks of Apple Inc.» (формулировку согласовать с юристом).
- Рендеры и фото — реальный товар в реальном цвете; никаких «улучшенных» материалов.
- Язык графики = язык маркетплейса (DE/FR/IT/ES/NL/SE/PL/TR/AR — локализовать, не оставлять EN).

---

## 8. Чек-лист перед загрузкой / Pre-upload QA

- [ ] MAIN: белый фон, ≥85%, без текста, ≥1000 px, товар не обрезан.
- [ ] Все кадры: sRGB, без CMYK, вес в лимите, имя файла по схеме.
- [ ] Текст читается с телефона без зума; ничего важного в нижних 19% / 12% (Store).
- [ ] Ни одного запрета из §7.
- [ ] Товар на графике = товар в карточке (модель, цвет, комплект).
- [ ] A+: alt-текст на английском у каждой картинки, ASIN в сравнении Active.
- [ ] Store: desktop **и** mobile preview пройдены, обрезка Hero проверена.
- [ ] Локализация: язык графики совпадает с маркетплейсом.
- [ ] Файлы названы по схеме и сведены в таблицу «файл → модуль → серия → alt-текст».

---

## 9. Лайфхаки / Lifehacks

1. **Инфографика на кадрах 2–4** — главный драйвер CVR после MAIN `[forum-lifehack]`.
2. **Видео в первых слотах галереи** удерживает покупателя дольше, чем ещё одно фото `[forum-lifehack]`.
3. **Один смысл на кадр.** Кадр с тремя тезисами не читается ни на телефоне, ни в зуме.
4. **Товар — герой кадра**, а не модель и не реквизит: POD-принт продаёт рисунок, а не обстановка.
5. **Не перерисовывать реальный товар.** Расхождение фото и товара — главная причина возвратов.
6. **Переиспользовать компоненты.** Один Figma-набор бейджей, рамок и кнопок на все серии: правка заголовка проходит во все макеты.
7. **Сначала бурд, потом вёрстка.** Один ключевой экран каждого формата на утверждение — дешевле, чем переделывать 20 модулей.

> Пункты 1–2, 6 — практика (`[forum-lifehack]`); остальное — правило процесса.

---

## 10. Именование файлов и сдача / File naming and handoff

```text
{серия}_PDP_MAIN.jpg            ← главное фото
{серия}_PDP_PT01…PT07.jpg       ← карусель
{серия}_AP_M01…M07.jpg          ← A+ модули
BS_C01…C04.jpg                  ← Brand Story карточки
ST_home_H01.jpg, ST_matte_T01.jpg ← Brand Store
```

Пакет сдачи: исходники (Figma/PSD) + экспорт по модулям + таблица «файл → модуль → серия → alt-текст» + отметка, где проверялся мобильный preview. Два раунда правок.
