# ChatService — обзор

## Ответственность

- создать/найти direct-диалог между двумя пользователями;
- (позже) групповые диалоги: create, invite, leave, roles;
- принять сообщение как opaque blob + служебные поля;
- вернуть страницу истории;
- опубликовать событие «новое сообщение» для realtime-слоя.

## Доменная модель (черновик)

```
Conversation(id, type: Direct|Group, title?, createdAt)
Membership(conversationId, userId, role, joinedAt)
Message(
  id, conversationId, senderUserId, senderDeviceId,
  ciphertext, nonce, header,
  mediaRefs[],
  sentAt, clientMsgId
)
```

`type = Group` закладывается сразу, даже если MVP UI только 1:1.

## Что сервис НЕ делает

- не шифрует и не расшифровывает;
- не хранит бинарные файлы (только refs на MediaService);
- не держит WebSocket-соединения клиентов;
- не управляет заявками на доступ / JWT.

## Интеграции

- **Identity** — валидные userId/deviceId (через Gateway JWT claims).
- **Realtime** — fan-out ciphertext получателям.
- **Media (P1)** — проверка/резолв `mediaId` при необходимости.
