# 🤖 AI-Powered Inventory Management System

> Complete inventory management system through natural conversations in Telegram, powered by Artificial Intelligence.

[![en](https://img.shields.io/badge/lang-en-red.svg)](README.md)
[![es](https://img.shields.io/badge/lang-es-yellow.svg)](README.es.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![n8n](https://img.shields.io/badge/n8n-Workflow-orange)](https://n8n.io)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-green)](https://openai.com)
[![Baserow](https://img.shields.io/badge/Baserow-Database-blue)](https://baserow.io)

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [Demo](#-demo)
- [Technologies](#-technologies)
- [Installation](#-installation)
- [Usage](#-usage)
- [Documentation](#-documentation)
- [Costs](#-costs)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 About the Project

This project was born from the need to create a **simple, affordable, and effective** inventory system for small businesses and non-profit organizations that cannot afford traditional systems costing $50-200/month.

### The Problem

- ✘ Professional systems are expensive and complex
- ✘ Spreadsheets require discipline and nobody updates them
- ✘ Mobile apps require training and have a learning curve
- ✘ Paper and pencil is not scalable or reliable

### The Solution

A Telegram bot with Artificial Intelligence that allows you to:
- ✅ Register items through natural conversation
- ✅ Query inventory with simple messages
- ✅ Update quantities without forms
- ✅ Real database (PostgreSQL) with visual interface
- ✅ Operating cost: $6-22/month

**Usage example:**

```
👤 "Add 5 office chairs, good condition, warehouse A"
🤖 "✅ Registered: 5 office chairs
    🏷️ Condition: good condition
    📍 Location: warehouse A"
```

---

## ✨ Features

### Main Functionalities

- 🗣️ **Natural conversations** - No complex commands
- 📦 **Complete inventory management** - Create, query, modify items
- 🧠 **Conversational AI** - Understands context and extracts information automatically
- 📊 **Professional database** - PostgreSQL via Baserow
- 🔒 **Access control** - Only authorized users
- 💾 **Conversation memory** - Bot remembers context
- 📱 **Multi-platform** - Works from any device with Telegram

### Managed Fields

**Required:**
- Item name
- Quantity

**Optional (automatically extracted if mentioned):**
- Category
- Condition (new, used, good, etc.)
- Donor
- Location
- Additional notes

---

## 🎥 Demo

### Complete Conversation

**Query product:**
```
👤 How many units of 10mm screw

🤖 📦 10mm screw
   🔢 Code: 01-100-07
   📊 Quantity: 10 units
   ⚙️ Condition: N/A
```

**Create new item:**
```
👤 New item, 15mm screw, 10 u

🤖 ✅ Item created successfully
   📦 Code: 01-100-12
   📝 Name: 15mm screw
   📊 Quantity: 10
```

**Subtract units:**
```
👤 Subtract 2 u from 01-100-12

🤖 ✅ Inventory updated
   📦 15mm screw
   🔢 Code: 01-100-12
   Now: 8
```

**Add units:**
```
👤 Add 10 u to 01-100-12

🤖 ✅ Inventory updated
   📦 15mm screw
   🔢 Code: 01-100-12
   Now: 18
```

**Verify updated quantity:**
```
👤 Units of 15mm screw

🤖 📦 15mm screw
   🔢 Code: 01-100-12
   📊 Quantity: 18 units
   ⚙️ Condition: N/A
```

**Create product (with German text):**
```
👤 Add new products: lagerschaler 10 Stück

🤖 ✅ Item created successfully
   📦 Code: 01-100-13
   📝 Name: lagerschaler
   📊 Quantity: 10
```

**Update by code:**
```
👤 Add 10 u to item 01-100-13

🤖 ✅ Inventory updated
   📦 lagerschaler
   🔢 Code: 01-100-13
   Now: 20
```

**Contextual help:**
```
👤 Hello

🤖 ❌ I cannot continue because information is missing.
   
   Please write the message following ONE of these options:
   
   1️⃣ Query a product
   Example: "Query 4mm screw"
   Example: "Info on code 01-100-01"
   
   2️⃣ Add units to an existing product
   Example: "Add 5 units to 4mm screw"
   Example: "Add 3 to code 01-100-01"
   
   3️⃣ Create a new product
   Example: "Create new product: surgical glove, 10 units"
   Example: "Register new item: Bosch drill, 5 units"
   
   ⚠️ Important:
   New products are only created if you explicitly indicate it.
```

### Demonstrated Features

✅ **Smart search** - By name or code  
✅ **Automatic code generation** - Numeric system  
✅ **Mathematical operations** - Add/subtract inventory  
✅ **Multi-language** - Spanish, German, etc.  
✅ **Contextual help** - Guidance when there's an error  
✅ **Real-time updates** - Immediate changes  

### Screenshots

![Telegram Conversation](images/screenshot-telegram.png)
![Baserow Dashboard](images/screenshot-baserow.png)

---

## 🛠️ Technologies

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Automation** | [n8n](https://n8n.io) | Workflow orchestration |
| **AI** | [OpenAI GPT-4o-mini](https://openai.com) | Natural language processing |
| **Database** | [Baserow](https://baserow.io) | PostgreSQL with visual interface |
| **Interface** | [Telegram Bot API](https://core.telegram.org/bots) | Chat interface |
| **Deployment** | Docker | Containerization |

### Architecture

```
┌─────────────┐
│    User     │
│  (Telegram) │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  Telegram   │
│   Bot API   │
└──────┬──────┘
       │
       ▼
┌─────────────┐      ┌─────────────┐
│     n8n     │─────▶│   OpenAI    │
│ (Workflows) │      │  GPT-4o-mini│
└──────┬──────┘      └─────────────┘
       │
       ▼
┌─────────────┐
│   Baserow   │
│ (PostgreSQL)│
└─────────────┘
```

---

## 🚀 Installation

### Prerequisites

- [Telegram](https://telegram.org) account
- [Baserow](https://baserow.io) account (free)
- [OpenAI](https://platform.openai.com) account (requires payment)
- One of the following options for n8n:
  - **Option 1:** [n8n Cloud](https://n8n.cloud) account (~$20/month)
  - **Option 2:** VPS with Docker (from $5/month)

### Installation Options

We offer **3 installation levels** according to your technical experience:

#### 📱 Level 1: Database Only
**For:** Non-technical users who only want the database  
**Time:** 10 minutes  
**Cost:** Free  
📖 [View tutorial](docs/02-baserow-config.md)

#### 🚀 Level 2: Complete System (n8n Cloud)
**For:** People with basic knowledge  
**Time:** 30-40 minutes  
**Cost:** ~$22/month  
📖 [View tutorial](docs/03-n8n-cloud-installation.md)

#### 🛠️ Level 3: Complete System (Own VPS)
**For:** Technical people / Developers  
**Time:** 1-2 hours  
**Cost:** ~$6-7/month  
📖 [View tutorial](docs/04-vps-installation.md)

### Quick Guide (Level 2 - n8n Cloud)

1. **Configure Baserow**
   ```bash
   # See docs/02-baserow-config.md
   # Create account, table and get API token
   ```

2. **Create Telegram Bot**
   ```bash
   # Search for @BotFather in Telegram
   # /newbot
   # Save token
   ```

3. **Configure OpenAI**
   ```bash
   # Create account on platform.openai.com
   # Add payment method
   # Generate API key
   ```

4. **Create n8n Cloud instance**
   ```bash
   # Register on n8n.cloud
   # Create instance (14 days free)
   ```

5. **Import workflow**
   ```bash
   # Download workflows/inventario-baserow.json
   # Import into n8n
   # Configure credentials
   ```

6. **Ready!** Send a message to your Telegram bot

---

## 💻 Usage

### Basic Commands

The bot does NOT use traditional commands. Only natural conversation:

**Greet / View menu:**
```
"Hello"
"Hi"
"Good morning"
```

**Create item (minimum):**
```
"Create 5 chairs"
"10 hammers"
"Add 3 laptops"
```

**Create item (complete):**
```
"Create 5 office chairs, in good condition, donated by John, warehouse A"
```

**Query:**
```
"Query chairs"
"How many tables do I have?"
"Search laptops"
```

**Modify quantity:**
```
"Increase 10 chairs"
"Add 5 tables"
"Remove 3 laptops"
"Decrease 2 hammers"
```

### Typical Workflow

1. User greets the bot
2. Bot shows menu of options
3. User selects option (or types directly)
4. Bot processes with AI and extracts information
5. If mandatory info is missing, bot asks
6. Bot confirms and executes action
7. Data is automatically saved in Baserow

---

## 📚 Documentation

### Available Documents

| Document | Description | Audience |
|----------|-------------|----------|
| [General Instructions](docs/01-general-instructions.md) | Overview and route decision | Everyone |
| [Baserow Configuration](docs/02-baserow-config.md) | Database setup | Beginners |
| [n8n Cloud Installation](docs/03-n8n-cloud-installation.md) | Complete system (easy) | Non-technical |
| [VPS Installation](docs/04-vps-installation.md) | Complete system (advanced) | Technical |

### Additional Files

- `workflows/inventario-baserow.json` - n8n workflow ready to import
- `prompts/agente-inventario.txt` (ES) - Optimized OpenAI prompts (Spanish)
- `prompts/agente-inventario.en.txt` (EN) - Optimized OpenAI prompts (English)
- `ejemplos/datos-ejemplo.csv` - Sample data for Baserow

---

## 💰 Costs

### Options Comparison

| Component | Option 1<br>(DB Only) | Option 2<br>(n8n Cloud) | Option 3<br>(VPS) |
|-----------|---------------------|---------------------|-----------------|
| Baserow | Free | Free | Free |
| OpenAI API | - | ~$1-2/month | ~$1-2/month |
| n8n | - | $20/month | - |
| Hosting | - | - | $5/month |
| **Total** | **$0** | **~$22/month** | **~$6-7/month** |

### Notes on Costs

- **Baserow:** Free up to 5,000 rows (sufficient for most cases)
- **OpenAI:** Typical usage $1-2/month with GPT-4o-mini. You can set limits.
- **n8n Cloud:** $20/month (Starter plan). 14 days free trial.
- **VPS:** From $5/month (Hostinger, DigitalOcean, etc.)

---

## 🗺️ Roadmap

### Current Version: v1.0

- [x] Natural conversations in Spanish
- [x] Complete CRUD of inventory
- [x] Integration with Baserow
- [x] Conversation memory
- [x] User access control
- [x] Complete documentation

### Version 1.1 (In progress)

- [ ] Advanced search with filters
- [ ] Export reports via Telegram
- [ ] Low stock alerts
- [ ] QR code support
- [ ] Voice commands

### Version 2.0 (Future)

- [ ] Multi-language support
- [ ] Item photos
- [ ] WhatsApp integration
- [ ] Web dashboard
- [ ] Public REST API
- [ ] Native mobile app

### Contributions Welcome

Have ideas to improve? Open an [Issue](../../issues) or submit a [Pull Request](../../pulls)

---

## 🤝 Contributing

Contributions are what make the open source community amazing! Any contribution you make will be **greatly appreciated**.

### How to Contribute

1. Fork the project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Areas Where We Need Help

- 📖 Improve documentation
- 🌍 Translations to other languages
- 🐛 Report and fix bugs
- ✨ New features
- 🎨 UX improvements in conversations
- 📹 Tutorial videos

### Style Guide

- Commits in English or Spanish
- Well-commented code
- Follow existing file structure
- Test before making PR

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

This means you can:
- ✅ Use commercially
- ✅ Modify
- ✅ Distribute
- ✅ Private use

With the only condition of:
- ⚠️ Include the license and copyright notice

---

## 📞 Contact

**Name** - [@instagram](https://www.instagram.com/fguevara.ia/)

**Project:** [https://github.com/f-guevara/inventory-ai-telegram](https://github.com/f-guevara/inventory-ai-telegram)

**LinkedIn:** [https://www.linkedin.com/in/fernandoguevara-erpsystems/](https://www.linkedin.com/in/fernandoguevara-erpsystems/)

---

## 🙏 Acknowledgments

- [n8n](https://n8n.io) - For the incredible automation platform
- [Baserow](https://baserow.io) - For the open source database
- [OpenAI](https://openai.com) - For making AI accessible
- [Telegram](https://telegram.org) - For the free bot API
- The open source community - For inspiring this project

---

## ⭐ Star History

If this project was useful to you, consider giving it a star ⭐

[![Star History Chart](https://api.star-history.com/svg?repos=f-guevara/inventory-ai-telegram&type=Date)](https://star-history.com/#f-guevara/inventory-ai-telegram&Date)

---

## 📊 Statistics

![GitHub Stars](https://img.shields.io/github/stars/f-guevara/inventory-ai-telegram?style=social)
![GitHub Forks](https://img.shields.io/github/forks/f-guevara/inventory-ai-telegram?style=social)
![GitHub Issues](https://img.shields.io/github/issues/f-guevara/inventory-ai-telegram)
![GitHub Pull Requests](https://img.shields.io/github/issues-pr/f-guevara/inventory-ai-telegram)

---

**Made with ❤️ for the open source community**