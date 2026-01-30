# Blockchain for 5G Healthcare Applications

## 📌 Project Overview

This project demonstrates the use of **blockchain technology** in the **healthcare domain**, combined with a **5G network simulation**. The application enables secure storage of healthcare documents (PDF files) in a blockchain, verification of their integrity, and restoration of the original data.

The main goal of the project is to practically demonstrate how blockchain can ensure:
- immutability of healthcare records,
- transparency of changes,
- data integrity and verifiability,

while also highlighting how **low-latency 5G networks** enable fast transmission of sensitive medical information.

The project is implemented as a **Flask-based web application** and is primarily intended for **educational and demonstration purposes**.

---

## 🧠 Motivation

Healthcare data belongs to the most sensitive categories of information. In traditional systems:
- data is stored centrally,
- records can be modified retrospectively,
- auditing and change tracking are complex.

Blockchain addresses these issues by ensuring that:
- each document is stored as a block,
- each block contains the hash of the previous block,
- any modification breaks the integrity of the entire chain.

When combined with 5G networks, this allows:
- fast data uploads from healthcare facilities,
- minimal latency when accessing records,
- support for real-time healthcare applications.

---

## 🏗️ Application Architecture

The application is divided into three main components:

### 1️⃣ Web Layer (Flask)
- handling HTTP requests,
- uploading PDF documents,
- REST endpoints for blockchain mining and network simulation,
- rendering the web interface.

### 2️⃣ Blockchain Layer
- custom blockchain implementation,
- Proof-of-Work mechanism,
- data integrity verification,
- persistent storage using a JSON file.

### 3️⃣ 5G Network Simulation
- simulation of low network latency,
- demonstration of fast system response,
- foundation for future extensions (2G / 4G / 5G).

---

## 🔗 Blockchain – Technical Description

### 📦 Block Structure

Each block in the blockchain contains:

- `no` – block index,
- `nonce` – number used during mining,
- `data` – Base64-encoded PDF document,
- `hashcode` – SHA-256 block hash,
- `prev` – hash of the previous block.

```text
Block = {
  no,
  nonce,
  data,
  hashcode,
  prev
}
