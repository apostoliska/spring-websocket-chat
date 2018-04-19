spring-websocket-chat
=====================

[![Join the chat at https://gitter.im/salmar/spring-websocket-chat](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/salmar/spring-websocket-chat?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/salmar/spring-websocket-chat.svg?branch=master)](https://travis-ci.org/salmar/spring-websocket-chat)

Chat application using AngularJS and Spring WebSockets (STOMP over WebSockets)


![Spring WebSocket Chat](http://www.sergialmar.com/wp-content/uploads/2014/09/spring-websocket-chat-room.png "Spring WebSocket Chat")
## Features
- Built with Spring Boot
- User login via Keycloak
- Chat message broadcasting and private messages (filtering profanities)
- Presence tracking sending notifications when users join / leave
- Broadcast notifications when users are typing
- WebSockets stats exposed at /stats
- WebSocket security with Spring Security
- Spring Session integration

## Running the app
gradle bootRun

## Keycloak Setup
 0. Download and Install Keycloak 3.4.3.Final from the [Keycloak Website](https://www.keycloak.org/archive/downloads-3.4.3.html) 
 1. Import chatcity realm from `chatcity-realm.json` into Keycloak via
 ```
  bin/standalone.sh -Dkeycloak.migration.action=import
     -Dkeycloak.migration.provider=singleFile -Dkeycloak.migration.file=/path/to/chatcity-realm.json
     -Dkeycloak.migration.strategy=OVERWRITE_EXISTING
 ```
 2. Start Keycloak via `bin/standalone.sh`
 3. Start the Spring WebSocket Chat on Port 20000 on localhost.
 4. Browse to `http://localhost:20000/chat` and login with either `tester`, `petra`, `admin` with password `test`.
 