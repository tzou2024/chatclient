# chatclient


## Chat Room

A website where users can sign in to different chat rooms and chat with
other users.

This project will require real time messaging with Socket.io
- General tutorial, not specific to using socket.io with React https://socket.io/get-started/chat/
- Tutorial for using socket.io with Express and React https://www.valentinog.com/blog/socket-react/
- Back end docs https://socket.io/docs/server-api/
- Front end docs https://socket.io/docs/client-api/

### MVP User Stories

- As an unregistered user, I would like to sign up with email and password.
- As a registered user, I would like to sign in with email and password.

- As a signed in user, I would like to change password.
- As a signed in user, I would like to sign out.
- As a signed in user, I would like to send a chat message (socket)

- As a signed in user in a room, I would like to see the messages in a chat (socket)
- As a signed in user in a room, I would like create my own profile
- As a signed in user in a room, I would like to update my own profile
- As a signed in user in a room, I would like to delete my profile

### Reach Goal(s)

- Allow for users to create and join different chat rooms
- Allow for realtime notifications on typing or unread messages
- Allow users to send private messages.

## Route Table

## Route Table
- ### User Authentication
   | Verb   | URI Pattern         | Controller#Action |
   | ------ | ------------------- | ----------------- |
   | POST   | `/sign-up`          | `users # signup`    |
   | POST   | `/sign-in`          | `users # signin`    |
   | PATCH  | `/change-password/` | `users # changepw`  |
   | DELETE | `/sign-out/`        | `users # signout `  |

   - ### Chat
   | Verb   | URI Pattern | Controller#Action    |
   | ------ | ----------- | -------------------- |
   | GET    | `/chatrooms` | `chatrooms # index` |
   | GET    | `/chatrooms/:chatroomId` | `chatrooms # show` |
   | GET    | `/mychatrooms`| `chatrooms # personal show` |
   | POST   | `/chatrooms` | `chatroom # add` |
   | PATCH  | `/chatrooms/:chatroomId`  | `chatrooms # update`|
   | DELETE | `/chatrooms/:chatroomId`  | `chatrooms # destroy`|

   ## Schema

 - ### User
   - email: string
       - required
       - unique
   - name: string
       - required
       - unique
   - hashedPassword: string
       - required
   - profile pick: string (url)
   - token: string
   - timestamps

 - ### Chatroom
   - name: string
       - required
       - unique
   - members: [{Users}]
   - messages: {{ message Schema}}
   - ChatOwner: {User}
   - token: string
   - timestamps

 - ### Message
   - author: {User}
   - content: {String}
  