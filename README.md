# ai-init

Переносимые инструкции для AI-агентов: скиллы, правила и рекомендации без
зависимости от конкретного приложения. Текущий набор ориентирован на PHP/Laravel;
проектная независимость не означает независимость от языка или фреймворка.

## Скиллы

Каждый каталог в `skills/` — самостоятельный скилл с `SKILL.md`, UI-метаданными
и дополнительными материалами по необходимости. Префикс `et-` сохранён для
совместимости имён и ссылок между скиллами.

| Скилл | Назначение |
|---|---|
| [et-activity-log](skills/et-activity-log/SKILL.md) | Журнал изменений, атрибуция, bulk/no-op и транзакции |
| [et-apidoc-documentation](skills/et-apidoc-documentation/SKILL.md) | Контракты API и документация Scribe |
| [et-github-pr-review](skills/et-github-pr-review/SKILL.md) | Ревью PR и локальных diff |
| [et-module-architecture](skills/et-module-architecture/SKILL.md) | Границы модулей и ответственность слоёв |
| [et-pest-testing](skills/et-pest-testing/SKILL.md) | Содержательные тесты Pest |
| [et-php-style-quality](skills/et-php-style-quality/SKILL.md) | Типизация, PHPDoc и проверки качества |
| [et-rest-naming-conventions](skills/et-rest-naming-conventions/SKILL.md) | Именование HTTP, кода и данных |
| [et-security-audit](skills/et-security-audit/SKILL.md) | Аудит безопасности с доказательствами |
| [et-spatie-package-conventions](skills/et-spatie-package-conventions/SKILL.md) | Интеграция пакетов Spatie |
| [et-validation-localization](skills/et-validation-localization/SKILL.md) | Валидация и локализованные ошибки |

Для использования поместите выбранные каталоги скиллов в каталог, который
поддерживает ваш AI-клиент. Пути обнаружения и необходимость перезапуска зависят
от клиента. Не перезаписывайте существующую установку без сравнения изменений.
Исходные проектные версии не обновляются автоматически.

## Принципы переносимости

- Сначала определить правила, версии зависимостей и возможности целевого проекта
- Не требовать конкретных каталогов, классов приложения, middleware, helpers или команд
- Не выдавать собственные расширения приложения за API Laravel или пакетов
- Применять архитектурные варианты и соглашения только там, где они выбраны
- Сохранять проверки поведения, безопасности, совместимости и побочных эффектов
- Не включать данные продукта, инфраструктурные адреса, секреты и личные пути

## Документация

Документы в `docs/` содержат общие правила. Они поддерживают стандартную
структуру Laravel с общими каталогами и модульную структуру с каталогами внутри
каждого доменного модуля. Два профиля размещения не требуют одинакового числа
слоёв; дополнительные Actions, Tasks и Repositories применяются по выбранному
архитектурному соглашению.

| Документ | Содержание |
|---|---|
| [architecture.md](docs/architecture.md) | Два профиля, таблица путей, слои, admin и регистрация |
| [testing.md](docs/testing.md) | Тестовые пути обоих профилей, изоляция, сценарии и assertions |
| [apidoc.md](docs/apidoc.md) | Вход, доступ, реальные ответы, Scribe и проверка OpenAPI |
| [general.md](docs/general.md) | Scope, совместимость, Git, проверки и доставка |
| [validation.md](docs/validation.md) | Правила входа, локализация и ошибки |
| [code-style.md](docs/code-style.md) | PHP types, PHPDoc, читаемость и quality tools |
| [naming.md](docs/naming.md) | HTTP, классы, данные и безопасное переименование |
| [ai-workflow.md](docs/ai-workflow.md) | Задачи агентам, контекст, инструменты и проверка результата |
| [authorization.md](docs/authorization.md) | Authentication, права, actor/tenant scope и jobs |
| [package-integration.md](docs/package-integration.md) | Версии, discovery, адаптеры и обновления пакетов |
| [activity-log.md](docs/activity-log.md) | Атрибуция, diff, bulk/no-op, транзакции и чувствительные данные |
| [concurrency-and-delivery.md](docs/concurrency-and-delivery.md) | Независимость, retries, after-commit и восстановление доставки |

Пути в архитектурных таблицах — примеры выбранного профиля, а не ссылки на
существующее приложение. Для адаптации сначала определите реальные пути,
namespace, bootstrap, версии и конфигурацию целевого проекта. Не переносите
конкретные guards, helpers, собственные APIs или команды из другого приложения.

Если нужны companion guides вместе со скиллами, используйте checkout целиком
или адаптируйте ссылки при установке. Скиллы остаются применимы отдельно: отсутствие
`docs/` не должно блокировать работу и не требует придумывать недоступные правила.
