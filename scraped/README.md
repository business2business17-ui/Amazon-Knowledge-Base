# Raw Seller Forums dumps (obscura)

Сырые дампы публичного read-only Amazon Seller Forums, собраны obscura v0.2.6
(`C:\Users\adria\tools\obscura-bin\obscura.exe fetch --dump text`), 2026-11-14.

Кодировка: текст английский — чистый; emoji/спецсимволы — mojibake (PowerShell
конвейер). Для читаемого текста см. `../12-lifehacks/02-forum-2026.md`.

## Категории (en_US)

| Файл | Категория | URL |
|---|---|---|
| listings-pricing.txt | Create and Manage Listings | `?categories[]=amzn1.spce.category.8b1ad436` |
| account-health.txt | Account Health | `?categories[]=amzn1.spce.category.8b1ad9d6` |
| grow-business.txt | Grow Your Business | `?categories[]=amzn1.spce.category.8b1ad7ec` |
| fulfill-orders.txt | Fulfill Orders | `?categories[]=amzn1.spce.category.8b1ad526` |

## Все категории

| Категория | category id |
|---|---|
| Account Setup | `amzn1.spce.category.8b1ad26a` |
| Create and Manage Listings | `amzn1.spce.category.8b1ad436` |
| Fulfill Orders | `amzn1.spce.category.8b1ad526` |
| Manage Inventory | `amzn1.spce.category.8b1ad60c` |
| Product Safety and Compliance | `amzn1.spce.category.8b1ad9e4` |
| Manage Your Brand | `amzn1.spce.category.8b1ad6fc` |
| Grow Your Business | `amzn1.spce.category.8b1ad7ec` |
| Manage Buyer Experience | `amzn1.spce.category.8b1ad8dc` |
| Account Health | `amzn1.spce.category.8b1ad9d6` |
| News and Announcements | `amzn1.spce.category.8b1ad9d2` |
| Community Connections | `amzn1.spce.category.8b1ad9e8` |

## Страны (read-only переключатель)

`https://sellercentral.amazon.com/seller-forums?mons_sel_locale=<locale>`
например: `en_US`, `en_GB`, `de_DE`, `fr_FR`, `it_IT`, `es_ES`, `nl_NL`, `sv_SE`,
`pl_PL`, `nl_BE`, `tr_TR`, `en_AE`, `ar_SA`.

## Как перезапустить

```powershell
$O="C:\Users\adria\tools\obscura-bin\obscura.exe"
& $O fetch --dump text --timeout 45 "https://sellercentral.amazon.com/seller-forums/discussions?categories%5B%5D=<id>" 2>$null | Out-File -Encoding utf8 out.txt
```
