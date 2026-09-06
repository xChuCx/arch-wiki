# L2 API Design & Communication
<!-- @id: l2-api-design-communication -->

<!-- @id: l2-api-01-api-idl-schemas-protobuf-vs-avro-vs-thri -->
## L2.API.01 API IDL & Schemas - Protobuf vs Avro vs Thrift
<!-- @id: l2-api-01-api-idl-schemas-protobuf-vs-avro-vs-thrift -->
**Executive Summary:** **TL;DR**: Выбор IDL (Interface Definition Language) — это не вопрос "кто быстрее сериализует". Это вопрос **управления изменениями** на горизонте 5-10 лет. *   **Protobuf** — стандарт для Service-to-Service (gRPC). Он оптимизирован под совместимость тегов. *   **Avro** — стандарт для Data-at-Rest и Event Streaming (Kafka). Он требует доступа к схе

- **Full Article Access:** [L2.API.01 API IDL & Schemas - Protobuf vs Avro vs Thrift.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.01 API IDL & Schemas - Protobuf vs Avro vs Thrift.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.01 API IDL & Schemas - Protobuf vs Avro vs Thrift.md`

---

<!-- @id: l2-api-02-graphql-federation-apollo-federation-sup -->
## @key говорит Роутеру: "Я могу найти User, если ты дашь мне id"
<!-- @id: key-user-id -->
**Executive Summary:** **TL;DR**: **Apollo Federation** превращает ваши разрозненные микросервисы (Subgraphs) в единый **Supergraph**. Главный вызов практика: **Сетевая задержка**. В монолите N+1 — это лишние запросы в БД (0.5ms). В Федерации N+1 — это лишние HTTP-запросы между сервисами (5-50ms). Без правильного использования `_entities` query и Dataloader ваш граф стан

- **Full Article Access:** [L2.API.02 GraphQL Federation - Apollo Federation, Supergraph architecture, N+1 problem mitigation.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.02 GraphQL Federation - Apollo Federation, Supergraph architecture, N+1 problem mitigation.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.02 GraphQL Federation - Apollo Federation, Supergraph architecture, N+1 problem mitigation.md`

---

<!-- @id: l2-api-03-contract-testing-consumer-driven-contrac -->
## L2.API.03 Contract Testing - Consumer-Driven Contracts (Pact), Schema Registry pattern
<!-- @id: l2-api-03-contract-testing-consumer-driven-contracts-pact-schema -->
**Executive Summary:** **TL;DR**: Контрактное тестирование — это **превентивный удар** по интеграционным багам. *   **Consumer-Driven Contracts (Pact)** — это для синхронного мира (REST/gRPC). Оно переворачивает ответственность: Потребитель (Consumer) диктует, какие поля ему нужны, а Поставщик (Provider) в рамках своего CI-пайплайна доказывает, что он выполняет этот конт

- **Full Article Access:** [L2.API.03 Contract Testing - Consumer-Driven Contracts (Pact), Schema Registry pattern.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.03 Contract Testing - Consumer-Driven Contracts (Pact), Schema Registry pattern.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.03 Contract Testing - Consumer-Driven Contracts (Pact), Schema Registry pattern.md`

---

<!-- @id: l2-api-04-idempotency-keys-implementation-deep-div -->
## АНТИПАТТЕРН: Никогда так не делайте в продакшене
<!-- @id: section -->
**Executive Summary:** **TL;DR**: Идемпотентность — это механизм обеспечения **Exactly-Once Semantics** (или, точнее, "эффективно однократного выполнения") в ненадежной сети. Главная сложность не в проверке ключа, а в **атомарности** проверки и бизнес-операции, а также в обработке состояния **"In-Progress"** (когда повтор прилетел, пока первый запрос еще выполняется).

- **Full Article Access:** [L2.API.04 Idempotency Keys Implementation Deep-Dive.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.04 Idempotency Keys Implementation Deep-Dive.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.04 Idempotency Keys Implementation Deep-Dive.md`

---

<!-- @id: l2-api-05-asynchronous-correlation-long-running-sa -->
## L2.API.05 Asynchronous Correlation & Long-Running Sagas
<!-- @id: l2-api-05-asynchronous-correlation-long-running-sagas -->
**Executive Summary:** **TL;DR**: Для асинхронных процессов "найти и продолжить" — это задача **State Machine (Orchestrator)**. *   Не используйте `Trace-ID` (инфраструктурный трейсинг) как `Correlation-ID` (бизнес-сцепку). *   Для эффективного поиска используйте **Reverse Mapping Tables** (когда внешний провайдер не возвращает ваш ID). *   Для надежного "продолжения" ис

- **Full Article Access:** [L2.API.05 Asynchronous Correlation & Long-Running Sagas.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.05 Asynchronous Correlation & Long-Running Sagas.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.05 Asynchronous Correlation & Long-Running Sagas.md`

---

<!-- @id: l2-api-06-rest-api-versioning-strategies-uri-vs-he -->
## L2.API.06 REST API Versioning Strategies - URI vs Header vs Content Negotiation
<!-- @id: l2-api-06-rest-api-versioning-strategies-uri-vs-header-vs-conten -->
**Executive Summary:** **TL;DR**: Версионирование API — это не спор о красоте URL. Это спор между **DX (Developer Experience)** и **Инфраструктурой (Caching/Routing)**. *   **URI Versioning** (`/v1/users`) — это выбор прагматика. Это "не по REST", но это дешево для CDN, понятно разработчику и легко маршрутизируется. *   **Header Versioning** — это выбор корпоративного ар

- **Full Article Access:** [L2.API.06 REST API Versioning Strategies - URI vs Header vs Content Negotiation.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.06 REST API Versioning Strategies - URI vs Header vs Content Negotiation.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.06 REST API Versioning Strategies - URI vs Header vs Content Negotiation.md`

---

<!-- @id: l2-api-07-grpc-versioning-package-evolution-interf -->
## Пример фрагмента Envoy Config (Raw)
<!-- @id: envoy-config-raw -->
**Executive Summary:** В gRPC версионирование — это **архитектурный паттерн**, зашитый в структуру ваших `.proto` файлов. Здесь нет "Query Params" или "Accept Headers". Версия является частью полного имени метода (Fully Qualified Name).

- **Full Article Access:** [L2.API.07 gRPC Versioning - Package Evolution & Interface Adapters.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.07 gRPC Versioning - Package Evolution & Interface Adapters.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.07 gRPC Versioning - Package Evolution & Interface Adapters.md`

---

<!-- @id: l2-api-08-kafka-event-streaming-schema-evolution -->
## КРИТИЧЕСКИ ВАЖНО:
<!-- @id: section-2 -->
**Executive Summary:** В Event Streaming системах данные персистентны (Retention может быть установлен на годы). Вы не можете просто "выключить старую версию API". Сообщение, записанное 3 года назад старой версией Producer, может быть прочитано завтра новым Consumer.

- **Full Article Access:** [L2.API.08 Kafka (Event Streaming) - Schema Evolution.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.08 Kafka (Event Streaming) - Schema Evolution.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.08 Kafka (Event Streaming) - Schema Evolution.md`

---

<!-- @id: l2-api-09-message-queues-versioning-transient-mess -->
## L2.API.09 Message Queues Versioning - Transient Messaging
<!-- @id: l2-api-09-message-queues-versioning-transient-messaging -->
**Executive Summary:** В отличие от Kafka, классические очереди (обычно) спроектированы для **эфемерных** сообщений. Задача: доставить задачу воркеру, выполнить и забыть (Ack).

- **Full Article Access:** [L2.API.09 Message Queues Versioning - Transient Messaging.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.09 Message Queues Versioning - Transient Messaging.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.09 Message Queues Versioning - Transient Messaging.md`

---

<!-- @id: l2-api-10-hypermedia-hateoas-richardson-maturity-m -->
## L2.API.10 Hypermedia, HATEOAS - Richardson Maturity Model, практическая применимость vs сложность
<!-- @id: l2-api-10-hypermedia-hateoas-richardson-maturity-model-vs -->
**Executive Summary:** Мы переходим к самой философской и спорной теме в мире REST API. **HATEOAS** (Hypermedia As The Engine Of Application State) — это "Святой Грааль" REST, описанный в диссертации Роя Филдинга.

- **Full Article Access:** [L2.API.10 Hypermedia, HATEOAS - Richardson Maturity Model, практическая применимость vs сложность.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.10 Hypermedia, HATEOAS - Richardson Maturity Model, практическая применимость vs сложность.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.10 Hypermedia, HATEOAS - Richardson Maturity Model, практическая применимость vs сложность.md`

---

<!-- @id: l2-api-11-asyncapi-specification -->
## L2.API.11 AsyncAPI specification - документирование событийно-ориентированных архитектур
<!-- @id: l2-api-11-asyncapi-specification -->
**Executive Summary:** **TL;DR**: OpenAPI (Swagger) решил проблему документации для REST, сделав HTTP-контракты читаемыми и машиноисполняемыми. **AsyncAPI** делает то же самое для Event-Driven Architecture (Kafka, RabbitMQ, MQTT, WebSockets). Как практик, вы должны внедрять AsyncAPI не для красоты, а для **Governance**: чтобы остановить хаос, когда никто не знает, кто пи

- **Full Article Access:** [L2.API.11 AsyncAPI specification - документирование событийно-ориентированных архитектур.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.API/L2.API.11 AsyncAPI specification - документирование событийно-ориентированных архитектур.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.API/L2.API.11 AsyncAPI specification - документирование событийно-ориентированных архитектур.md`

---

