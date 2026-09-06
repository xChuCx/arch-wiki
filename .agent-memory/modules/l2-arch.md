# L2 Architectural Patterns & Styles
<!-- @id: l2-architectural-patterns-styles -->

<!-- @id: l2-arch-01-monolith-layered-hexagonal-modularity -->
## L2.ARCH.01 Monolith - Layered, Hexagonal, Modularity
<!-- @id: l2-arch-01-monolith-layered-hexagonal-modularity -->
**Executive Summary:** **TL;DR**: Монолит — это **единица развертывания**, а не характеристика качества кода. Современный архитектурный стандарт для старта проектов и большинства Enterprise-систем — **Modular Monolith (Modulith)** с использованием гексагональной архитектуры внутри модулей. Главная задача эксперта — управление **coupling** (связностью) через строгие грани

- **Full Article Access:** [L2.ARCH.01 Monolith - Layered, Hexagonal, Modularity.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.01 Monolith - Layered, Hexagonal, Modularity.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.01 Monolith - Layered, Hexagonal, Modularity.md`

---

<!-- @id: l2-arch-02-microservices-autonomy-data-ownership-c -->
## L2.ARCH.02 Microservices - autonomy, data ownership, Conway’s Law
<!-- @id: l2-arch-02-microservices-autonomy-data-ownership-conway-s-law -->
**Executive Summary:** **TL;DR**: Микросервисы — это архитектурный стиль, направленный на достижение **Loose Coupling (Слабой связности)** и **High Cohesion (Высокого сцепления)** через физическое разделение сервисов. Главная цена — сложность управления распределенными данными (Data Ownership) и операционная нагрузка.

- **Full Article Access:** [L2.ARCH.02 Microservices - autonomy, data ownership, Conway’s Law.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.02 Microservices - autonomy, data ownership, Conway’s Law.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.02 Microservices - autonomy, data ownership, Conway’s Law.md`

---

<!-- @id: l2-arch-03-soa-vs-microservices-vs-eda -->
## L2.ARCH.03 SOA vs microservices vs EDA
<!-- @id: l2-arch-03-soa-vs-microservices-vs-eda -->
**Executive Summary:** **TL;DR**: *   **SOA (Service-Oriented Architecture)** — это стратегия **интеграции масштаба предприятия** (Enterprise Scope). Цель: переиспользование сервисов разными департаментами. Главный антипаттерн: ESB (Smart Pipes). *   **Microservices** — это стратегия **построения приложений** (Application Scope). Цель: скорость изменений (Velocity) и нез

- **Full Article Access:** [L2.ARCH.03 SOA vs microservices vs EDA.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.03 SOA vs microservices vs EDA.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.03 SOA vs microservices vs EDA.md`

---

<!-- @id: l2-arch-04-event-driven-architecture-event-sourcin -->
## L2.ARCH.04 Event‑Driven Architecture - event sourcing, CQRS
<!-- @id: l2-arch-04-event-driven-architecture-event-sourcing-cqrs -->
**Executive Summary:** **TL;DR**: *   **EDA** — это стиль коммуникации (асинхронность). *   **CQRS** — это стиль разделения ответственности (разные модели для записи и чтения). *   **Event Sourcing** — это стиль персистенции (храним историю изменений, а не текущее состояние). **Expert Rule**: CQRS можно использовать без Event Sourcing. Но Event Sourcing практически невоз

- **Full Article Access:** [L2.ARCH.04 Event‑Driven Architecture - event sourcing, CQRS.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.04 Event‑Driven Architecture - event sourcing, CQRS.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.04 Event‑Driven Architecture - event sourcing, CQRS.md`

---

<!-- @id: l2-arch-05-serverless-architecture-internals-trade -->
## Инициализация ВНЕ хендлера (выполняется 1 раз на Cold Start)
<!-- @id: 1-cold-start -->
**Executive Summary:** **TL;DR**: Serverless (FaaS) — это архитектура "Scale-to-Zero". Она идеальна для непрогнозируемых нагрузок и "склеивания" сервисов (Glue Code), но ужасна для Long-running процессов и Low-latency систем (из-за Cold Starts). Главная сложность экспертного уровня — управление состоянием (Stateless nature) и гарантия идемпотентности в распределенной сре

- **Full Article Access:** [L2.ARCH.05 Serverless Architecture - Internals & Trade-offs.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.05 Serverless Architecture - Internals & Trade-offs.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.05 Serverless Architecture - Internals & Trade-offs.md`

---

<!-- @id: l2-arch-06-lambda-architecture-batch-speed-serving -->
## L2.ARCH.06 Lambda architecture (batch+speed+serving)
<!-- @id: l2-arch-06-lambda-architecture-batch-speed-serving -->
**Executive Summary:** **TL;DR**: Lambda Architecture — это паттерн проектирования обработки данных, который решает дилемму "низкая задержка (Latency) vs высокая точность/полнота (Accuracy)". Он достигает этого путем запуска двух параллельных путей обработки: **Batch Layer** (для точности и исторических данных) и **Speed Layer** (для оперативных данных), результаты котор

- **Full Article Access:** [L2.ARCH.06 Lambda architecture (batch+speed+serving).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.06 Lambda architecture (batch+speed+serving).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.06 Lambda architecture (batch+speed+serving).md`

---

<!-- @id: l2-arch-07-kappa-architecture-stream-only -->
## L2.ARCH.07 Kappa architecture (stream‑only)
<!-- @id: l2-arch-07-kappa-architecture-stream-only -->
**Executive Summary:** **TL;DR**: Kappa Architecture — это архитектурный паттерн, где **Stream Processing** является единственным способом обработки данных. Мы отказываемся от Batch Layer. Исходным источником истины становится **неизменяемый лог событий** (Log) с длительным сроком хранения. Пересчет данных (Reprocessing) выполняется путем "перемотки" (Replay) потока из л

- **Full Article Access:** [L2.ARCH.07 Kappa architecture (stream‑only).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.07 Kappa architecture (stream‑only).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.07 Kappa architecture (stream‑only).md`

---

<!-- @id: l2-arch-08-cell-based-multi-tenant-isolation -->
## Usage
<!-- @id: usage -->
**Executive Summary:** **TL;DR**: Cell-Based Architecture (Клеточная архитектура) — это паттерн разбиения системы на множество идентичных, изолированных экземпляров (Cells), каждый из которых может обслужить только фиксированное подмножество трафика или тенантов. Это **"Bulkhead Pattern" на уровне всего дата-центра**. Главная цель — минимизация **Blast Radius** (радиуса 

- **Full Article Access:** [L2.ARCH.08 Cell‑based & multi‑tenant isolation.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.08 Cell‑based & multi‑tenant isolation.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.08 Cell‑based & multi‑tenant isolation.md`

---

<!-- @id: l2-arch-09-micro-frontends -->
## L2.ARCH.09 Micro‑frontends
<!-- @id: l2-arch-09-micro-frontends -->
**Executive Summary:** **TL;DR**: Микрофронтенды (MFE) — это архитектурный стиль, при котором фронтенд-приложение декомпозируется на независимые, отдельно развертываемые артефакты, которые "склеиваются" в runtime или на этапе build. **Главная цель**: Масштабирование **организации** (независимые релизы команд), а не масштабирование **производительности** (часто производит

- **Full Article Access:** [L2.ARCH.09 Micro‑frontends.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.09 Micro‑frontends.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.09 Micro‑frontends.md`

---

<!-- @id: l2-arch-10-api-gateway-vs-bff-vs-service-mesh -->
## L2.ARCH.10 API Gateway vs BFF vs Service Mesh
<!-- @id: l2-arch-10-api-gateway-vs-bff-vs-service-mesh -->
**Executive Summary:** **TL;DR**: *   **API Gateway** — это "Вышибала" (The Bouncer) на входе в клуб. Управляет трафиком **North-South** (Клиент -> Система). Отвечает за *политики* (AuthN, Rate Limiting, Billing). *   **BFF (Backend for Frontend)** — это "Консьерж" для конкретного VIP-клиента. Адаптирует данные под специфику UI (Mobile vs Web). Отвечает за *User Experien

- **Full Article Access:** [L2.ARCH.10 API Gateway vs BFF vs Service Mesh.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.10 API Gateway vs BFF vs Service Mesh.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.10 API Gateway vs BFF vs Service Mesh.md`

---

<!-- @id: l2-arch-11-multi-region-architectures-active-activ -->
## L2.ARCH.11 Multi-Region Architectures - Active-Active vs Active-Passive
<!-- @id: l2-arch-11-multi-region-architectures-active-active-vs-active-pa -->
**Executive Summary:** **TL;DR**: *   **Active-Passive (A-P)** — это стратегия **Disaster Recovery (DR)**. Она про RTO/RPO. Главная сложность: автоматизация переключения (Failover) и риск потери данных при асинхронной репликации. *   **Active-Active (A-A)** — это стратегия **Low Latency & High Availability**. Главная сложность: теорема CAP, конфликты данных (Split-brain)

- **Full Article Access:** [L2.ARCH.11 Multi-Region Architectures - Active-Active vs Active-Passive.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.11 Multi-Region Architectures - Active-Active vs Active-Passive.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.11 Multi-Region Architectures - Active-Active vs Active-Passive.md`

---

<!-- @id: l2-arch-12-data-locality-edge-computing-cdn-integr -->
## L2.ARCH.12 Data locality, edge computing, CDN integration
<!-- @id: l2-arch-12-data-locality-edge-computing-cdn-integration -->
**Executive Summary:** **TL;DR**: В глобальных системах **Latency is the new Downtime**. Ваша задача — переместить вычисления и данные как можно ближе к пользователю, соблюдая при этом законы о хранении данных (Data Residency). CDN больше не "тупой кэш картинок", это программируемый слой (Edge), способный брать на себя роутинг, авторизацию и даже SSR (Server-Side Renderi

- **Full Article Access:** [L2.ARCH.12 Data locality, edge computing, CDN integration.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.12 Data locality, edge computing, CDN integration.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.12 Data locality, edge computing, CDN integration.md`

---

<!-- @id: l2-arch-13-strangler-fig-legacy-migration-patterns -->
## L2.ARCH.13 Strangler Fig & Legacy Migration patterns
<!-- @id: l2-arch-13-strangler-fig-legacy-migration-patterns -->
**Executive Summary:** **TL;DR**: Никогда не делайте "Big Bang Rewrite" (переписывание с нуля). Единственный работающий метод для крупных систем — инкрементальная миграция. Паттерн **Strangler Fig (Фикус-душитель)** — это стратегия перехвата трафика на границе системы. **Branch by Abstraction** — это стратегия перехвата вызовов внутри кода. **CDC (Change Data Capture)** 

- **Full Article Access:** [L2.ARCH.13 Strangler Fig & Legacy Migration patterns.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.13 Strangler Fig & Legacy Migration patterns.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.13 Strangler Fig & Legacy Migration patterns.md`

---

<!-- @id: l2-arch-14-api-management-policies-throttling-tier -->
## L2.ARCH.14 API Management policies - Throttling tiers, Monetization strategies, Developer Portal DX
<!-- @id: l2-arch-14-api-management-policies-throttling-tiers-monetization -->
**Executive Summary:** **TL;DR**: API Management — это не просто прокси-сервер Nginx перед вашим бэкендом. Это слой, превращающий **код** в **продукт**. *   **Throttling** — это ваша страховка от "шумных соседей" и инструмент сегментации клиентов (платишь больше — едешь быстрее). *   **Monetization** — это механизм биллинга, который должен быть встроен в шлюз, а не в код

- **Full Article Access:** [L2.ARCH.14 API Management policies - Throttling tiers, Monetization strategies, Developer Portal DX.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.14 API Management policies - Throttling tiers, Monetization strategies, Developer Portal DX.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.14 API Management policies - Throttling tiers, Monetization strategies, Developer Portal DX.md`

---

<!-- @id: l2-arch-15-webhooks-delivery-guarantees-hmac-signa -->
## УЯЗВИМЫЙ КОД
<!-- @id: section -->
**Executive Summary:** **TL;DR**: Отправка вебхука — это не вызов функции. Это обещание доставки (Delivery Guarantee). Вы должны построить систему, которая переживет даунтайм получателя в 24 часа, защитит вас от SSRF-атак (когда получатель атакует вашу же инфру) и гарантирует криптографическую целостность данных. И самое главное: вы не можете гарантировать *Exactly-Once*

- **Full Article Access:** [L2.ARCH.15 Webhooks & delivery guarantees (HMAC signature, retries, exponential backoff).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.15 Webhooks & delivery guarantees (HMAC signature, retries, exponential backoff).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.ARCH/L2.ARCH.15 Webhooks & delivery guarantees (HMAC signature, retries, exponential backoff).md`

---

