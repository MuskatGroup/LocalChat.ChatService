# LocalChat.ChatService

Домен чата: диалоги, участники, история сообщений. Хранит только **ciphertext** и метаданные доставки; plaintext на сервер не попадает.

## Назначение

- conversations (`Direct` | `Group`);
- membership и роли в диалоге;
- сохранение сообщений (ciphertext, nonce, ratchet/header, `mediaRefs[]`);
- выдача истории по диалогу;
- события для RealtimeService о новых сообщениях.

## Стек

- .NET 10
- EF Core + PostgreSQL

## Документация

- [Обзор](docs/overview.md)
- [TODO](docs/todo.md)

## Запуск

Через Orchestrator. Плановый порт: **5102**.

## Связанные репозитории

| Репозиторий | Роль |
|---|---|
| [LocalChat.RealtimeService](https://github.com/MuskatGroup/LocalChat.RealtimeService) | Доставка |
| [LocalChat.MediaService](https://github.com/MuskatGroup/LocalChat.MediaService) | `mediaRefs` (P1) |
| [LocalChat.IdentityService](https://github.com/MuskatGroup/LocalChat.IdentityService) | User/device ids |
| [LocalChat.Web](https://github.com/MuskatGroup/LocalChat.Web) | Клиент |

## Лицензия

Apache-2.0 — см. [LICENSE](LICENSE).
