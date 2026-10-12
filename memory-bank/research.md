# Джерела та перевірки
Оновлено 2026-10-12. Джерела досліджувалися в діалозі; реалізація ще не перевірена.
Повторна пряма перевірка API OpenRouter підтвердила H/M/S/G/B, їхні тарифи, контекст, JSON Schema/tools і reasoning; GitHub API без авторизації — public/main. Повний [звіт](validation-report.md). Це не inference-тести чи гарантія підтримки параметрів будь-яким endpoint.

| Джерело | Для чого | Статус |
|---|---|---|
| [Вихідний SVG](drafts/inputs/salon-agent.svg) | Початковий скоуп | Незмінена копія |
| [OpenRouter models](https://openrouter.ai/api/v1/models) | Назви, можливості й ціни | Перевірялися 12.10.2026, повторити до запуску |
| [Structured outputs](https://openrouter.ai/docs/guides/features/structured-outputs) | JSON Schema й endpoint | Досліджено |
| [Tool calling](https://openrouter.ai/docs/guides/features/tool-calling) | Межі виклику інструментів | Досліджено |
| [Reasoning](https://openrouter.ai/docs/guides/best-practices/reasoning-tokens) | Бюджет токенів | Досліджено |
| [Fallback](https://openrouter.ai/docs/guides/routing/model-fallbacks) | API-маршрутизація | Досліджено |
| [Telegram API](https://core.telegram.org/bots/api) | ID, polling/webhook | Досліджено; polling рекомендований |
| [Sheets limits](https://developers.google.com/workspace/sheets/api/limits) | Атомарність і квоти | Досліджено |
| [Calendar events](https://developers.google.com/workspace/calendar/api/guides/create-events) | Події Calendar | Досліджено |
| [n8n Docker](https://docs.n8n.io/hosting/installation/docker/) | Локальне розгортання | Docker у користувача є |
| [n8n encryption key](https://docs.n8n.io/hosting/configuration/configuration-examples/encryption-key/) | Відновлення credentials | Досліджено |
| [restic](https://restic.readthedocs.io/en/stable/040_backup.html) | Можливий backup-інструмент | Кандидат, не встановлено |

Матеріали салону на Google Drive заявлені користувачем; посилання й вміст не отримані. Якість моделей, токени й пошук українською не виміряні.
Розрахунок $6.795 умовний, за попередніми тарифами; актуальність перед запуском обов’язкова. Зовнішня навчальна Google Sheets-таблиця створена раніше з прикладом 100 користувачів; вона не є джерелом актуального плану 300 користувачів і в цій консолідації не змінюється.
