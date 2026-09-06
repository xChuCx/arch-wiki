# L1 Distributed Systems Theory
<!-- @id: l1-distributed-systems-theory -->

<!-- @id: l1-dst-01-crash-stop-crash-recovery-byzantine -->
## L1.DST.01: Модель отказов - crash-stop, crash-recovery, Byzantine
<!-- @id: l1-dst-01-crash-stop-crash-recovery-byzantine -->
**Executive Summary:** Выбор математической модели отказов в архитектуре — это осознанный выбор того, от чего ваша система **не** будет защищаться. *   **Crash-Stop (Fail-Stop):** Утопичная модель для теоретиков и базовая модель для неизменяемой облачной инфраструктуры (Stateless pods в Kubernetes). *   **Crash-Recovery:** Жесткая реальность для любых Stateful систем (Database, Message Queues, Consensus). Главное здесь 

**Tags:** distributed-systems, failure-models, crash-stop, crash-recovery, byzantine, architecture

- **Full Article Access:** [L1.DST.01 Модель отказов - crash-stop, crash-recovery, Byzantine.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.01 Модель отказов - crash-stop, crash-recovery, Byzantine.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.01 Модель отказов - crash-stop, crash-recovery, Byzantine.md`

---

<!-- @id: l1-dst-02-cap-theorem -->
## L1.DST.02: CAP theorem, формулировка и ограничения интерпретации
<!-- @id: l1-dst-02-cap-theorem -->
**Executive Summary:** На уровне Эксперта вы должны навсегда перестать повторять маркетинговую мантру джуниоров «выбери два из трех». Это грубое и опасное упрощение. Строгая математическая теорема (Gilbert & Lynch) гласит: **«В асинхронной сети с возможностью потери сообщений невозможно одновременно гарантировать Линеаризуемость (Linearizability) и Абсолютную Доступность (Availability)»**. Выбор архитектора при проектир

**Tags:** distributed-systems, cap-theorem, pacelc, spanner, consistency, architecture

- **Full Article Access:** [L1.DST.02 CAP theorem, формулировка и ограничения интерпретации.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.02 CAP theorem, формулировка и ограничения интерпретации.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.02 CAP theorem, формулировка и ограничения интерпретации.md`

---

<!-- @id: l1-dst-03-pacelc-latency-vs-consistency-tradeoffs -->
## L1.DST.03: PACELC - latency vs consistency tradeoffs
<!-- @id: l1-dst-03-pacelc-latency-vs-consistency-tradeoffs -->
**Executive Summary:** **CAP-теорема** — это исторический, и во многом уже маркетинговый лозунг 2000-х годов, который описывает жесткое поведение распределенной системы только и исключительно во время сетевой аварии (Partition). Но современные системы работают в штатном режиме (без аварий) 99.99% времени. **PACELC** — это реальный, повседневный математический инструмент Staff-архитектора для принятия тяжелых решений в м

**Tags:** distributed-systems, pacelc, cap-theorem, latency, consistency, architecture

- **Full Article Access:** [L1.DST.03 PACELC - latency vs consistency tradeoffs.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.03 PACELC - latency vs consistency tradeoffs.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.03 PACELC - latency vs consistency tradeoffs.md`

---

<!-- @id: l1-dst-04-eventual-causal-strong-consistency -->
## L1.DST.04: Eventual, causal, strong consistency
<!-- @id: l1-dst-04-eventual-causal-strong-consistency -->
**Executive Summary:** На архитектурном уровне Expert вы обязаны раз и навсегда перестать думать о концепции "согласованности" (Consistency) как о примитивном бинарном переключателе "включено/выключено". Консистентность — это **богатый спектр (иерархия) математических моделей**, каждая из которых строго определяет допустимый порядок видимости системных событий. *   **Strong (Строгая / Linearizability):** Распределенная 

**Tags:** distributed-systems, consistency-models, linearizability, eventual-consistency, causal-consistency, architecture

- **Full Article Access:** [L1.DST.04 Eventual, causal, strong consistency.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.04 Eventual, causal, strong consistency.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.04 Eventual, causal, strong consistency.md`

---

<!-- @id: l1-dst-05-vector-clocks-lamport-clocks-partial-ord -->
## L1.DST.05 Vector clocks, Lamport clocks, partial order
<!-- @id: l1-dst-05-vector-clocks-lamport-clocks-partial-order -->
**Executive Summary:** **TL;DR**: Физическое время в распределенных системах — это иллюзия (NTP имеет дрифт). Если ваша архитектура полагается на `timestamp` для упорядочивания событий, вы обречены на потерю данных при конфликтах (Last Write Wins). *   **Часы Лампорта** дают вам **полный порядок** (Total Order), но не говорят о причинах (Causality). *   **Векторные часы*

- **Full Article Access:** [L1.DST.05 Vector clocks, Lamport clocks, partial order.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.05 Vector clocks, Lamport clocks, partial order.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.05 Vector clocks, Lamport clocks, partial order.md`

---

<!-- @id: l1-dst-06-consensus-problem-flp-impossibility -->
## L1.DST.06: Consensus Problem, FLP Impossibility
<!-- @id: l1-dst-06-consensus-problem-flp-impossibility -->
**Executive Summary:** **Проблема консенсуса** — это бьющееся ядро любых отказоустойчивых распределенных систем. Легендарная теорема **FLP** (Fischer, Lynch, Paterson, 1985) математически доказывает, что в полностью асинхронной распределенной системе (где нет гарантий времени доставки пакетов) даже при наличии всего **одного** возможного сбоя (crash failure), ни один детерминированный алгоритм консенсуса не может 100% г

**Tags:** distributed-systems, consensus, flp-impossibility, failure-detectors, architecture

- **Full Article Access:** [L1.DST.06 Consensus Problem, FLP Impossibility.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.06 Consensus Problem, FLP Impossibility.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.06 Consensus Problem, FLP Impossibility.md`

---

<!-- @id: l1-dst-07-paxos-family-single-decree-multi-paxos -->
## L1.DST.07 Paxos family - single‑decree, multi‑Paxos
<!-- @id: l1-dst-07-paxos-family-single-decree-multi-paxos -->
**Executive Summary:** **Paxos** — это семейство фундаментальных протоколов для решения задачи консенсуса в ненадежной асинхронной сети.  - **Single-Decree Paxos (Базовый Паксос)** позволяет надежно выбрать ровно одно значение. - **Multi-Paxos** позволяет выбрать последовательность значений (Replicated Log), что делает его применимым для систем реального мира.  Главная идея: безопасность (Safety) гарантируется математич

- **Full Article Access:** [L1.DST.07 Paxos family - single‑decree, multi‑Paxos.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.07 Paxos family - single‑decree, multi‑Paxos.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.07 Paxos family - single‑decree, multi‑Paxos.md`

---

<!-- @id: l1-dst-08-viewstamped-replication-vrr -->
## L1.DST.08 Viewstamped Replication (VRR)
<!-- @id: l1-dst-08-viewstamped-replication-vrr -->
**Executive Summary:** **VRR** — это распределенный алгоритм консенсуса, применяемый для репликации состояния конечных автоматов в асинхронной сети. Его ключевая особенность — жесткая архитектура Primary-Backup и использование единого монолитного лога операций, в отличие от разрозненных слотов в Paxos.

- **Full Article Access:** [L1.DST.08 Viewstamped Replication (VRR).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.08 Viewstamped Replication (VRR).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.08 Viewstamped Replication (VRR).md`

---

<!-- @id: l1-dst-09-raft-leader-election-log-replication-mem -->
## L1.DST.09 Raft: Выборы лидера, Репликация лога и Смена конфигурации
<!-- @id: l1-dst-09-raft -->
**Executive Summary:** **Raft** — это алгоритм консенсуса, созданный Диего Онгаро и Джоном Оустерхаутом (Stanford University) с конкретной и осознанной целью: **быть понятным** (Understandability). В отличие от семейства Paxos, которое выводит консенсус из абстрактных математических свойств асинхронной системы (и часто требует десятилетий для создания корректной production-ready реализации), Raft декомпозирует сложную з

- **Full Article Access:** [L1.DST.09 Raft - leader election, log replication, membership change.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.09 Raft - leader election, log replication, membership change.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.09 Raft - leader election, log replication, membership change.md`

---

<!-- @id: l1-dst-10-zab-zookeeper-atomic-broadcast -->
## L1.DST.10 Zab: ZooKeeper Atomic Broadcast
<!-- @id: l1-dst-10-zab-zookeeper-atomic-broadcast -->
**Executive Summary:** **Zab (ZooKeeper Atomic Broadcast)** — это специализированный высокопроизводительный протокол, созданный инженерами Yahoo! (в частности, Флавио Жункейрой и Бенджамином Ридом) эксклюзивно для Apache ZooKeeper. В то время как академический мир сходил с ума по Paxos (алгоритм консенсуса по распределению *одного абстрактного значения*), а Raft еще не был изобретен, команде ZooKeeper нужна была практич

- **Full Article Access:** [L1.DST.10 Zab - Zookeeper atomic broadcast.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.10 Zab - Zookeeper atomic broadcast.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.10 Zab - Zookeeper atomic broadcast.md`

---

<!-- @id: l1-dst-11-byzantine-generals-problem-bft-pbft -->
## L1.DST.11 Проблема Византийских Генералов и BFT
<!-- @id: l1-dst-11-bft -->
**Executive Summary:** Мы покидаем уютный мир "честных, но смертных" процессов (Crash Faults, как в Raft или Paxos) и входим в суровую реальность "злонамеренных предателей" (Byzantine Faults). Проблема Византийских Генералов решает фундаментальную задачу консенсуса в условиях, когда компоненты системы могут не просто отказывать (падать), но и активно лгать, вступать в сговор, посылать разные сообщения разным участникам 

- **Full Article Access:** [L1.DST.11 Byzantine Generals problem и BFT (PBFT).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.11 Byzantine Generals problem и BFT (PBFT).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.11 Byzantine Generals problem и BFT (PBFT).md`

---

<!-- @id: l1-dst-12-gossip-anti-entropy-swim -->
## L1.DST.12 Gossip Protocols, Anti-Entropy и SWIM
<!-- @id: l1-dst-12-gossip-protocols-anti-entropy-swim -->
**Executive Summary:** В распределенных системах, состоящих из малого числа узлов (3-7), мы используем консенсусные реестры с сильной согласованностью (ZooKeeper/etcd/Raft) для хранения метаданных кластера. Но что делать, если ваша система спроектирована на масштабирование до 1,000 или 10,000 узлов (как Cassandra, Riak, Amazon Dynamo или Service Mesh Envoy)? Вы **математически не можете** использовать Zookeeper для отсл

- **Full Article Access:** [L1.DST.12 Gossip, Anti-entropy, SWIM.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.12 Gossip, Anti-entropy, SWIM.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.12 Gossip, Anti-entropy, SWIM.md`

---

<!-- @id: l1-dst-13-crdts-g-counter-or-set-lww-register -->
## L1.DST.13 CRDTs: G-Counter, LWW-Register, OR-Set
<!-- @id: l1-dst-13-crdts-g-counter-lww-register-or-set -->
**Executive Summary:** **CRDT (Conflict-free Replicated Data Types)** — это единственный математически доказуемый способ строить по-настоящему децентрализованные Active-Active (Multi-Master) системы хранения данных и Offline-First приложения без центрального спасителя (координатора) и без ручного разруливания конфликтов слияния (Merge Conflicts). В отличие от алгоритмов консенсуса вроде Paxos/Raft (которые запрещают пар

- **Full Article Access:** [L1.DST.13 CRDTs - G-Counter, OR-Set, LWW-Register.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.13 CRDTs - G-Counter, OR-Set, LWW-Register.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.13 CRDTs - G-Counter, OR-Set, LWW-Register.md`

---

<!-- @id: l1-dst-14-2pc-3pc-distributed-commit-failure-scena -->
## L1.DST.14 Распределенный коммит: 2PC, 3PC, Failure Scenarios и Эвристики
<!-- @id: l1-dst-14-2pc-3pc-failure-scenarios -->
**Executive Summary:** *   **2PC (Two-Phase Commit)** — это бескомпромиссный стандарт Enterprise-индустрии (XA transactions, JTA, PostgreSQL FDW, Oracle DBLINK), несмотря на то, что это алгоритм **математически блокирующий (blocking protocol)**. Если Координатор транзакции аппаратно умирает в самую неудачную миллисекунду, ваша система хранения данных встает колом, блокируя таблицы для всех остальных клиентов (Denial of 

- **Full Article Access:** [L1.DST.14 2PC,3PC, distributed commit, failure scenarios.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.14 2PC,3PC, distributed commit, failure scenarios.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.14 2PC,3PC, distributed commit, failure scenarios.md`

---

<!-- @id: l1-dst-15-replication-primary-backup-chain-quorum -->
## L1.DST.15 Архитектура Репликации: Primary-Backup, Chain, Quorum
<!-- @id: l1-dst-15-primary-backup-chain-quorum -->
**Executive Summary:** Репликация в Distributed Systems — это далеко не просто `rsync` или "копирование байтов" с диска на диск. Это фундаментальный архитектурный выбор (Trade-off) между **Latency (Задержкой)**, **Consistency (Согласованностью)** и **Durability (Надежностью)**. *   **Primary-Backup (Leader Strategy):** Де-факто индустриальный стандарт для систем, требующих линеаризуемости (PostgreSQL, MySQL). Работает п

- **Full Article Access:** [L1.DST.15 Replication - primary‑backup, chain, quorum.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.15 Replication - primary‑backup, chain, quorum.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.15 Replication - primary‑backup, chain, quorum.md`

---

<!-- @id: l1-dst-16-quorum-systems-majority-rw-quorums-weigh -->
## L1.DST.16 Системы Кворумов: Математика Топологий, R/W кворумы и Веса
<!-- @id: l1-dst-16-r-w -->
**Executive Summary:** Понятие "Кворум" в распределенных вычислениях (Distributed Systems) — это катастрофически неправильно понимаемый термин. Большинство разработчиков считает, что это просто тупое "голосование большинства серверов" ($N/2+1$). На самом деле Кворум — это строгий математический инструмент управления **вероятностью геометрического пересечения множеств**. *   **Simple Majority ($2f+1$)** — Жесткий фундаме

- **Full Article Access:** [L1.DST.16 Quorum systems - majority, rw quorums, weighted.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.16 Quorum systems - majority, rw quorums, weighted.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.16 Quorum systems - majority, rw quorums, weighted.md`

---

<!-- @id: l1-dst-17-partitioning-schemes-range-hash-consiste -->
## L1.DST.17 Архитектура Партиционирования: Range, Hash, Consistent Ring & Data Skew
<!-- @id: l1-dst-17-range-hash-consistent-ring-data-skew -->
**Executive Summary:** Выбор схемы физического партиционирования (Partitioning/Sharding) — это абсолютно самое важное, необратимое и дорогое "One-Way Door" решение при проектировании распределенной СУБД. Вы почти никогда не сможете изменить эту топологию "на лету" без даунтайма или сложнейших многомесячных миграционных скриптов. *   **Range Partitioning (Диапазоны):** Сохраняет лексикографический порядок ключей (Идеальн

- **Full Article Access:** [L1.DST.17 Partitioning schemes - range, hash, consistent hashing.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.17 Partitioning schemes - range, hash, consistent hashing.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.17 Partitioning schemes - range, hash, consistent hashing.md`

---

<!-- @id: l1-dst-18-leaderless-protocols-dynamo-style-riak -->
## L1.DST.18 Leaderless Архитектура (Dynamo-Style): Доступность любой ценой, Конфликты и VNodes
<!-- @id: l1-dst-18-leaderless-dynamo-style-vnodes -->
**Executive Summary:** Классические протоколы (Raft / Paxos) строят `CP-системы`, опираясь на жесткого Лидера. Если Лидер падает, кластер парализован на секунды (Downtime). Leaderless архитектура (Dynamo-style) — это радикальный выбор в пользу **High Availability** и **Low Latency** записи ценой экспоненциального усложнения разрешения конфликтов. В отличие от CP-систем, здесь нет единого лидера, отказ которого останавли

- **Full Article Access:** [L1.DST.18 Leaderless protocols (Dynamo‑style, Riak).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.18 Leaderless protocols (Dynamo‑style, Riak).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.18 Leaderless protocols (Dynamo‑style, Riak).md`

---

<!-- @id: l1-dst-19-snapshotting-log-compaction-replicated-s -->
## L1.DST.19 Snapshotting и Log Compaction: Жизненный цикл State Machine
<!-- @id: l1-dst-19-snapshotting-log-compaction-state-machine -->
**Executive Summary:** Без использования математически корректного *Snapshotting* и *Log Compaction* абсолютно любой распределенный лог консенсуса (будь то Raft, Paxos или Zookeeper Zab) бесконечно и монотонно растет, пока физический диск (Storage) не переполнится с ошибкой `ENOSPC`, а время восстановления узла после перезагрузки (Recovery Time Objective - RTO) не устремится к бесконечности. Для инженера уровня Staff су

- **Full Article Access:** [L1.DST.19 Snapshotting и log compaction в replicated state machine.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.19 Snapshotting и log compaction в replicated state machine.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.19 Snapshotting и log compaction в replicated state machine.md`

---

<!-- @id: l1-dst-20-formal-verification-of-distributed-syste -->
## L1.DST.20 Формальная Верификация Распределенных Систем (TLA+)
<!-- @id: l1-dst-20-tla -->
**Executive Summary:** Классическое индустриальное Тестирование (Unit, Integration, E2E) проверяет, что ваш код делает то, что вы ожидаете, исключительно на *некоторых локальных счастливых путях* исполнения. **Формальная верификация (TLA+)** же математически доказывает, что ваш фундаментальный архитектурный дизайн на 100% корректен с точки зрения Логики на абсолютно *всех теоретически возможных путях* исполнения в Мульт

- **Full Article Access:** [L1.DST.20 Formal verification of distributed systems (TLA+).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.20 Formal verification of distributed systems (TLA+).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.20 Formal verification of distributed systems (TLA+).md`

---

<!-- @id: l1-dst-21-deterministic-simulation-testing-foundat -->
## L1.DST.21 Детерминированное Симуляционное Тестирование (Стиль FoundationDB)
<!-- @id: l1-dst-21-foundationdb -->
**Executive Summary:** Обычные Unit-тесты и мучительные E2E-тесты фундаментально бесполезны для системного поиска редчайших гонок (Race Conditions) в ядрах распределенных систем. Настоящий, хардкорный **Deterministic Simulation Testing (DST)** — это тоталитарная архитектурная парадигма программирования, при которой абсолютно вся сложная распределенная система (Кластер, Сеть TCP, NVMe Диски, Кварцевое Время) синтетически

- **Full Article Access:** [L1.DST.21 Deterministic Simulation Testing (FoundationDB style).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.21 Deterministic Simulation Testing (FoundationDB style).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.21 Deterministic Simulation Testing (FoundationDB style).md`

---

<!-- @id: l1-dst-22-time-synchronization-ntp-ptp-truetime-hl -->
## L1.DST.22 Время и Синхронизация: NTP, PTP, TrueTime и HLC
<!-- @id: l1-dst-22-ntp-ptp-truetime-hlc -->
**Executive Summary:** Главный урок распределенных систем: **Инженер, верящий вызову `time.Now()` на сервере — мертвый инженер**. Время в дата-центрах — это не монотонная физическая константа вселенной, а грязная, постоянно дрейфующая, непредсказуемая абстракция, отягощенная температурными перепадами кварца, асимметрией маршрутизации BGP и невидимыми паузами гипервизоров AWS.  *   **NTP (Network)** обеспечивает приемлем

- **Full Article Access:** [L1.DST.22 Time Synchronization (NTP, PTP, TrueTime, HLC).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.DST/L1.DST.22 Time Synchronization (NTP, PTP, TrueTime, HLC).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.DST/L1.DST.22 Time Synchronization (NTP, PTP, TrueTime, HLC).md`

---

