# Redis Learning Notes

Welcome to my **Redis** learning documentation repository. This repository contains notes and references regarding Redis commands and administration basics I've been studying.

---

## 📖 What is Redis?

**Redis** (*Remote Dictionary Server*) is an extremely fast, open-source, in-memory data structure store. It is widely used as:
- **Database**
- **Cache**
- **Message Broker**

Redis is highly performant due to its in-memory nature, making it an ideal solution for applications requiring low latency.

---

## 🛠️ Redis Administration & Connection Commands

Below are the commands I've learned for managing the Redis server, monitoring, and client connections.

### 1. Connection & Bulk Operations
| Command | Description |
| :--- | :--- |
| `redis-cli -h localhost -p 6379` | Connects to the local Redis server. |
| `redis-cli -h localhost -p 6379 -n 0 --pipe < input_file.txt` | Executes commands in bulk from a file via pipe. |
| `select 0` | Selects the Redis database by its index. |

### 2. Administration & Monitoring
| Command | Description |
| :--- | :--- |
| `monitor` | Real-time monitoring of all commands executed on the server. |
| `info` | Displays server statistics and general information. |
| `config get` | Retrieves server configuration settings (e.g., `config get *`). |

### 3. Client Management
| Command | Description |
| :--- | :--- |
| `client list` | Lists all clients currently connected to the server. |
| `client id` | Returns the unique ID of the current client connection. |
| `client kill <ip:port>` | Forcefully terminates a specific client connection. |

---

## 🚀 Redis Query Exploration (Input File)

This table provides a breakdown of the queries used in `input_file_redis.txt` during my learning process:

| Line | Command | Description |
| :--- | :--- | :--- |
| 1-3 | `setex key 30 val` | Sets a key with a value and a 30-second TTL (Time-to-Live). |
| 5 | `ttl key` | Gets the remaining time-to-live of a key. |
| 7 | `set key val` | Sets the value of a key. |
| 8 | `mset k1 v1 k2 v2` | Sets multiple keys simultaneously. |
| 9 | `expire key 10` | Sets a 10-second TTL for a specific key. |
| 11 | `keys *` | Lists all keys in the current database. |
| 12 | `get key` | Retrieves the value of a key. |
| 13 | `mget k1 k2` | Retrieves values for multiple keys. |
| 15-16 | `incr` / `decr` | Increments/decrements a numeric key's value by 1. |
| 18-19 | `incrby` / `decrby` | Increments/decrements a numeric key's value by N. |
| 21-24 | `multi` ... `discard` | Initiates a transaction and discards it. |
| 26-29 | `multi` ... `exec` | Initiates a transaction and executes it atomically. |
| 31 | `flushdb` | Deletes all data in the current database. |

---

## 📝 Note
This documentation serves as a personal reference guide. Ensure your Redis server is running before executing any of these commands.

---
*Happy Learning! 🚀*
