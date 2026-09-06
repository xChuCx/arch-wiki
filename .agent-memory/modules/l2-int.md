# L2 Messaging & Enterprise Integration
<!-- @id: l2-messaging-enterprise-integration -->

<!-- @id: l2-int-01-enterprise-integration-patterns-eip-mess -->
## L2.INT.01 Enterprise Integration Patterns (EIP) - Message Broker patterns, Dead Letter Queues, Scatter-Gather, Wire Tap
<!-- @id: l2-int-01-enterprise-integration-patterns-eip-message-broker-pat -->
**Executive Summary:** **TL;DR**: EIP — это язык, на котором разговаривают распределенные системы. Это набор паттернов для решения проблем асинхронности, надежности и связности. Ключевой навык эксперта — не просто внедрить очередь, а спроектировать **стратегию обработки сбоев (Failure Handling Strategy)** и **семантику доставки**.

- **Full Article Access:** [L2.INT.01 Enterprise Integration Patterns (EIP) - Message Broker patterns, Dead Letter Queues, Scatter-Gather, Wire Tap.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.INT/L2.INT.01 Enterprise Integration Patterns (EIP) - Message Broker patterns, Dead Letter Queues, Scatter-Gather, Wire Tap.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.INT/L2.INT.01 Enterprise Integration Patterns (EIP) - Message Broker patterns, Dead Letter Queues, Scatter-Gather, Wire Tap.md`

---

<!-- @id: l2-int-02-change-data-capture-cdc-at-scale-debeziu -->
## L2.INT.02 Change Data Capture (CDC) at scale - Debezium pitfalls, transactional outbox pattern implementation details
<!-- @id: l2-int-02-change-data-capture-cdc-at-scale-debezium-pitfalls-tra -->
**Executive Summary:** **TL;DR**: CDC вычитывает журнал транзакций БД (WAL/Binlog) и стримит каждое изменение (`INSERT`, `UPDATE`, `DELETE`) как событие. Самый надежный паттерн интеграции — **Transactional Outbox** через CDC (Log-based), так как он гарантирует атомарность изменения состояния и отправки события. Главный риск — влияние на Master-БД (WAL retention).

- **Full Article Access:** [L2.INT.02 Change Data Capture (CDC) at scale - Debezium pitfalls, transactional outbox pattern implementation details.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.INT/L2.INT.02 Change Data Capture (CDC) at scale - Debezium pitfalls, transactional outbox pattern implementation details.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.INT/L2.INT.02 Change Data Capture (CDC) at scale - Debezium pitfalls, transactional outbox pattern implementation details.md`

---

