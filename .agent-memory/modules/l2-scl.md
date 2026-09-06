# L2 High Availability, Scalability & Fault Tolerance
<!-- @id: l2-high-availability-scalability-fault-tolerance -->

<!-- @id: l2-scl-01-horizontal-vs-vertical-scaling-scaling-l -->
## L2.SCL.01 Horizontal vs vertical scaling, scaling laws (Amdahl, Gustafson)
<!-- @id: l2-scl-01-horizontal-vs-vertical-scaling-scaling-laws-amdahl-gus -->
**Executive Summary:** **TL;DR**: Масштабируемость — это не магия добавления серверов, это **борьба с сериализацией и координацией**. *   **Vertical Scaling (Scale-Up):** Ограничено физикой **NUMA** и законом убывающей доходности. Идеально для сильной связности (Monolithic SQL). *   **Horizontal Scaling (Scale-Out):** Ограничено **сетью** и **законом USL** (Coherence Pen

- **Full Article Access:** [L2.SCL.01 Horizontal vs vertical scaling, scaling laws (Amdahl, Gustafson).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.01 Horizontal vs vertical scaling, scaling laws (Amdahl, Gustafson).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.01 Horizontal vs vertical scaling, scaling laws (Amdahl, Gustafson).md`

---

<!-- @id: l2-scl-02-sharding-strategies-range-hash-geo-custo -->
## L2.SCL.02 Sharding strategies - range, hash, geo, customer‑tier
<!-- @id: l2-scl-02-sharding-strategies-range-hash-geo-customer-tier -->
**Executive Summary:** **TL;DR**: Шардинг (Sharding) — это признание поражения перед физикой одного сервера. *   **Hash Sharding**: Максимальная пропускная способность записи, но убивает Range-запросы (превращает их в Scatter-Gather). Требует Consistent Hashing. *   **Range Sharding**: Идеален для сканирования (`BETWEEN`), но страдает от "Write Hotspots" (проблема моното

- **Full Article Access:** [L2.SCL.02 Sharding strategies - range, hash, geo, customer‑tier.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.02 Sharding strategies - range, hash, geo, customer‑tier.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.02 Sharding strategies - range, hash, geo, customer‑tier.md`

---

<!-- @id: l2-scl-03-consistent-hashing-cassandra-dynamo -->
## L2.SCL.03 Consistent hashing и виртуальные ноды (Cassandra, Dynamo)
<!-- @id: l2-scl-03-consistent-hashing-cassandra-dynamo -->
**Executive Summary:** **TL;DR**: Consistent Hashing — это алгоритм, который превращает хаос перебалансировки в математическую предсказуемость. *   **Проблема:** При обычном хешировании (`hash % N`) добавление одного сервера заставляет переехать 100% данных. Кластер встает. *   **Решение (The Ring):** Мы хешируем и данные, и серверы в одно кольцевое пространство ($0 \dot

- **Full Article Access:** [L2.SCL.03 Consistent hashing и виртуальные ноды (Cassandra, Dynamo).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.03 Consistent hashing и виртуальные ноды (Cassandra, Dynamo).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.03 Consistent hashing и виртуальные ноды (Cassandra, Dynamo).md`

---

<!-- @id: l2-scl-04-caching-patterns-read-through-write-thro -->
## L2.SCL.04 Caching patterns - read‑through, write‑through, write‑behind
<!-- @id: l2-scl-04-caching-patterns-read-through-write-through-write-behi -->
**Executive Summary:** **TL;DR**: Кэширование — это не просто ускорение чтения. Это механизм **управления консистентностью** и **сглаживания пиков** (Load Shedding). *   **Read-Through**: Кэш прозрачен. Приложение не знает о БД. Идеально для **защиты БД от "Thundering Herd"** (шторма запросов) через Request Coalescing. *   **Write-Through**: Синхронная запись в Кэш и БД.

- **Full Article Access:** [L2.SCL.04 Caching patterns - read‑through, write‑through, write‑behind.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.04 Caching patterns - read‑through, write‑through, write‑behind.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.04 Caching patterns - read‑through, write‑through, write‑behind.md`

---

<!-- @id: l2-scl-05-semantic-caching-the-ai-latency-shield -->
## User Context: {tenant: "corp_acme", roles: ["finance"], level: "confidential"}
<!-- @id: user-context-tenant-corp-acme-roles-finance-level-confidential -->
**Executive Summary:** **TL;DR**: Традиционный кэш (Exact Match) бесполезен для LLM из-за вариативности естественного языка. *   **Semantic Cache**: Кэширует **смысл** (вектор), а не текст. Позволяет вернуть ответ на вопрос "Как дела?", если в кэше уже есть ответ на "Как жизнь?". *   **Physics**: Вы меняете дорогой GPU-инференс (секунды) на дешевый Vector Search (миллисе

- **Full Article Access:** [L2.SCL.05 Semantic Caching - The AI Latency Shield.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.05 Semantic Caching - The AI Latency Shield.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.05 Semantic Caching - The AI Latency Shield.md`

---

<!-- @id: l2-scl-06-cache-invalidation-cache-stampede-dogpil -->
## L2.SCL.06 Cache invalidation, cache stampede, dogpile protection
<!-- @id: l2-scl-06-cache-invalidation-cache-stampede-dogpile-protection -->
**Executive Summary:** --- **TL;DR**: Инвалидация кэша — это проблема **распределенного консенсуса**. *   **Cache Stampede (Thundering Herd):** Когда тысячи запросов одновременно пробивают протухший кэш и убивают БД. Решение: **Singleflight** (барьер) или **Probabilistic Early Expiration**. *   **Invalidation Races:** Когда запись в БД и удаление из кэша рассинхронизирую

- **Full Article Access:** [L2.SCL.06 Cache invalidation, cache stampede, dogpile protection.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.06 Cache invalidation, cache stampede, dogpile protection.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.06 Cache invalidation, cache stampede, dogpile protection.md`

---

<!-- @id: l2-scl-07-rate-limiting-token-bucket-leaky-bucket -->
## L2.SCL.07 Rate limiting (token bucket, leaky bucket)
<!-- @id: l2-scl-07-rate-limiting-token-bucket-leaky-bucket -->
**Executive Summary:** **Rate Limiting (RL)** — это механизм управления **Backpressure** (обратным давлением), а не просто "блокировка спама". * **Token Bucket** = Разрешает **Berst** (всплески). Стандарт для UX/API. * **Leaky Bucket** = Сглаживает поток (**Smoothing**). Стандарт для защиты баз данных (Write path). * **Distributed State** = Главная боль. Выбор между *Strong Consistency* (Redis Lua, +Latency) и *Eventual

- **Full Article Access:** [L2.SCL.07 Rate limiting (token bucket, leaky bucket).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.07 Rate limiting (token bucket, leaky bucket).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.07 Rate limiting (token bucket, leaky bucket).md`

---

<!-- @id: l2-scl-08-circuit-breaker-bulkhead-retry-with-jitt -->
## Resilience4j Config Example
<!-- @id: resilience4j-config-example -->
**Executive Summary:** Надежность (Resilience) в распределенных системах — это не "как избежать сбоев", а "как изящно деградировать". * **Retry (Нападение):** Попытка скрыть *Transient Failure* (временный сбой). Опасен, так как умножает нагрузку. Требует **Jitter** и **Budget**. * **Circuit Breaker (Защита):** Предохранитель. Предотвращает каскадные сбои и дает бэкенду время на восстановление ("Fail Fast"). * **Bulkhead

- **Full Article Access:** [L2.SCL.08 Circuit breaker, bulkhead, retry with jitter.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.08 Circuit breaker, bulkhead, retry with jitter.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.08 Circuit breaker, bulkhead, retry with jitter.md`

---

<!-- @id: l2-scl-09-backpressure-async-reactive-streams -->
## L2.SCL.09 Backpressure в async системах (Reactive Streams)
<!-- @id: l2-scl-09-backpressure-async-reactive-streams -->
**Executive Summary:** В синхронном мире Backpressure бесплатен: если сервер БД тормозит, тред приложения блокируется. Если все треды заблокированы, мы перестаем принимать новые запросы.

- **Full Article Access:** [L2.SCL.09 Backpressure в async системах (Reactive Streams).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.09 Backpressure в async системах (Reactive Streams).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.09 Backpressure в async системах (Reactive Streams).md`

---

<!-- @id: l2-scl-10-idempotency -->
## --- INFRASTRUCTURE HEADERS ---
<!-- @id: infrastructure-headers -->
**Executive Summary:** В распределенных системах сеть ненадежна. Вы никогда не знаете, дошел ли ваш запрос, если вы получили `Timeout`. Единственная безопасная стратегия при ошибке — **повторить запрос (Retry)**. Но повтор опасен дублированием (списание денег дважды).

- **Full Article Access:** [L2.SCL.10 Idempotency ключей и безопасное повторение запросов.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.10 Idempotency ключей и безопасное повторение запросов.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.10 Idempotency ключей и безопасное повторение запросов.md`

---

<!-- @id: l2-scl-11-chaos-engineering-fault-injection-steady -->
## Пример из жизни
<!-- @id: section -->
**Executive Summary:** **Chaos Engineering** — это дисциплина экспериментирования на системе с целью создания уверенности в её способности выдерживать турбулентные условия эксплуатации.

- **Full Article Access:** [L2.SCL.11 Chaos Engineering - fault injection, steady‑state hypothesis.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.11 Chaos Engineering - fault injection, steady‑state hypothesis.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.11 Chaos Engineering - fault injection, steady‑state hypothesis.md`

---

<!-- @id: l2-scl-12-multi-region-replication-failover-runboo -->
## 🔴 [CRITICAL] REGION FAILOVER PROTOCOL
<!-- @id: critical-region-failover-protocol -->
**Executive Summary:**  Запустить приложение в `us-east-1` просто. Запустить его одновременно в `us-east-1`, `eu-central-1` и `ap-northeast-1` с гарантией консистентности данных — это инженерный подвиг.  **Главная дилемма:** Вы не можете победить скорость света.  - **Strong Consistency:** Данные всегда верны, но задержка огромна (транзакция через океан).  - **Eventual Consistency:** Работает быстро, но при падении регио

- **Full Article Access:** [L2.SCL.12 Multi‑region replication, failover runbooks.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.12 Multi‑region replication, failover runbooks.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.12 Multi‑region replication, failover runbooks.md`

---

<!-- @id: l2-scl-13-tail-latency-p99-p999-h-t-fairness -->
## 1. Посмотреть текущую дисциплину (qdisc)
<!-- @id: 1-qdisc -->
**Executive Summary:**  Если вы приходите ко мне с отчетом "Среднее время ответа (Avg/Mean) — 200мс", я вас выгоню.  - Если Билл Гейтс зайдет в бар, "в среднем" каждый посетитель станет миллионером.  - В распределенных системах **Mean Latency** скрывает проблемы.  - Ваши деньги и репутация живут в **Tail Latency** (Хвостовой задержке). Именно там ("в хвосте") сидят самые "дорогие" пользователи, генерирующие сложные запр

- **Full Article Access:** [L2.SCL.13 Tail latency, p99 p999, H‑T fairness.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.13 Tail latency, p99 p999, H‑T fairness.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.13 Tail latency, p99 p999, H‑T fairness.md`

---

<!-- @id: l2-scl-14-thundering-herd-mitigation-queueing-pre- -->
## Структура данных в Redis:
<!-- @id: redis -->
**Executive Summary:**  Представьте, что все будильники в городе звонят в одну секунду, и все жители одновременно спускают воду в туалете. Водопроводная система взорвется.  В IT это происходит, когда:  1. Истекает TTL популярного ключа в кэше (**Cache Stampede**).  2. Сервис перезагружается, и 100к клиентов делают Reconnect одновременно (**Connection Storm**).  3. Планировщик (Cron) запускает тяжелую задачу на 1000 серв

- **Full Article Access:** [L2.SCL.14 Thundering herd mitigation (queueing, pre‑warming).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.14 Thundering herd mitigation (queueing, pre‑warming).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.14 Thundering herd mitigation (queueing, pre‑warming).md`

---

<!-- @id: l2-scl-15-distributed-locking-redis-redlock-etcd-f -->
## Pseudo-code for Agentic Fencing
<!-- @id: pseudo-code-for-agentic-fencing -->
**Executive Summary:** Перед тем как написать `mutex.Lock()`, вы должны ответить на вопрос: **"Какова цена того, что распределенный лок откажет, и два процесса войдут в критическую секцию одновременно?"**

- **Full Article Access:** [L2.SCL.15 Distributed Locking (Redis Redlock, Etcd, Fencing tokens).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.15 Distributed Locking (Redis Redlock, Etcd, Fencing tokens).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.15 Distributed Locking (Redis Redlock, Etcd, Fencing tokens).md`

---

<!-- @id: l2-scl-16-distributed-transactions -->
## --- ACTIVITY LAYER (The Muscle) ---
<!-- @id: activity-layer-the-muscle -->
**Executive Summary:** **Распределенная транзакция** — это операция, затрагивающая данные на двух и более сетевых узлах (БД, сервисах).

- **Full Article Access:** [L2.SCL.16 Distributed transactions.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.16 Distributed transactions.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.16 Distributed transactions.md`

---

<!-- @id: l2-scl-17-deployment-strategies-blue-green-canary- -->
## Bad: Hardcoded Logic
<!-- @id: bad-hardcoded-logic -->
**Executive Summary:** **Deployment Strategy** — это методология обновления работающего приложения с версии $V_1$ на $V_2$ таким образом, чтобы минимизировать **Downtime** (время простоя) и **Impact** (влияние ошибок на пользователей).

- **Full Article Access:** [L2.SCL.17 Deployment strategies (Blue‑Green, Canary, Rolling).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.17 Deployment strategies (Blue‑Green, Canary, Rolling).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.17 Deployment strategies (Blue‑Green, Canary, Rolling).md`

---

<!-- @id: l2-scl-18-observability-metrics-logs-tracing-corre -->
## HELP http_request_duration_seconds A histogram of latency.
<!-- @id: help-http-request-duration-seconds-a-histogram-of-latency -->
**Executive Summary:**  **Monitoring** говорит вам, что система упала ("Health: Red"). Это про _Known Unknowns_ (мы знали, что диск может переполниться, и поставили алерт).  **Observability** объясняет, **почему** она упала. Это про _Unknown Unknowns_ (мы не знали, что новый микросервис вызывает дедлок в базе данных при определенном User-Agent).  **Формула Успеха:**  $$Observability = Metrics + Logs + Traces + Correlati

- **Full Article Access:** [L2.SCL.18 Observability (Metrics, Logs, Tracing correlation).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.18 Observability (Metrics, Logs, Tracing correlation).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.18 Observability (Metrics, Logs, Tracing correlation).md`

---

<!-- @id: l2-scl-19-load-testing-tools-k6-gatling-locust -->
## Глобальный ID запуска (генерируется один раз при старте мастера)
<!-- @id: id -->
**Executive Summary:** Раньше (эпоха JMeter) нагрузочное тестирование было "Черным ящиком". * **Input:** Мы бомбардируем сервис 10,000 запросов. * **Output:** Мы получаем график: "Latency выросла до 5 секунд". * **Missing Link:** Мы не знали, *что именно* происходило внутри кода в этот момент. Инженеры гадали: "Это БД? Сеть? Или GC?"

- **Full Article Access:** [L2.SCL.19 Load testing tools (K6, Gatling, Locust).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.19 Load testing tools (K6, Gatling, Locust).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.19 Load testing tools (K6, Gatling, Locust).md`

---

<!-- @id: l2-scl-20-load-balancing-algorithms-service-mesh-s -->
## L2.SCL.20 Load Balancing Algorithms & Service Mesh Sidecars
<!-- @id: l2-scl-20-load-balancing-algorithms-service-mesh-sidecars -->
**Executive Summary:** В сетевом стеке Kubernetes есть фундаментальный компромисс:

- **Full Article Access:** [L2.SCL.20 Load Balancing Algorithms & Service Mesh Sidecars.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.20 Load Balancing Algorithms & Service Mesh Sidecars.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.20 Load Balancing Algorithms & Service Mesh Sidecars.md`

---

<!-- @id: l2-scl-21-capacity-planning-little-s-law-usl -->
## L2.SCL.21 Capacity planning (Little’s Law, USL)
<!-- @id: l2-scl-21-capacity-planning-little-s-law-usl -->
**Executive Summary:** Интуиция подсказывает: *"Если 1 кассир обслуживает 10 покупателей в час, то 10 кассиров обслужат 100".*

- **Full Article Access:** [L2.SCL.21 Capacity planning (Little’s Law, USL).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.21 Capacity planning (Little’s Law, USL).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.21 Capacity planning (Little’s Law, USL).md`

---

<!-- @id: l2-scl-22-future-trends-serverless-edge-wasm -->
## L2.SCL.22 Future trends (Serverless, Edge, Wasm)
<!-- @id: l2-scl-22-future-trends-serverless-edge-wasm -->
**Executive Summary:** В классической облачной модели (даже в Kubernetes) вы арендуете **мощность** (Capacity). * Вы запускаете Pod с Java-приложением. Он потребляет 512MB RAM. * Если трафика нет (ночь), он все равно потребляет 512MB RAM и стоит денег.

- **Full Article Access:** [L2.SCL.22 Future trends (Serverless, Edge, Wasm).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.22 Future trends (Serverless, Edge, Wasm).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.SCL/L2.SCL.22 Future trends (Serverless, Edge, Wasm).md`

---

