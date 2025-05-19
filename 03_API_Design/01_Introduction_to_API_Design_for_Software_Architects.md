# 📘 Introduction to API Design for Software Architects

## 🎯 Introduction and Motivation

In this lecture, we explore the **design of Application Programming Interfaces (APIs)** for large-scale systems. A well-designed API acts as a **contract** between the system and its clients—enabling integration, scalability, and maintainability without exposing internal implementation details.

After gathering functional requirements, we view the system as a **black box** that exhibits behavior through a well-defined interface—our API.

## 🔍 What is an API?

An **API (Application Programming Interface)** is a contract:
* Between developers who **implement** the system.
* And clients who **consume** it—such as:
  * Web or mobile frontends,
  * External systems,
  * Internal services.

In large-scale systems, APIs are typically accessed **remotely over the network** and are crucial for integration across platforms and teams.

## 🧭 Categories of APIs

### 🌐 Public APIs
* Exposed to the general public.
* Open for integration by any developer.
* Recommended practices:
  * Require registration.
  * Monitor and control access.
  * Blacklist malicious actors.

### 🏢 Private APIs
* Used internally within an organization.
* Enable collaboration and reuse across internal systems without public exposure.

### 🤝 Partner APIs
* Exposed to third parties with **formal agreements** (e.g., paying customers or partners).
* Controlled access via contractual relationships.

## ✅ Benefits of Defining an API

* **Accelerates client development**—clients can integrate before implementation is complete.
* **Decouples system design**—internal architecture can evolve independently.
* **Improves scalability** and **interoperability**.

## 🧠 API Design Principles and Best Practices

### 🛡️ 1. Encapsulation & Abstraction
* Internal implementation must remain **hidden**.
* Clients should not require **knowledge of internal business logic**.

### 🔗 2. Decoupling
* Ensure clients are **not tightly coupled** to the internal structure.
* Enables system evolution without breaking the API contract.

### 🎯 3. Simplicity & Usability
* Easy to understand and hard to misuse.
* Strategies:
  * Provide **a single way** to perform each operation.
  * Use **descriptive and consistent** naming conventions.
  * Expose only **necessary** information.

### 🔁 4. Idempotency
* An operation is idempotent if **repeating it yields the same result**.
* Examples:
  * ✅ `Update address` → idempotent.
  * ❌ `Increase balance by $100` → not idempotent.
* Idempotency is critical due to **network uncertainties** (e.g., retries, timeouts).

### 📄 5. Pagination
* Required for **large result sets** (e.g., emails, products).
* Helps reduce payload size and improve **user experience**.
* Common implementation:
  * `limit` → number of items per page.
  * `offset` → where to start in the dataset.

### ⏳ 6. Asynchronous APIs
* Suitable for **long-running operations** (e.g., video processing, big data reports).
* The client receives an **immediate response** with a tracking ID.
* Client polls or subscribes for result status.

### 🔢 7. API Versioning
* APIs must support **versioning** to accommodate breaking changes.
* Allows maintaining **multiple versions**:
  * Example: `/v1/resource`, `/v2/resource`
* Enables **graceful deprecation** of older versions.

## 🧾 Summary

In this lecture, we covered:

* **What an API is** and its role as a **contract** for remote system interaction.
* The **three categories** of APIs:
  * Public,
  * Private,
  * Partner.
* Key **best practices and patterns** for designing robust APIs:
  * ✅ Encapsulation & abstraction
  * ✅ Usability and simplicity
  * ✅ Idempotent operations
  * ✅ Pagination for large datasets
  * ✅ Asynchronous handling for long tasks
  * ✅ Explicit versioning

In the next lectures, we will explore **common API styles and protocols** used in the industry today.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/05_SLA%2C_SLO%2C_SLI.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/03_API_Design/02_RPC.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
