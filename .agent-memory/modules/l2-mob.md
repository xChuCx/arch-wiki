# L2 Mobile, Client & Offline Architecture
<!-- @id: l2-mobile-client-offline-architecture -->

<!-- @id: l2-mob-01-offline-first-architectures-conflict-res -->
## L2.MOB.01 Offline-first architectures - Conflict Resolution strategies (Last-Write-Wins vs CRDT on client)
<!-- @id: l2-mob-01-offline-first-architectures-conflict-resolution-strate -->
**Executive Summary:** **TL;DR**: Offline-first означает, что приложение всегда пишет в **локальную БД**, а синхронизация происходит в фоне. Главная проблема — **конфликты слияния** (Merge Conflicts), возникающие, когда устройство возвращается в сеть. *   **LWW (Last-Write-Wins)**: Дешево и сердито, но теряет данные. Требует надежных часов (HLC). *   **CRDT (Conflict-fre

- **Full Article Access:** [L2.MOB.01 Offline-first architectures - Conflict Resolution strategies (Last-Write-Wins vs CRDT on client).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.MOB/L2.MOB.01 Offline-first architectures - Conflict Resolution strategies (Last-Write-Wins vs CRDT on client).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.MOB/L2.MOB.01 Offline-first architectures - Conflict Resolution strategies (Last-Write-Wins vs CRDT on client).md`

---

<!-- @id: l2-mob-02-battery-bandwidth-optimization-batching- -->
## L2.MOB.02 Battery & Bandwidth optimization - Batching, binary protocols, radio wake-up patterns
<!-- @id: l2-mob-02-battery-bandwidth-optimization-batching-binary-protoco -->
**Executive Summary:** **TL;DR**: Самый энергоемкий компонент после экрана — это **Radio Unit** (Cellular/Wi-Fi). Оптимизация батареи сводится к минимизации времени активности радиомодуля. *   **Правило**: "Burst transmission" (передача пачками) лучше, чем "Constant trickle" (постоянная капель). *   **Инструменты**: Protobuf (сжатие данных), Batching (сжатие времени), Wo

- **Full Article Access:** [L2.MOB.02 Battery & Bandwidth optimization - Batching, binary protocols, radio wake-up patterns.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.MOB/L2.MOB.02 Battery & Bandwidth optimization - Batching, binary protocols, radio wake-up patterns.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.MOB/L2.MOB.02 Battery & Bandwidth optimization - Batching, binary protocols, radio wake-up patterns.md`

---

<!-- @id: l2-mob-03-backend-for-frontend-bff-patterns-aggreg -->
## L2.MOB.03 Backend for Frontend (BFF) patterns - Aggregation, trimming, protocol translation
<!-- @id: l2-mob-03-backend-for-frontend-bff-patterns-aggregation-trimming -->
**Executive Summary:** **TL;DR**: BFF — это слой презентационной логики, перенесенный с клиента на сервер. Его главная задача — оптимизировать взаимодействие между клиентом и бэкендом, скрывая сложность микросервисного ландшафта. *   **Главный принцип**: BFF принадлежит команде фронтенда/мобильной разработки ("Client on the Server"). *   **Ключевые функции**: Агрегация (

- **Full Article Access:** [L2.MOB.03 Backend for Frontend (BFF) patterns - Aggregation, trimming, protocol translation.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.MOB/L2.MOB.03 Backend for Frontend (BFF) patterns - Aggregation, trimming, protocol translation.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.MOB/L2.MOB.03 Backend for Frontend (BFF) patterns - Aggregation, trimming, protocol translation.md`

---

