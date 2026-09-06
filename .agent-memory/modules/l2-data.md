# L2 Data Engineering & Pipelines
<!-- @id: l2-data-engineering-pipelines -->

<!-- @id: l2-data-01-data-modeling-star-schema-vs-snowflake- -->
## L2.DATA.01 Data Modeling - Star Schema vs Snowflake vs Data Vault 2.0
<!-- @id: l2-data-01-data-modeling-star-schema-vs-snowflake-vs-data-vault -->
**Executive Summary:** **TL;DR**: *   **Star Schema (Kimball)**: Стандарт де-факто для **Data Marts (Витрин)** и слоя Presentation. Оптимизирована для чтения и понятна людям (BI-аналитикам). *   **Snowflake Schema**: Нормализованная версия Звезды. Используется редко, для специфичных случаев экономии места или очень сложной иерархии измерений. *   **Data Vault 2.0 (Linste

- **Full Article Access:** [L2.DATA.01 Data Modeling - Star Schema vs Snowflake vs Data Vault 2.0.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.01 Data Modeling - Star Schema vs Snowflake vs Data Vault 2.0.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.01 Data Modeling - Star Schema vs Snowflake vs Data Vault 2.0.md`

---

<!-- @id: l2-data-02-etl-elt-pipelines-orchestration -->
## Пример использования Cosmos
<!-- @id: cosmos -->
**Executive Summary:** **TL;DR**: *   **ELT победил ETL** в облаках. Мы грузим "сырые" данные, а трансформируем их мощностями Warehouse (Snowflake/BigQuery). *   **dbt** — это компилятор, который превращает Jinja+SQL в DDL/DML команды, автоматически строя граф зависимостей (Lineage) через функцию `ref()`. *   **Orchestration (Airflow)** — это не просто запускалка скрипто

- **Full Article Access:** [L2.DATA.02 ETL - ELT Pipelines & Orchestration.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.02 ETL - ELT Pipelines & Orchestration.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.02 ETL - ELT Pipelines & Orchestration.md`

---

<!-- @id: l2-data-03-data-quality-governance-data-contracts- -->
## L2.DATA.03 Data Quality & Governance - Data Contracts, Anomaly detection in data streams
<!-- @id: l2-data-03-data-quality-governance-data-contracts-anomaly-detect -->
**Executive Summary:** **TL;DR**: *   **Data Contracts**: Это API-контракты для данных. Способ перенести ответственность за качество с Потребителя (который страдает) на Производителя (который ломает). *   **Data Quality Testing**: Детерминированные проверки (Null check, Regex), которые блокируют деплой или загрузку. *   **Data Observability & Anomaly Detection**: Вероятн

- **Full Article Access:** [L2.DATA.03 Data Quality & Governance - Data Contracts, Anomaly detection in data streams.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.03 Data Quality & Governance - Data Contracts, Anomaly detection in data streams.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.03 Data Quality & Governance - Data Contracts, Anomaly detection in data streams.md`

---

<!-- @id: l2-data-04-stream-processing-internals-watermarks- -->
## L2.DATA.04 Stream Processing Internals - Watermarks, Windowing types (Tumbling, Sliding, Session), Late data handling
<!-- @id: l2-data-04-stream-processing-internals-watermarks-windowing-type -->
**Executive Summary:** **TL;DR**: Стриминг — это искусство компромисса между **Latency** (как быстро мы дадим ответ) и **Completeness** (насколько точным он будет). Watermark — это механизм управления этим компромиссом, а Windows — это способ дискретизации бесконечного потока в конечное состояние.

- **Full Article Access:** [L2.DATA.04 Stream Processing Internals - Watermarks, Windowing types (Tumbling, Sliding, Session), Late data handling.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.04 Stream Processing Internals - Watermarks, Windowing types (Tumbling, Sliding, Session), Late data handling.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.04 Stream Processing Internals - Watermarks, Windowing types (Tumbling, Sliding, Session), Late data handling.md`

---

<!-- @id: l2-data-05-batch-processing-optimization-spark-shu -->
## N = 20 (солим на 20 бакетов)
<!-- @id: n-20-20 -->
**Executive Summary:** **TL;DR**: *   **Shuffle** — самая дорогая операция (Disk I/O + Network I/O + Serialization). Ваша цель — отложить его, устранить или уменьшить объем данных перед ним. *   **Skew (Перекос)** — главный убийца производительности. Если 99 задач завершились за минуту, а одна висит час — у вас Skew. Решение: AQE или Salting. *   **Broadcast Join** — пре

- **Full Article Access:** [L2.DATA.05 Batch Processing Optimization - Spark Shuffle internals, Skew handling, Broadcast joins.md](file:///i:/TestProj/arch-wiki/4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.05 Batch Processing Optimization - Spark Shuffle internals, Skew handling, Broadcast joins.md)
- **Repository Path:** `4Layers/L2.System Design & Architecture/L2.DATA/L2.DATA.05 Batch Processing Optimization - Spark Shuffle internals, Skew handling, Broadcast joins.md`

---

