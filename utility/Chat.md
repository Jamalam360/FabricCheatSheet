[Back to contents](../README.md)

## Sending to the in-game chat

There are multiple ways to send messages to the in-game chat box

### Broadcasting from server side to all clients

```java
MinecraftClient.getInstance().getServer().getPlayerManager().broadcastChatMessage(new LiteralText("lttstore.com"), MessageType.CHAT/MessageType.SYSTEM/MessageType.GAME_INFO, uuidOfSender);
```

### Broadcasting from the server to a specific client

```java
ServerPlayerEntity#sendMessage(new LiteralText("lttstore.com"), false);
```

### Broadcasting from the client to the server

```java
MiencraftClient.getInstance.player.sendChatMessage("lttstore.com");
```

