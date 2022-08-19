# Notes

Website where users can take/organize notes in folders.

This project will utilize Django a Django Backend Api and React frontend

### MVP User Stories

- As an unregistered user, I would like to sign up with email and password.
- As a registered user, I would like to sign in with email and password.

- As a signed in user, I would like to change password.
- As a signed in user, I would like to sign out.
- As a signed in user, I would like to send a chat message (socket)

- As a signed in user I would like to create a folder with a name a description
  
- As a signed in user I would like to create a note with Title and content
  
- As a signed in user I would like to update my notes

- As a signed in user I would like to update my folders
  
### Goals

-  Use Redux or Context for state management
-  Use Django for API
- Nice UI using Chakra UI or other styling library

### Reach Goal(s)

- Have a real text editor with fonts and bulleted lists ect to make notes
- Incorperate file upload with notes
- Share notes with other users
- Collaborative notes
  

## Route Table

## Route Table
- ### User Authentication
   | Verb   | URI Pattern         | Controller#Action |
   | ------ | ------------------- | ----------------- |
   | POST   | `/sign-up`          | `users # signup`    |
   | POST   | `/sign-in`          | `users # signin`    |
   | PATCH  | `/change-password/` | `users # changepw`  |
   | DELETE | `/sign-out/`        | `users # signout `  |

 - ### Folders
   | Verb   | URI Pattern | Controller#Action    |
   | ------ | ----------- | -------------------- |
   | GET    | `/folders` | `folders # index` |
   | GET    | `/folders/:folderId` | `folders # show` |
   | GET    | `/myfolders`| `folders # personal show` |
   | POST   | `/folders` | `folder # add` |
   | PATCH  | `/folders/:folderId`  | `folders # update`|
   | DELETE | `/folders/:folderId`  | `folders # destroy`|

 - ### Notes
   | Verb   | URI Pattern | Controller#Action    |
   | ------ | ----------- | -------------------- |
   | GET    | `/foldes/:folderId/notes` | `notes # index` |
   | GET    | `/folders/:folderID/notes/:noteId` | `notes # show` |
   | POST   | `/folders/:folderID/notes` | `note # add` |
   | PATCH  | `/folders/:folderID/notes/:noteId`  | `fnote # update`|
   | DELETE | `/folders/:folderID/notes/:noteId`  | `fnote # destroy`|

## Schema

 - ### User
   - email: string
       - required
       - unique
   - hashedPassword: string
       - required
   - token: string
   - timestamps

 - ### folder
   - name: string
       - required
       - unique
   - description: string 
   - notes: {{ note Schema}}
   - token: string
   - timestamps

 - ### note
   - author: {User}
   - title: String
   - content: String
  