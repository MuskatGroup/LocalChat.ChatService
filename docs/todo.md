# ChatService — TODO

## P0 — MVP

- [ ] проект .NET 10 + EF Core + PostgreSQL
- [ ] Conversation / Membership / Message
- [ ] создать или получить Direct-диалог
- [ ] `POST` сообщение (ciphertext only) + идемпотентность по `clientMsgId`
- [ ] `GET` история с пагинацией
- [ ] проверка membership перед записью/чтением
- [ ] событие NewMessage → Realtime (HTTP/queue)
- [ ] Dockerfile + миграции
- [ ] health

## P1

- [ ] `mediaRefs[]` + контракт с MediaService
- [ ] replies / quote (метаданные, без plaintext)
- [ ] удаление/редактирование на уровне «tombstone» ciphertext

## P2

- [ ] Group: создание, приглашения, роли (Member/Admin)
- [ ] системные события (участник добавлен) как отдельные типы сообщений
- [ ] поиск по метаданным (не по тексту — текст недоступен)

## Вне скоупа

- E2EE crypto, WebRTC, хранение файлов, push.
