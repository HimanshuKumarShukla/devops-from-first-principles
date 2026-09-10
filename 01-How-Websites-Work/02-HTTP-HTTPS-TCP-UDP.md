# 02 — 📡 HTTP, HTTPS, TCP & UDP

> [!IMPORTANT]
> ## 🔵 Core Idea
> HTTP defines web request/response semantics, while transport protocols such as TCP or QUIC move data across the network.

## ⚡ Pareto — Remember This

```text
HTTP  → What are we saying?
TCP   → Reliable ordered transport
UDP   → Datagram transport with fewer built-in guarantees
IP    → Where is it going?
HTTPS → HTTP protected by TLS
```

---

## 1. HTTP — Request → Response

HTTP = **Hypertext Transfer Protocol**

Core model:

```text
CLIENT                         SERVER
   │
   │ GET /products
   │─────────────────────────►
   │
   │ 200 + product data
   │◄─────────────────────────
```

### Common HTTP Methods

| Method | Typical Meaning |
|---|---|
| `GET` | Read/retrieve |
| `POST` | Create/submit |
| `PUT` | Replace/update |
| `PATCH` | Partial update |
| `DELETE` | Delete |

Example:

```http
GET /products
```

```json
[
  {
    "name": "Laptop",
    "price": 60000
  }
]
```

---

## 2. Important Status Codes

| Code | Meaning |
|---:|---|
| `200` | OK |
| `201` | Created |
| `301/302` | Redirect |
| `400` | Bad Request |
| `401` | Authentication required / not authenticated |
| `403` | Forbidden |
| `404` | Not Found |
| `500` | Internal Server Error |
| `502` | Bad Gateway |
| `503` | Service Unavailable |

> [!WARNING]
> ## 🔴 DevOps Signal
> `502 Bad Gateway` often means a gateway/proxy could not get a valid response from an upstream service.

Example:

```text
Browser
   ↓
Nginx
   ↓
Node ❌
```

Possible result:

```text
502 Bad Gateway
```

---

## 3. HTTP vs HTTPS

```text
HTTP
  +
TLS
  =
HTTPS
```

More precisely:

> HTTPS is HTTP carried over a TLS-protected connection.

Common ports:

```text
HTTP  → 80
HTTPS → 443
```

---

## 4. TCP

TCP = **Transmission Control Protocol**

Key properties:

- Connection-oriented
- Reliable delivery
- Ordered byte stream
- Retransmission
- Flow/congestion mechanisms

### Simplified Handshake

```text
CLIENT                     SERVER

   │ ---- SYN ------------> │
   │ <--- SYN + ACK ------- │
   │ ---- ACK ------------> │
   │                        │
   │ ===== DATA ==========> │
```

This is the **TCP three-way handshake**.

### Why reliability matters

Suppose data units are conceptually:

```text
1 2 3 4 5
```

If `3` is lost, TCP has mechanisms that allow recovery/retransmission so the receiving application gets the ordered byte stream.

---

## 5. UDP

UDP = **User Datagram Protocol**

Properties:

- Connectionless
- Datagram-based
- No built-in delivery guarantee
- No built-in ordering guarantee
- Lower protocol overhead than TCP

```text
SEND datagram
SEND datagram
SEND datagram
```

> [!WARNING]
> ## 🔴 Don't Oversimplify
> **UDP = fast and TCP = slow** is a bad rule.  
> Real performance depends on workload, network conditions and higher-level protocol design.

### Important Modern Example

HTTP/3 uses **QUIC**, and QUIC runs over UDP while implementing sophisticated reliability/security behavior above it.

---

## 6. Layer Mental Model

```text
┌───────────────────────────┐
│ HTTP / HTTPS              │ ← Application/web semantics
├───────────────────────────┤
│ TCP / UDP / QUIC          │ ← Transport
├───────────────────────────┤
│ IP                        │ ← Addressing/routing
├───────────────────────────┤
│ Wi‑Fi / Ethernet etc.     │ ← Link/physical
└───────────────────────────┘
```

> [!TIP]
> Ye full networking model nahi hai, but DevOps learning ke current stage ke liye excellent mental model hai.

---

## 🔑 Keywords

`HTTP` `HTTPS` `Request` `Response` `Status Code`  
`TCP` `UDP` `Handshake` `Reliable Delivery` `Ordered Byte Stream` `Datagram` `QUIC`

---

## 🧠 Active Recall — Short Answers

**Q1. HTTP ka fundamental model?**  
Request → Response.

**Q2. `GET` generally kisliye?**  
Data/resource retrieve karne ke liye.

**Q3. `POST` generally kisliye?**  
New resource/action create/submit karne ke liye.

**Q4. `404`?**  
Requested resource not found.

**Q5. `500`?**  
Server-side internal error.

**Q6. `502`?**  
Gateway/proxy ko upstream service se valid response nahi mila.

**Q7. TCP ka killer feature?**  
Reliable, ordered byte-stream transport.

**Q8. UDP ka core difference?**  
Datagram transport with no built-in reliable/ordered delivery guarantee.

**Q9. HTTPS kya hai?**  
HTTP protected by TLS.

**Q10. HTTP/3 commonly kis transport technology par based hai?**  
QUIC over UDP.
