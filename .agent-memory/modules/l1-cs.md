# L1 Computer Science & Algorithms
<!-- @id: l1-computer-science-algorithms -->

<!-- @id: l1-cs-01-big-o-upper-lower-bounds -->
## L1.CS.01 Асимптотическая сложность, Big O Θ Ω, upper-lower bounds
<!-- @id: l1-cs-01-big-o-upper-lower-bounds -->
**Executive Summary:** В этом модуле мы перейдем от интуитивного "этот цикл медленный" к строгому математическому аппарату, который позволяет проектировать системы, выдерживающие нагрузки в миллионы RPS. Мы разберем, где теория лжет, и почему кэш процессора иногда важнее количества операций.

- **Full Article Access:** [L1.CS.01 Асимптотическая сложность, Big O Θ Ω, upper-lower bounds.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.01 Асимптотическая сложность, Big O Θ Ω, upper-lower bounds.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.01 Асимптотическая сложность, Big O Θ Ω, upper-lower bounds.md`

---

<!-- @id: l1-cs-02-master-theorem-recursion-tree -->
## L1.CS.02 Анализ рекурсии, Master Theorem, Recursion Tree
<!-- @id: l1-cs-02-master-theorem-recursion-tree -->
**Executive Summary:** Рекурсия в Computer Science — это не просто вызов функции самой себя. Это способ моделирования процессов, где задача разбивается на подзадачи. В распределенных системах "рекурсивный вызов" часто означает **RPC-вызов** на другой узел кластера. Ошибка в оценке сложности здесь стоит не миллисекунды CPU, а часы простоя кластера.

- **Full Article Access:** [L1.CS.02 Анализ рекурсии, Master Theorem, Recursion Tree.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.02 Анализ рекурсии, Master Theorem, Recursion Tree.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.02 Анализ рекурсии, Master Theorem, Recursion Tree.md`

---

<!-- @id: l1-cs-03-dynamic-array-hash-table -->
## L1.CS.03 Амортизированный анализ (Dynamic Array, Hash Table)
<!-- @id: l1-cs-03-dynamic-array-hash-table -->
**Executive Summary:** Амортизированный анализ — это способ честно оценить стоимость владения алгоритмом. В отличие от "среднего случая", где мы надеемся на удачу (распределение данных), здесь мы заключаем **контракт**: система гарантирует среднюю стоимость операции в длинной цепочке, даже если дьявол подсовывает нам худшие входные данные.

- **Full Article Access:** [L1.CS.03 Амортизированный анализ (Dynamic Array, Hash Table).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.03 Амортизированный анализ (Dynamic Array, Hash Table).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.03 Амортизированный анализ (Dynamic Array, Hash Table).md`

---

<!-- @id: l1-cs-04-open-addressing-chaining-resize-strategie -->
## L1.CS.04 Хеш-таблицы - Open Addressing, Chaining, Resize Strategies
<!-- @id: l1-cs-04-open-addressing-chaining-resize-strategies -->
**Executive Summary:** В классической теории алгоритмов (Big O) предполагается, что доступ к любой ячейке памяти стоит $Cost = 1$. В реальности (современная x86_64/ARM64 архитектура) доступ к памяти — это спектр от **1 такта** (L1 Cache) до **300+ тактов** (RAM). Хеш-таблица — это структура, которая по своей природе (random access) тяготеет к худшему концу этого спектра.

- **Full Article Access:** [L1.CS.04 Хеш-таблицы - Open Addressing, Chaining, Resize Strategies.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.04 Хеш-таблицы - Open Addressing, Chaining, Resize Strategies.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.04 Хеш-таблицы - Open Addressing, Chaining, Resize Strategies.md`

---

<!-- @id: l1-cs-05-avl-red-black-b-tree-b-tree -->
## L1.CS.05 Сбалансированные деревья - AVL, Red-Black, B-tree, B+-tree
<!-- @id: l1-cs-05-avl-red-black-b-tree-b-tree -->
**Executive Summary:** Мы рассматриваем деревья как **паттерны доступа к памяти**. Главный враг производительности — **Memory Wall**. *   1 операция сравнения (ALU) = < 1 цикла CPU. *   1 доступ к L3 Cache = ~40-50 циклов. *   1 доступ к RAM (Cache Miss) = ~300 циклов.

- **Full Article Access:** [L1.CS.05 Сбалансированные деревья - AVL, Red-Black, B-tree, B+-tree.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.05 Сбалансированные деревья - AVL, Red-Black, B-tree, B+-tree.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.05 Сбалансированные деревья - AVL, Red-Black, B-tree, B+-tree.md`

---

<!-- @id: l1-cs-06-heap-priority-queue-binomial-fibonacci-he -->
## L1.CS.06 Heap, Priority Queue, Binomial, Fibonacci Heaps
<!-- @id: l1-cs-06-heap-priority-queue-binomial-fibonacci-heaps -->
**Executive Summary:** **Priority Queue (Очередь с приоритетом)** — это *интерфейс* (ADT). Он говорит "что" делать (дай минимум, добавь элемент). **Binary Heap (Двоичная Куча)** — это *реализация*. Она говорит "как" это хранить.

- **Full Article Access:** [L1.CS.06 Heap, Priority Queue, Binomial, Fibonacci Heaps.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.06 Heap, Priority Queue, Binomial, Fibonacci Heaps.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.06 Heap, Priority Queue, Binomial, Fibonacci Heaps.md`

---

<!-- @id: l1-cs-06a-priority-queue-adt-binomial-heaps -->
## L1.CS.06a Priority Queue (ADT), Binomial Heaps
<!-- @id: l1-cs-06a-priority-queue-adt-binomial-heaps -->
**Executive Summary:** **Priority Queue (PQ)** — это **Абстрактный Тип Данных (ADT)**. Это *контракт*, который описывает, **что** система умеет делать (API). **Binary Heap (Куча)** — это **Структура Данных**. Это конкретный способ, **как** реализовать этот контракт в байтах.

- **Full Article Access:** [L1.CS.06a Priority Queue (ADT), Binomial Heaps.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.06a Priority Queue (ADT), Binomial Heaps.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.06a Priority Queue (ADT), Binomial Heaps.md`

---

<!-- @id: l1-cs-06b-bonus-timing-wheels -->
## L1.CS.06b (Bonus) Timing Wheels (Колеса таймеров)
<!-- @id: l1-cs-06b-bonus-timing-wheels -->
**Executive Summary:** Представьте, что вы пишете сетевой шлюз (Gateway), который держит **10 миллионов** открытых WebSocket соединений. Для каждого соединения нужен `Keep-Alive` таймер. Если мы не получили "ping" за 60 секунд — разрываем связь.

- **Full Article Access:** [L1.CS.06b (Bonus) Timing Wheels (Колеса таймеров).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.06b (Bonus) Timing Wheels (Колеса таймеров).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.06b (Bonus) Timing Wheels (Колеса таймеров).md`

---

<!-- @id: l1-cs-07-bfs-dfs-topological-sort-scc -->
## L1.CS.07 Графы - BFS,DFS, Topological Sort, SCC
<!-- @id: l1-cs-07-bfs-dfs-topological-sort-scc -->
**Executive Summary:** В классической теории (Кормен, Седжвик) мы учим, что **Список Смежности (Adjacency List)** — это стандарт для разреженных графов с асимптотикой обхода $O(V+E)$.

- **Full Article Access:** [L1.CS.07 Графы - BFS,DFS, Topological Sort, SCC.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.07 Графы - BFS,DFS, Topological Sort, SCC.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.07 Графы - BFS,DFS, Topological Sort, SCC.md`

---

<!-- @id: l1-cs-08-shortest-path-dijkstra-bellman-ford-a-mul -->
## L1.CS.08 Shortest path - Dijkstra, Bellman‑Ford, A, Multi‑source
<!-- @id: l1-cs-08-shortest-path-dijkstra-bellman-ford-a-multi-source -->
**Executive Summary:** Поиск кратчайшего пути (Shortest Path Problem, SPP) — это фундамент не только карт, но и компьютерных сетей (OSPF), социального анализа (LinkedIn degrees of separation) и арбитража валют.

- **Full Article Access:** [L1.CS.08 Shortest path - Dijkstra, Bellman‑Ford, A, Multi‑source.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.08 Shortest path - Dijkstra, Bellman‑Ford, A, Multi‑source.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.08 Shortest path - Dijkstra, Bellman‑Ford, A, Multi‑source.md`

---

<!-- @id: l1-cs-09-minimum-spanning-tree-prim-kruskal-disjoi -->
## L1.CS.09 Minimum Spanning Tree - Prim-Kruskal, Disjoint-Set
<!-- @id: l1-cs-09-minimum-spanning-tree-prim-kruskal-disjoint-set -->
**Executive Summary:** Представьте, что вы прокладываете оптоволокно между городами (строите MST). У вас есть 10,000 городов. Изначально они изолированы. Вы добавляете кабель между городом А и Б. Теперь они связаны. Потом между В и Г. Потом между Б и В.

- **Full Article Access:** [L1.CS.09 Minimum Spanning Tree - Prim-Kruskal, Disjoint-Set.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.09 Minimum Spanning Tree - Prim-Kruskal, Disjoint-Set.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.09 Minimum Spanning Tree - Prim-Kruskal, Disjoint-Set.md`

---

<!-- @id: l1-cs-10-approximation-algorithms -->
## L1.CS.10 Approximation algorithms и жадные стратегии
<!-- @id: l1-cs-10-approximation-algorithms -->
**Executive Summary:** **TL;DR**: Мир не ограничивается задачами, решаемыми за полиномиальное время ($P$). Жадные стратегии — это попытка решить сложное быстро, принимая локально оптимальные решения. Приближенные (Approximation) алгоритмы — это математическая гарантия того, насколько "плохим" может быть наше быстрое решение по сравнению с недостижимым идеалом.

- **Full Article Access:** [L1.CS.10 Approximation algorithms и жадные стратегии.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.10 Approximation algorithms и жадные стратегии.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.10 Approximation algorithms и жадные стратегии.md`

---

<!-- @id: l1-cs-11-bloom-filter-false-positive-rate-tuning-v -->
## L1.CS.11 Bloom Filter - False Positive Rate, Tuning, Variants
<!-- @id: l1-cs-11-bloom-filter-false-positive-rate-tuning-variants -->
**Executive Summary:** Мы выяснили, что обычный Bloom Filter **не поддерживает удаление**.

- **Full Article Access:** [L1.CS.11 Bloom Filter - False Positive Rate, Tuning, Variants.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.11 Bloom Filter - False Positive Rate, Tuning, Variants.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.11 Bloom Filter - False Positive Rate, Tuning, Variants.md`

---

<!-- @id: l1-cs-12 -->
## L1.CS.12 Вероятностные структуры - От Алгоритмов к Железу
<!-- @id: l1-cs-12 -->
**Executive Summary:** Мы переходим от теории "множеств" к байтам и тактам процессора. Вероятностные структуры данных (Probabilistic Data Structures) — это способ торговать точностью ради скорости и памяти. В сетевом оборудовании и базах данных мы используем их, чтобы *не делать* дорогие I/O операции.

- **Full Article Access:** [L1.CS.12 Вероятностные структуры - От Алгоритмов к Железу.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.12 Вероятностные структуры - От Алгоритмов к Железу.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.12 Вероятностные структуры - От Алгоритмов к Железу.md`

---

<!-- @id: l1-cs-13-hyperloglog-cardinality-estimation-bias-c -->
## L1.CS.13 HyperLogLog, Cardinality Estimation, Bias Correction
<!-- @id: l1-cs-13-hyperloglog-cardinality-estimation-bias-correction -->
**Executive Summary:** **TL;DR**: HyperLogLog (HLL) позволяет подсчитать количество уникальных элементов (Cardinality) в потоке из миллиардов событий, используя всего **1.5 — 12 КБ** памяти, с погрешностью менее 1%. Для Staff Architect это не просто "функция `PFADD` в Redis", а фундаментальный примитив для построения **OLAP-кубов**, систем мониторинга и аналитики реально

- **Full Article Access:** [L1.CS.13 HyperLogLog, Cardinality Estimation, Bias Correction.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.13 HyperLogLog, Cardinality Estimation, Bias Correction.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.13 HyperLogLog, Cardinality Estimation, Bias Correction.md`

---

<!-- @id: l1-cs-14-count-min-sketch-heavy-hitters -->
## L1.CS.14 Count‑Min Sketch, Heavy Hitters
<!-- @id: l1-cs-14-count-min-sketch-heavy-hitters -->
**Executive Summary:** **TL;DR**: Если HyperLogLog отвечает на вопрос "Сколько уникальных?", то **Count-Min Sketch (CMS)** отвечает на вопрос "**Сколько раз встречался элемент X?**" (Frequency Estimation). Для Staff Architect это стандартный инструмент для защиты от DDoS (поиск Heavy Hitters), построения гистограмм в реальном времени и оптимизации кэшей, когда хранить `H

- **Full Article Access:** [L1.CS.14 Count‑Min Sketch, Heavy Hitters.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.14 Count‑Min Sketch, Heavy Hitters.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.14 Count‑Min Sketch, Heavy Hitters.md`

---

<!-- @id: l1-cs-15-streaming-algorithms-reservoir-sampling-q -->
## 1. NAIVE (Algorithm R) - Медленно на больших N
<!-- @id: 1-naive-algorithm-r-n -->
**Executive Summary:** В мире микросервисов среднее время ответа (Average/Median) бесполезно. Оно скрывает проблемы. Нас волнует **99-й и 99.9-й перцентиль** ($P_{99}, P_{99.9}$).

- **Full Article Access:** [L1.CS.15 Streaming algorithms - Reservoir sampling, Quantiles.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.15 Streaming algorithms - Reservoir sampling, Quantiles.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.15 Streaming algorithms - Reservoir sampling, Quantiles.md`

---

<!-- @id: l1-cs-16-memory-allocators-internals-jemalloc-tcma -->
## 1. Архитектура: Где живут метаданные? (Memory Layout Internals)
<!-- @id: 1-memory-layout-internals -->
**Executive Summary:** **TL;DR**: Стандартный системный аллокатор (glibc `malloc`) — это "универсал", который часто проигрывает в специализированных нагрузках. Для высоконагруженных серверов (High-Load C++/Rust/Java services) смена аллокатора на **jemalloc** или **mimalloc** может дать **-30% к RSS** и **+20% к Throughput** просто за счет `LD_PRELOAD`, без изменения един

- **Full Article Access:** [L1.CS.16 Memory Allocators Internals - jemalloc, tcmalloc, mimalloc.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.16 Memory Allocators Internals - jemalloc, tcmalloc, mimalloc.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.16 Memory Allocators Internals - jemalloc, tcmalloc, mimalloc.md`

---

<!-- @id: l1-cs-17-garbage-collection-deep-dive-generational -->
## L1.CS.17 Garbage Collection Deep Dive - Generational hypothesis, Write barriers, Tricolor marking
<!-- @id: l1-cs-17-garbage-collection-deep-dive-generational-hypothesis-wr -->
**Executive Summary:** **TL;DR**: Для джуниора GC — это магия, которая чистит память. Для Staff Engineer GC — это фоновый процесс, который конкурирует с вашим приложением за CPU и пропускную способность памяти (Memory Bandwidth). Вы должны понимать, как **Мутатор** (ваше приложение) взаимодействует с **Коллектором**, почему `Write Barrier` делает каждую запись ссылки чут

- **Full Article Access:** [L1.CS.17 Garbage Collection Deep Dive - Generational hypothesis, Write barriers, Tricolor marking.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CS/L1.CS.17 Garbage Collection Deep Dive - Generational hypothesis, Write barriers, Tricolor marking.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CS/L1.CS.17 Garbage Collection Deep Dive - Generational hypothesis, Write barriers, Tricolor marking.md`

---

