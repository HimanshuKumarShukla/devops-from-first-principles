# 11 — 🧠 Unit 01 Active Recall

> [!IMPORTANT]
> Rule: pehle answer mentally bolo. **Uske baad one-line answer dekho.**

---

## Level 1 — Foundation

**Q1. Internet aur Web same hain?**  
**A.** No. Internet underlying network hai; Web HTTP/HTTPS-based service ecosystem hai.

**Q2. Server fundamentally kya hai?**  
**A.** Computer/software system that listens for and serves requests.

**Q3. IP address ka role?**  
**A.** Network destination ko address/locate karna.

**Q4. Port ka role?**  
**A.** Correct network service endpoint identify karna.

**Q5. `localhost:3000` ka meaning?**  
**A.** Apni machine par port 3000 par listening service.

---

## Level 2 — HTTP & Transport

**Q6. HTTP ka basic model?**  
**A.** Request → Response.

**Q7. `GET` generally kisliye?**  
**A.** Data/resource retrieve karne ke liye.

**Q8. `POST` generally kisliye?**  
**A.** Resource/action create/submit karne ke liye.

**Q9. `404`?**  
**A.** Requested resource not found.

**Q10. `500`?**  
**A.** Server-side internal error.

**Q11. `502`?**  
**A.** Gateway/proxy ko upstream service se valid response nahi mila.

**Q12. TCP ka killer feature?**  
**A.** Reliable ordered byte-stream transport.

**Q13. UDP ka fundamental difference?**  
**A.** Datagram transport with no built-in reliable/ordered delivery guarantee.

**Q14. HTTP/3 kis transport technology ka use karta hai?**  
**A.** QUIC over UDP.

---

## Level 3 — DNS

**Q15. DNS ka core job?**  
**A.** Domain/hostname ko destination information mein resolve karna.

**Q16. Domain aur server same hain?**  
**A.** No.

**Q17. A record?**  
**A.** Hostname → IPv4.

**Q18. AAAA record?**  
**A.** Hostname → IPv6.

**Q19. CNAME?**  
**A.** Hostname → another hostname.

**Q20. `api.example.com` kya ho sakta hai?**  
**A.** Separate hostname/subdomain pointing to API infrastructure.

---

## Level 4 — Networking

**Q21. Private IP kya hai?**  
**A.** Private/internal network ke andar use hone wala address.

**Q22. Public IP?**  
**A.** Internet-routable address.

**Q23. Router ka role?**  
**A.** Packets ko networks ke beech appropriate next destination ki taraf forward karna.

**Q24. NAT?**  
**A.** Network addresses/connections ko translate/map karta hai.

**Q25. Firewall?**  
**A.** Rules ke basis par traffic allow/block karta hai.

**Q26. Database directly internet expose karna generally desirable hai?**  
**A.** No.

---

## Level 5 — Frontend / Backend

**Q27. React SPA production build typically kya produce karta hai?**  
**A.** Static browser-consumable HTML/CSS/JS assets.

**Q28. Client-side React primarily kahan execute hota hai?**  
**A.** User's browser.

**Q29. Node backend kahan execute hota hai?**  
**A.** Server-side infrastructure.

**Q30. Frontend/backend same machine par hona compulsory hai?**  
**A.** No.

**Q31. Next.js sirf browser mein run karta hai?**  
**A.** No, it can include both server-side and client-side execution.

---

## Level 6 — Nginx

**Q32. Nginx ke Pareto four roles?**  
**A.** Static serving, reverse proxy, TLS termination, load balancing.

**Q33. Reverse proxy?**  
**A.** Client request receive karke appropriate backend ko forward karta hai.

**Q34. Forward proxy kis side ko represent karta hai?**  
**A.** Client side.

**Q35. Reverse proxy kis side ko represent karta hai?**  
**A.** Server side.

**Q36. Node `3000` ko public expose karna compulsory hai?**  
**A.** No.

**Q37. Nginx simple static Docker webpage mein kya karta tha?**  
**A.** Static files serve karta tha.

---

## Level 7 — TLS

**Q38. HTTPS kya hai?**  
**A.** HTTP protected by TLS.

**Q39. TLS ke three core goals?**  
**A.** Confidentiality, integrity and authentication.

**Q40. Certificate ka basic role?**  
**A.** Server identity/authentication establish karne mein help karna.

**Q41. CA?**  
**A.** Certificate Authority.

**Q42. TLS termination?**  
**A.** Front layer incoming TLS handle karta hai and traffic onward forward karta hai.

**Q43. HTTPS means application fully secure?**  
**A.** No.

---

## Level 8 — Full Architecture

**Q44. Browser `https://shop.com/products` type karne ke baad first conceptual tasks?**  
**A.** URL parse + DNS resolution.

**Q45. DNS ke baad?**  
**A.** Network routes traffic to destination infrastructure.

**Q46. HTTPS request secure kaise hota hai?**  
**A.** TLS handshake and encrypted session.

**Q47. Public entry layer backend tak request kaise bhej sakta hai?**  
**A.** Reverse proxy/routing.

**Q48. React SPA API data flow?**  
**A.** Browser → Nginx → backend → database → backend → browser.

**Q49. Load balancer kyun?**  
**A.** Traffic multiple backend instances mein distribute karne ke liye.

**Q50. Cache kyun?**  
**A.** Repeated expensive access faster/cheaper banane ke liye.

**Q51. CDN kyun?**  
**A.** Content users ke geographically closer serve karne ke liye.

**Q52. Queue kyun?**  
**A.** Async/background work decouple aur buffer karne ke liye.

---

# 🔥 Interview Challenge — Explain Without Notes

Try verbally explaining:

```text
User types amazon.in
↓
DNS
↓
network routing
↓
TLS/HTTPS
↓
public entry/load balancer
↓
application services
↓
cache/database/search
↓
response
```

If tum 2–3 minutes mein confidently explain kar pao, Unit 01 ka foundation strong hai.
