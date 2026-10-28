# 🪙 CustomEconomy

A lightweight, high-performance, and **asynchronous SQL-backed economy plugin** designed for Paper/Spigot Minecraft servers. Built with modern data persistence practices to ensure zero main-thread lag, secure transactions, and absolute data integrity.

---

## ✨ Features

* **Asynchronous Database Operations:** All queries, saves, and loads run on separate threads to prevent any server lag or tick drops.
* **Dual Database Support:** Native support for local **SQLite** (zero configuration required) and remote **MySQL** for multi-server networks.
* **In-Memory Caching:** Player balances are cached in RAM (`ConcurrentHashMap`) for instant lookups during gameplay (`/balance`, `/pay`).
* **Safe Transactions:** Built-in anti-exploit checks preventing negative values, self-payments, and duplication glitches.
* **LuckPerms Integration:** Fully compatible with permission plugins without requiring operator (`OP`) privileges.

---

## 📋 Commands & Aliases

| Command | Description | Alias | Permission |
| :--- | :--- | :--- | :--- |
| `/balance [player]` | Check your balance or another player's balance. | `/bal`, `/money` | `customeconomy.balance` |
| `/pay <player> <amount>` | Send money to another online player. | *None* | `customeconomy.pay` |
| `/economy <give\|take\|set\|reset> <player> [amount]` | Admin commands to manage player balances. | `/eco` | `customeconomy.admin` |

---

## 🔒 Permissions

```yaml
permissions:
  customeconomy.balance:
    description: Allows players to check their balance.
    default: true
  customeconomy.pay:
    description: Allows players to pay money to others.
    default: true
  customeconomy.admin:
    description: Full access to admin economy management commands.
    default: op
