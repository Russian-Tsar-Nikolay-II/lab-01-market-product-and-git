## Product Choice
**Product name:** Telegram  
**Website:** [https://telegram.org](https://telegram.org)  
**Short description:** Telegram is a cloud-based messaging app that allows users to send messages, media, and make voice/video calls securely.

## Main components
![Telegram Component Diagram](./docs/diagrams/out/telegram/component-diagram/Component%20Diagram.svg)
- **Messaging Service** — Responsible for sending and receiving messages between users.  
- **Media Storage** — Stores images, videos and other files in the cloud.  
- **User Authentication** — manages login, registration, and sessions.  
- **Notification Service** — Sends push notifications about new messages.  
- **Search Service** — Provides search by chats and messages.

## Data flow
![Diagram](./docs/diagrams/out/telegram/sequence-diagram/Sequence%20Diagram.svg)

The user sends a message:
- **Messaging Service** receives the message and stores it in **Media Storage**.  
- Then the **Messaging Service** notifies the **Notification Service**, which sends a push notification to the recipient.

## Deployment

![Diagram](./docs/diagrams/out/telegram/deployment-diagram/Deployment%20Diagram.svg)

- **Messaging Service** and **Media Storage** are deployed in the cloud.  
- **Notification Service** is connected to Android/iOS push services.  
- **User Authentication** runs on separate servers for security.

## Assumptions
- Media Storage uses deduplication to optimize space.  
- Notification Service processes millions of notifications in real time.

## Open questions

- How exactly does message encryption work on the server?  
- How is the load distributed between the Messaging Service servers?
 - What goverments threaten Durov
