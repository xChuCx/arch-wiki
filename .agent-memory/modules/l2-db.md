# L2 Database Internals & Storage Engines
<!-- @id: l2-database-internals-storage-engines -->

<!-- @id: l2-db-01-acid-vs-base-cap-implications -->
## L2.DB.01 ACID vs BASE, CAP implications
<!-- @id: l2-db-01-acid-vs-base-cap-implications -->
**Executive Summary:** **TL;DR**: *   **ACID** — это набор гарантий транзакционности *внутри одного узла* (или кластера с жесткой координацией). *   **CAP** — это теорема о *невозможности* (Impossibility result) для распределенных систем в условиях сбоя сети. *   **BASE** — это философия проектирования для высокой доступности через ослабление консистентности. *   **PACEL

- **Full Article Access:** [L2.DB.01 ACID vs BASE, CAP implications.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.01 ACID vs BASE, CAP implications.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.01 ACID vs BASE, CAP implications.md`

---

<!-- @id: l2-db-02-isolation-levels-read-uncommitted-seriali -->
## 5. Истинная иерархия уровней изоляции: Poset, а не Лестница
<!-- @id: 5-poset -->
**Executive Summary:** **TL;DR**: Стандарт SQL-92 фундаментально сломан и не описывает реальность современных MVCC-баз. Изоляция — это не линейная лестница, а частично упорядоченное множество (Partial Order). На уровне Scholar мы оперируем терминами **Conflict Serializability**, **View Serializability** и анализируем графы зависимостей (Serialization Graph).

- **Full Article Access:** [L2.DB.02 Isolation levels - Read Uncommitted → Serializable, anomalies.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.02 Isolation levels - Read Uncommitted → Serializable, anomalies.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.02 Isolation levels - Read Uncommitted → Serializable, anomalies.md`

---

<!-- @id: l2-db-03-mvcc-internals -->
## L2.DB.03 MVCC internals
<!-- @id: l2-db-03-mvcc-internals -->
**Executive Summary:** **TL;DR**: Для уровня Senior/Staff понимание MVCC — это не просто знание об уровнях изоляции. Это понимание физики данных на диске. *   **PostgreSQL**: Использует **MGA (Multi-Generation Architecture)**. Версии строк хранятся в основной куче (Heap). Плюсы: быстрый откат. Минусы: Write Amplification, Bloat, необходимость Vacuum. *   **MySQL (InnoDB)

- **Full Article Access:** [L2.DB.03 MVCC internals.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.03 MVCC internals.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.03 MVCC internals.md`

---

<!-- @id: l2-db-04-wal-write-ahead-logging-log-structured-st -->
## L2.DB.04 WAL - write‑ahead logging, log‑structured storage
<!-- @id: l2-db-04-wal-write-ahead-logging-log-structured-storage -->
**Executive Summary:** **TL;DR**: WAL (Write-Ahead Log) — это и есть ваша база данных. Файлы данных (таблицы) — это лишь кэш состояния лога, оптимизированный для чтения. *   **Физика**: WAL превращает Random Write (в файлы данных) в Sequential Write (в лог). Это основа производительности ACID. *   **Надежность**: WAL гарантирует атомарность через механизм LSN и защиту от

- **Full Article Access:** [L2.DB.04 WAL - write‑ahead logging, log‑structured storage.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.04 WAL - write‑ahead logging, log‑structured storage.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.04 WAL - write‑ahead logging, log‑structured storage.md`

---

<!-- @id: l2-db-05-b-tree-storage-engines-innodb-postgres-he -->
## L2.DB.05 B‑tree storage engines (InnoDB, Postgres heap+indexes)
<!-- @id: l2-db-05-b-tree-storage-engines-innodb-postgres-heap-indexes -->
**Executive Summary:** **TL;DR**: На уровне Staff/Expert разница между "Heap" (Postgres) и "Index-Organized" (InnoDB) архитектурами определяет фундаментальную производительность системы на годы вперед. *   **MySQL (InnoDB)**: Таблица — это B+Tree индекс. Данные лежат в листьях.     *   *Win:* Идеально для Range-запросов и лукапов по PK.     *   *Fail:* Случайная вставка 

- **Full Article Access:** [L2.DB.05 B‑tree storage engines (InnoDB, Postgres heap+indexes).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.05 B‑tree storage engines (InnoDB, Postgres heap+indexes).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.05 B‑tree storage engines (InnoDB, Postgres heap+indexes).md`

---

<!-- @id: l2-db-06-lsm-tree-engines-leveldb-rocksdb-cassandr -->
## L2.DB.06 LSM‑tree engines (LevelDB, RocksDB, Cassandra, TiKV)
<!-- @id: l2-db-06-lsm-tree-engines-leveldb-rocksdb-cassandra-tikv -->
**Executive Summary:** **TL;DR**: LSM-деревья — это ответ индустрии на физические ограничения вращающихся дисков и SSD. Они меняют **Random Write** (дорого) на **Sequential Write** (дешево), но переносят стоимость на **CPU** (Compaction) и **Read Latency** (Merge-on-Read). *   **Главный принцип**: Никогда не менять данные на месте. Всегда дописывать новые версии. *   **Г

- **Full Article Access:** [L2.DB.06 LSM‑tree engines (LevelDB, RocksDB, Cassandra, TiKV).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.06 LSM‑tree engines (LevelDB, RocksDB, Cassandra, TiKV).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.06 LSM‑tree engines (LevelDB, RocksDB, Cassandra, TiKV).md`

---

<!-- @id: l2-db-07-columnar-vs-row-oriented-vectorized-execu -->
## L2.DB.07 Columnar vs row‑oriented, vectorized execution, compression
<!-- @id: l2-db-07-columnar-vs-row-oriented-vectorized-execution-compressi -->
**Executive Summary:** **TL;DR**: Выбор между строкой и колонкой — это выбор между **Latnecy** (доставка одной записи) и **Throughput** (сканирование миллиардов). *   **Columnar (DSM)**: Идеально для OLAP. Данные сжаты по типу, CPU использует SIMD (Vectorization) для обработки массивов. Главная проблема — **Tuple Reconstruction** (сборка атрибутов обратно в строку). *   

- **Full Article Access:** [L2.DB.07 Columnar vs row‑oriented, vectorized execution, compression.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.07 Columnar vs row‑oriented, vectorized execution, compression.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.07 Columnar vs row‑oriented, vectorized execution, compression.md`

---

<!-- @id: l2-db-08-query-planning-cost-based-optimizers -->
## Pseudo-code
<!-- @id: pseudo-code -->
**Executive Summary:** **TL;DR**: Оптимизатор (CBO) — это мозг базы данных, решающий математическую задачу **оптимизации стоимости** в условиях неопределенности. *   **Вход:** SQL (декларативное "что"), Статистика (гистограммы, MCV). *   **Задача:** Найти самый дешевый путь выполнения (Plan) из миллиардов возможных вариантов (Join Ordering — NP-Hard задача). *   **Валюта

- **Full Article Access:** [L2.DB.08 Query planning & cost‑based optimizers.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.08 Query planning & cost‑based optimizers.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.08 Query planning & cost‑based optimizers.md`

---

<!-- @id: l2-db-09-distributed-sql-spanner-cockroachdb-yugab -->
## L2.DB.09 Distributed SQL (Spanner, CockroachDB, Yugabyte)
<!-- @id: l2-db-09-distributed-sql-spanner-cockroachdb-yugabyte -->
**Executive Summary:** **TL;DR**: Distributed SQL — это попытка обмануть теорему CAP и дать разработчику интерфейс PostgreSQL, но с масштабируемостью Cassandra. *   **Архитектура**: Это **CP-системы** (Consistent + Partition Tolerant). Доступность (Availability) достигается избыточностью (Raft/Paxos). *   **Секрет**: Ключевая проблема — не репликация, а **Время**. Без си

- **Full Article Access:** [L2.DB.09 Distributed SQL (Spanner, CockroachDB, Yugabyte).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.09 Distributed SQL (Spanner, CockroachDB, Yugabyte).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.09 Distributed SQL (Spanner, CockroachDB, Yugabyte).md`

---

<!-- @id: l2-db-10-nosql-families-key-value-document-wide-co -->
## Часть 3. Wide-Column Stores (Family of BigTable)
<!-- @id: 3-wide-column-stores-family-of-bigtable -->
**Executive Summary:** **TL;DR**: На уровне Expert выбор NoSQL — это не выбор "Mongo или Redis". Это выбор **структуры доступа (Access Pattern)** и **физической модели распределения**. *   **Key-Value**: Фундамент. O(1) доступ. Значение — "черный ящик". Идеально для кэшей и сессий. *   **Document**: "Schema-on-Read". Значение — структурированный объект (JSON/BSON), котор

- **Full Article Access:** [L2.DB.10 NoSQL families - key‑value, document, wide‑column.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.10 NoSQL families - key‑value, document, wide‑column.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.10 NoSQL families - key‑value, document, wide‑column.md`

---

<!-- @id: l2-db-11-graph-dbs-social-graph-tao-neo4j -->
## L2.DB.11 Graph DBs и social graph (TAO, Neo4j)
<!-- @id: l2-db-11-graph-dbs-social-graph-tao-neo4j -->
**Executive Summary:** **TL;DR**: Графовые базы данных решают проблему **"Join Bomb"**. *   **Neo4j (Native Graph)**: Реализует **Index-Free Adjacency**. Связь — это физический указатель на диске/в памяти. Идеально для **глубоких обходов** (Deep Traversal) и сложной аналитики связей. Узкое место — Random I/O. *   **Meta's TAO (Distributed Graph over RDBMS)**: Это не БД, 

- **Full Article Access:** [L2.DB.11 Graph DBs и social graph (TAO, Neo4j).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.11 Graph DBs и social graph (TAO, Neo4j).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.11 Graph DBs и social graph (TAO, Neo4j).md`

---

<!-- @id: l2-db-12-time-series-dbs-prometheus-m3-timescale -->
## Часть 4. TimescaleDB: SQL on Steroids (Hybrid Row/Columnar)
<!-- @id: 4-timescaledb-sql-on-steroids-hybrid-row-columnar -->
**Executive Summary:** **TL;DR**: TSDB — это специализированные движки для данных, где "Время" — это первичный ключ сортировки. *   **Физика**: Оптимизированы под **Append-Only** (вставка всегда в конец) и **Range Scans** (чтение диапазонов). *   **Сжатие**: Используют алгоритмы "Gorilla" (Delta-of-Delta + XOR), сжимая 16 байт (`timestamp` + `value`) до 1.3 бита. Это на 

- **Full Article Access:** [L2.DB.12 Time‑series DBs (Prometheus, M3, Timescale).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.12 Time‑series DBs (Prometheus, M3, Timescale).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.12 Time‑series DBs (Prometheus, M3, Timescale).md`

---

<!-- @id: l2-db-13-newsql-htap-tidb-singlestore-snowflake -->
## L2.DB.13 NewSQL & HTAP - TiDB, SingleStore, Snowflake
<!-- @id: l2-db-13-newsql-htap-tidb-singlestore-snowflake -->
**Executive Summary:** **TL;DR**: Мы наблюдаем смерть парадигмы "ETL". *   **TiDB**: Это **MySQL на стероидах** с архитектурой Google Spanner. Разделяет Row-store (TiKV) и Column-store (TiFlash) через Raft-репликацию. Идеален для **Scale-Out OLTP** с потребностью в аналитике. *   **SingleStore**: Король **Ingestion**. Использует "Universal Storage" (гибрид памяти и диска

- **Full Article Access:** [L2.DB.13 NewSQL & HTAP - TiDB, SingleStore, Snowflake.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.13 NewSQL & HTAP - TiDB, SingleStore, Snowflake.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.13 NewSQL & HTAP - TiDB, SingleStore, Snowflake.md`

---

<!-- @id: l2-db-14-change-data-capture-cdc-debezium-log-base -->
## АНТИ-ПАТТЕРН: Это гарантированно сломается
<!-- @id: section -->
**Executive Summary:** **TL;DR**: **Change Data Capture (CDC)** — это единственный надежный способ превратить базу данных (State) в поток событий (Stream). *   **Polling (Query-based)** — это анти-паттерн. Он убивает базу, пропускает удаления (`DELETE`) и создает задержки. *   **Log-based (Debezium)** — это чтение "Транзакционного Журнала" (WAL/Binlog). Это источник прав

- **Full Article Access:** [L2.DB.14 Change Data Capture (CDC), Debezium, log‑based replication.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.14 Change Data Capture (CDC), Debezium, log‑based replication.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.14 Change Data Capture (CDC), Debezium, log‑based replication.md`

---

<!-- @id: l2-db-15-data-warehouse-vs-data-lake-vs-lakehouse- -->
## L2.DB.15 Data warehouse vs data lake vs lakehouse (Delta, Apache Iceberg)
<!-- @id: l2-db-15-data-warehouse-vs-data-lake-vs-lakehouse-delta-apache-i -->
**Executive Summary:** **TL;DR**: Мы наблюдаем конец эпохи "Разделения". *   **Data Warehouse (DW):** Дорогой, монолитный, быстрый SQL по структурированным данным. *Физика:* Проприетарный формат + SSD + Вычисления рядом с данными. *   **Data Lake (DL):** Дешевая свалка файлов (S3/HDFS). *Физика:* Разделение хранения и вычислений. Отсутствие ACID. "Schema-on-Read". *   **

- **Full Article Access:** [L2.DB.15 Data warehouse vs data lake vs lakehouse (Delta, Apache Iceberg).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.15 Data warehouse vs data lake vs lakehouse (Delta, Apache Iceberg).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.15 Data warehouse vs data lake vs lakehouse (Delta, Apache Iceberg).md`

---

<!-- @id: l2-db-16-oltp-vs-olap-workload-characterization -->
## L2.DB.16 OLTP vs OLAP workload characterization
<!-- @id: l2-db-16-oltp-vs-olap-workload-characterization -->
**Executive Summary:** **TL;DR**: Разница между OLTP и OLAP — это не просто "быстро" и "медленно". Это война между **Random Access** (Случайный доступ) и **Sequential Scan** (Последовательное сканирование). *   **OLTP (On-Line Transaction Processing):** Это "Хирургия". Точечные уколы в базу. Критичны: **IOPS**, **Locking**, **Latency**. Враг: B-Tree depth и Lock Contenti

- **Full Article Access:** [L2.DB.16 OLTP vs OLAP workload characterization.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.16 OLTP vs OLAP workload characterization.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.16 OLTP vs OLAP workload characterization.md`

---

<!-- @id: l2-db-17-secondary-indexes-covering-indexes-index- -->
## L2.DB.17 Secondary indexes, covering indexes, index‑only scans
<!-- @id: l2-db-17-secondary-indexes-covering-indexes-index-only-scans -->
**Executive Summary:** **TL;DR**: Индекс — это не магия ускорения, это **технический долг**. *   **Secondary Index** — это де-факто дублирование данных. Это обещание базе данных поддерживать копию подмножества данных в отсортированном виде. *   **The Cost:** Чтение через вторичный индекс — это **Random I/O**. Если селективность низкая (> 30% строк), индекс вредит. *   **

- **Full Article Access:** [L2.DB.17 Secondary indexes, covering indexes, index‑only scans.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.17 Secondary indexes, covering indexes, index‑only scans.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.17 Secondary indexes, covering indexes, index‑only scans.md`

---

<!-- @id: l2-db-18-sharding-vs-partitioning-db-vs-app-level -->
## L2.DB.18 Sharding vs partitioning (DB‑уровень vs app‑level)
<!-- @id: l2-db-18-sharding-vs-partitioning-db-vs-app-level -->
**Executive Summary:** **TL;DR**: *   **Partitioning** — это техника **управляемости** (Manageability) внутри одного инстанса. Она помогает удалять старые данные за $O(1)$ и ускоряет запросы через Pruning. Она **не** дает масштабирования записи (Write Scale). *   **Sharding** — это техника **масштабирования** (Scalability) через распределение данных по разным серверам. Э

- **Full Article Access:** [L2.DB.18 Sharding vs partitioning (DB‑уровень vs app‑level).md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.18 Sharding vs partitioning (DB‑уровень vs app‑level).md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.18 Sharding vs partitioning (DB‑уровень vs app‑level).md`

---

<!-- @id: l2-db-19-multi-tenant-pooled-vs-siloed-vs-hybrid -->
## L2.DB.19 Multi‑tenant схемы - pooled vs siloed vs hybrid
<!-- @id: l2-db-19-multi-tenant-pooled-vs-siloed-vs-hybrid -->
**Executive Summary:** **TL;DR**: Multi-tenancy — это уравнение экономики против физики. *   **Siloed (Database-per-tenant):** Максимальная изоляция, нулевой "шумных соседей", но адский операционный оверхед. Физический предел — память и коннекты. *   **Bridge (Schema-per-tenant):** "Золотая середина" для Postgres, которая становится ловушкой при масштабе > 5,000 тенантов

- **Full Article Access:** [L2.DB.19 Multi‑tenant схемы - pooled vs siloed vs hybrid.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DB/L2.DB.19 Multi‑tenant схемы - pooled vs siloed vs hybrid.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DB/L2.DB.19 Multi‑tenant схемы - pooled vs siloed vs hybrid.md`

---

