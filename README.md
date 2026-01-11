# NaBus

**NaBus (Sodium Bus)** is a high-performance, schema-based distributed **event broker** —  
inspired by Kafka and RabbitMQ, but with **honey on top** 🍯.

NaBus is built for modern systems that want **strong schemas**, **simple contracts**, and **it just works™** ergonomics.

---

## What is NaBus?

NaBus is an **event broker** that lets producers and consumers communicate through
**strongly-defined schemas**, using **gRPC under the hood** for speed and reliability.

Instead of fighting with serialization formats, versioning chaos, or glue code,
you define your data **once** using **JSON Schema**, and NaBus takes care of the rest.

Think:

- Kafka-like durability & streaming
- RabbitMQ-like simplicity
- Schema-first by default
- gRPC performance
- Honey on top 🍯

---

## Key Features

- 🚀 **High-performance event broker**
- 📜 **Schema-first** (JSON Schema)
- 🔒 **Strong contracts between producers & consumers**
- ⚡ **gRPC-based transport**
- 🧠 **Automatic validation & compatibility**
- 🔄 **Event streaming & pub/sub**
- 🧩 **Language-agnostic clients**
- 🛠 **Simple, powerful CLI**

---

## Architecture Overview

NaBus is composed of **separate projects**:

| Project           | Description                             |
| ----------------- | --------------------------------------- |
| **NaBus**         | Core event broker (this repository)     |
| **nbus-cli**      | Command-line interface (separate repo)  |
| **NaBus Clients** | Language-specific SDKs (separate repos) |

This keeps the core broker clean, stable, and focused.

---

## Schema-Based by Design

NaBus is **schema-first**.

You define events using **JSON Schema**:

```json
{
  "$id": "user.created",
  "type": "object",
  "properties": {
    "id": { "type": "string" },
    "email": { "type": "string", "format": "email" },
    "createdAt": { "type": "string", "format": "date-time" }
  },
  "required": ["id", "email", "createdAt"]
}
```

NaBus is primarily written in Rust. Rust is chosen for its performance, reliability, and strong type system, which helps in building a robust event broker. Its ownership model ensures memory safety without needing a garbage collector, making it ideal for high-performance applications like NaBus. Plus, with Rust's growing ecosystem, it's easier than ever to find libraries and tools to help with development.

---
