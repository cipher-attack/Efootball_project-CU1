# eFootball Responder Bot - System Overview

The **eFootball Responder Bot** is a high-performance, custom-built Telegram application. It is engineered with modern backend technologies to automate channel workflows, manage user requests, and facilitate structured interactions.

## Core System Features

### 1. Mandatory Channel Integration (Force Join)
The system utilizes a custom middleware that requires users to join a specified Telegram channel before accessing the bot's functionalities. This protocol ensures consistent channel growth through automated user redirection.

### 2. Persistent Database Architecture
User data and system interactions are securely logged in a relational database powered by PostgreSQL and Prisma ORM. This infrastructure allows for comprehensive data retention and scalable broadcast messaging to the registered user base.

### 3. Integrated Ticketing System
User requests, such as "Team Build" or "Player Progression" inquiries, are routed through a structured support ticketing system. Administrators can review, reply to, and close tickets directly via the admin interface, isolating operational data from personal messages.

### 4. Service & Transaction Routing
The bot utilizes an interactive, menu-driven interface to collect structured data for services including Account Selling and Coin Purchasing. Processed data is systematically formatted and forwarded to the administrator for fulfillment.

### 5. Inline Global Search
Equipped with Telegram's inline query engine, the system allows users to search the database from any external chat (e.g., `@yourbotname Messi`). It instantly returns formatted player statistics and media, embedding automated redirection links back to the primary bot.

### 6. Security & Traffic Management
To maintain optimal availability, the application is secured with custom rate-limiting and anti-spam middlewares. These protocols automatically detect, restrict, and block malicious traffic or excessive automated requests.

---

## Technical Specifications

*   **Runtime Environment:** Node.js
*   **Language:** TypeScript
*   **Framework:** Telegraf
*   **Database:** PostgreSQL (via Prisma ORM)
*   **Architecture:** Modular routing (Isolated User, Admin, and Owner logic)

## Administrative Controls

The system provides a strictly authorized administrative interface accessible directly via Telegram. Permissions include:
*   Updating system prompts and promotional content dynamically.
*   Modifying operational configurations (e.g., billing details).
*   Managing user access (Ban/Unban protocols).
*   Executing global broadcast messages to all registered users.

---

## Repository Structure

```
├── README.md
├── api
│   ├── set-webhook.ts
│   └── webhook.ts
├── package.json
├── prisma
│   └── schema.prisma
├── public
│   └── index.html
├── src
│   ├── core
│   │   ├── admin.handler.ts
│   │   ├── bot.ts
│   │   ├── faq.handler.ts
│   │   ├── meta.handler.ts
│   │   ├── order.handler.ts
│   │   ├── prisma.ts
│   │   ├── system.service.ts
│   │   └── utils.ts
│   ├── middlewares                                                           │   │   ├── auth.middleware.ts
│   │   ├── core.middleware.ts
│   │   ├── forceJoin.middleware.ts
│   │   ├── rateLimiter.middleware.ts
│   │   └── security.middleware.ts
│   ├── modules
│   │   ├── admin
│   │   │   ├── admin.handler.ts
│   │   │   ├── admin.service.ts
│   │   │   ├── owner.service.ts
│   │   │   └── player-builder.service.ts
│   │   ├── automation
│   │   │   ├── automation.handler.ts
│   │   │   └── menu.config.ts
│   │   ├── chat
│   │   │   └── chat.service.ts
│   │   ├── commerce
│   │   │   └── commerce.service.ts
│   │   ├── formation
│   │   │   ├── formation.engine.ts
│   │   │   └── meta.seeder.ts
│   │   └── player
│   │       └── player.service.ts
│   ├── routers
│   │   ├── admin.router.ts
│   │   ├── owner.router.ts
│   │   └── user.router.ts
│   └── utils
│       └── formatter.ts
└── tsconfig.ጅሶን
```