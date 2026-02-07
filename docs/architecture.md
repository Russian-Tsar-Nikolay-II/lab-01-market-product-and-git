## Product Choice
**Product name:** Telegram  
**Website:** [https://telegram.org](https://telegram.org)  
**Short description:** Telegram is a cloud-based messaging app that allows users to send messages, media, and make voice/video calls securely.

## Main components
![Telegram Component Diagram](./docs/diagrams/out/telegram/component-diagram/Component%20Diagram.svg)
- **Messaging Service (Сервис сообщений)** — отвечает за отправку и получение сообщений между пользователями.  
- **Media Storage (Хранилище медиа)** — хранит изображения, видео и другие файлы в облаке.  
- **User Authentication (Аутентификация пользователей)** — управляет логином, регистрацией и сессиями.  
- **Notification Service (Сервис уведомлений)** — отправляет push-уведомления о новых сообщениях.  
- **Search Service (Сервис поиска)** — обеспечивает поиск по чатам и сообщениям.

## Data flow
![Диаграмма последовательности Telegram](./docs/diagrams/out/telegram/sequence-diagram/Sequence%20Diagram.svg)

Пользователь отправляет сообщение:
- **Messaging Service** получает сообщение и сохраняет его в **Media Storage**.  
- Затем **Messaging Service** уведомляет **Notification Service**, который шлёт push-уведомление получателю.

## Deployment

![Диаграмма развёртывания Telegram](./docs/diagrams/out/telegram/deployment-diagram/Deployment%20Diagram.svg)

- **Messaging Service** и **Media Storage** развёрнуты в облаке.  
- **Notification Service** подключён к push-сервисам Android/iOS.  
- **User Authentication** работает на отдельных серверах для безопасности.

## Assumptions
- Предполагаю, что Media Storage использует дедупликацию для оптимизации места.  
- Предполагаю, что Notification Service обрабатывает миллионы уведомлений в реальном времени.

## Open questions

- Как именно работает шифрование сообщений на сервере?  
- Как распределяется нагрузка между серверами Messaging Service?
