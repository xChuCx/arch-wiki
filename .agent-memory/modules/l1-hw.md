# L1 Hardware & Storage Physics
<!-- @id: l1-hardware-storage-physics -->

<!-- @id: l1-hw-01-erasure-coding-reed-solomon-lrc-local-rec -->
## L1.HW.01 Масштабирование надежности: Erasure Coding, Reed-Solomon и LRC
<!-- @id: l1-hw-01-erasure-coding-reed-solomon-lrc -->
**Executive Summary:** На масштабах хранения от сотен терабайт до петабайт традиционная репликация данных ($3\times Replication$) превращается в экономическое самоубийство. Построение современных гипермасштабируемых систем хранения (Ceph, MinIO, HDFS, Azure Blob) базируется на семействе алгоритмов защиты от стирания — **Erasure Coding (EC)**. Переход от "тупого" копирования к алгебраическим уравнениям переносит узкое го

- **Full Article Access:** [L1.HW.01 Erasure Coding - Reed-Solomon, LRC (Local Reconstruction Codes), Trade-offs.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.HW/L1.HW.01 Erasure Coding - Reed-Solomon, LRC (Local Reconstruction Codes), Trade-offs.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.HW/L1.HW.01 Erasure Coding - Reed-Solomon, LRC (Local Reconstruction Codes), Trade-offs.md`

---

<!-- @id: l1-hw-02-ssd-internals-pages-blocks-wear-leveling- -->
## L1.HW.02 SSD Internals: Инженерия кремния и смерть от Write Amplification
<!-- @id: l1-hw-02-ssd-internals-write-amplification -->
**Executive Summary:** Многие программисты до сих пор относятся к SSD как к "очень быстрому магнитному диску". Это фундаментальная ошибка мышления, приводящая к фатальным архитектурным решениям. Современный Enterprise NVMe SSD — это высоконагруженная автономная Распределенная Система. На борту этой системы трудится собственный многоядерный ARM-процессор ($\sim 1 \ GHz$), развернуты гигабайты собственной DRAM памяти, и 2

- **Full Article Access:** [L1.HW.02 SSD Internals - Pages, Blocks, Wear Leveling, Write Amplification, GC внутри диска.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.HW/L1.HW.02 SSD Internals - Pages, Blocks, Wear Leveling, Write Amplification, GC внутри диска.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.HW/L1.HW.02 SSD Internals - Pages, Blocks, Wear Leveling, Write Amplification, GC внутри диска.md`

---

<!-- @id: l1-hw-03-cpu-caches-l1-l2-l3-latencies-cache-lines -->
## L1.HW.03 Архитектура CPU Памяти: Кэши, Coherency (MESI), False Sharing и NUMA
<!-- @id: l1-hw-03-cpu-coherency-mesi-false-sharing-numa -->
**Executive Summary:** Плоской оперативной памяти не существует. Скорость света и ограничения кремния превратили современный CPU в сложнейшую многоэтажную машину по предсказанию будущего. Инженерия High-Load (Разработка KV-моторов, HFT-ботов на С++, Inferencing-движков LLM) на 90% сводится к физическому управлению локальностью данных. Ваша алгоритмическая сложность $O(\log N)$ не имеет никакого смысла, если каждый шаг п

- **Full Article Access:** [L1.HW.03 CPU Caches - L1-L2-L3 latencies, Cache lines, False sharing, NUMA topology impact.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.HW/L1.HW.03 CPU Caches - L1-L2-L3 latencies, Cache lines, False sharing, NUMA topology impact.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.HW/L1.HW.03 CPU Caches - L1-L2-L3 latencies, Cache lines, False sharing, NUMA topology impact.md`

---

<!-- @id: l1-hw-04-gpu-architecture-extreme-expansion -->
## L1.HW.04 Ультимативная Архитектура GPU: От Физики Кремния до Low-Level CUDA и Triton
<!-- @id: l1-hw-04-gpu-low-level-cuda-triton -->
**Executive Summary:** Эта лекция — самый глубокий разбор архитектуры видеокарт Nvidia в курсе. Она разделена на две части: **Часть I (Главы 1-6):** Макро-архитектура — философия Throughput, иерархия SM, Warps, Tensor Cores, HBM/NVLink, Roofline Model. **Часть II (Главы 7-16):** Низкоуровневое программирование — CUDA C++ с полными примерами кода, трассировка PTX/SASS ассемблера, механика Occupancy и Register Pressure, C

- **Full Article Access:** [L1.HW.04 GPU Architecture Extreme Expansion.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.HW/L1.HW.04 GPU Architecture Extreme Expansion.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.HW/L1.HW.04 GPU Architecture Extreme Expansion.md`

---

<!-- @id: l1-hw-05-edge-ai-and-autonomous-architecture -->
## L1.HW.05 Архитектура Edge AI и Автопилотов: ASICs, Sensor Fusion, NPU и SWaP
<!-- @id: l1-hw-05-edge-ai-asics-sensor-fusion-npu-swap -->
**Executive Summary:** Датацентры могут позволить себе роскошь бесконечного электричества и гигантских градирен охлаждения. Обучение LLM на кластере из $10,000 \ GPU H100$ потребляет Мегаватты. Но когда вы переносите Инференс Нейросети в беспилотный автомобиль, дрон или робособаку, правила физики кардинально меняются. Рождается треугольник ограничений **SWaP (Size, Weight, and Power — Размер, Вес и Энергопотребление)**.

- **Full Article Access:** [L1.HW.05 Edge AI and Autonomous Architecture.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.HW/L1.HW.05 Edge AI and Autonomous Architecture.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.HW/L1.HW.05 Edge AI and Autonomous Architecture.md`

---

<!-- @id: l1-hw-06-modern-memory-architecture-extreme-expans -->
## L1.HW.06 Архитектура Современной Памяти (Deep Dive): От Физического Кремния до CXL Фабрик
<!-- @id: l1-hw-06-deep-dive-cxl -->
**Executive Summary:** Рядовой программист уверен, что оперативная память ($RAM$) обладает константным временем доступа $O(1)$. Это самая опасная и дорогая иллюзия в $Computer \ Science$. Настоящая оперативная память глубоко асимметрична. Она представляет собой трехмерный лабиринт из Каналов (Channels), Ранков (Ranks), Банков (Banks), Строк (Rows) и Столбцов (Columns). Понимание того, как контроллер памяти (IMC) физичес

- **Full Article Access:** [L1.HW.06 Modern Memory Architecture Extreme Expansion.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.HW/L1.HW.06 Modern Memory Architecture Extreme Expansion.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.HW/L1.HW.06 Modern Memory Architecture Extreme Expansion.md`

---

