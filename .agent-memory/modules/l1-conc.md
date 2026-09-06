# L1 Concurrency & Multithreading
<!-- @id: l1-concurrency-multithreading -->

<!-- @id: l1-conc-01-threads-vs-processes-context-switch-cos -->
## L1.CONC.01: Threads vs processes, context switch cost
<!-- @id: l1-conc-01-threads-vs-processes-context-switch-cost -->
**Executive Summary:** Для уровня Practitioner разница между потоком и процессом — это не просто «общая память». Это глубокий архитектурный выбор между **Fault Isolation** (процессы) и **Data Locality** (потоки). Самое важное: стоимость переключения контекста — это не только физическое время на сохранение регистров CPU. Настоящий, невидимый убийца производительности — это **TLB Flush** (сброс кэша трансляции адресов) и 

**Tags:** concurrency, os, threads, processes, linux

- **Full Article Access:** [L1.CONC.01 Threads vs processes, context switch cost.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.01 Threads vs processes, context switch cost.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.01 Threads vs processes, context switch cost.md`

---

<!-- @id: l1-conc-02-mutex-rw-lock-condition-variables-deadl -->
## L1.CONC.02: Mutex, RW‑lock, condition variables, deadlock patterns
<!-- @id: l1-conc-02-mutex-rw-lock-condition-variables-deadlock-patterns -->
**Executive Summary:** *   **Mutex** — это не только высокоуровневый `lock`, под капотом это тяжелый системный вызов (futex). Современные адаптивные мьютексы хитро крутятся в user-space перед тем, как уснуть в ядре. *   **RW-Lock** — это опасный инструмент, который часто **медленнее** обычного мьютекса из-за архитектурного эффекта "cache line bouncing" при постоянном обновлении счетчиков читателей на шине процессора. Ис

**Tags:** concurrency, synchronization, mutex, deadlock, multithreading

- **Full Article Access:** [L1.CONC.02 Mutex, RW‑lock, condition variables, deadlock patterns.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.02 Mutex, RW‑lock, condition variables, deadlock patterns.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.02 Mutex, RW‑lock, condition variables, deadlock patterns.md`

---

<!-- @id: l1-conc-03-event-loop-reactor-proactor-async-io -->
## L1.CONC.03: Event loop, reactor-proactor, async IO
<!-- @id: l1-conc-03-event-loop-reactor-proactor-async-io -->
**Executive Summary:** *   **Event Loop** — это фундаментальный бесконечный цикл, который ждет событий от ОС и диспетчеризует их. *   **Reactor** (модели на базе Linux `epoll`, BSD `kqueue`) — модель **"Готовности" (Readiness)**. ОС сообщает: "В сокете есть данные, можешь читать". Вы сами делаете системный вызов `read()`. *   **Proactor** (Windows `IOCP`, Linux `io_uring`) — модель **"Завершения" (Completion)**. Вы гово

**Tags:** concurrency, event-loop, reactor, proactor, async-io, linux

- **Full Article Access:** [L1.CONC.03 Event loop, reactor-proactor, async IO.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.03 Event loop, reactor-proactor, async IO.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.03 Event loop, reactor-proactor, async IO.md`

---

<!-- @id: l1-conc-04-goroutines-schedulers-channels-go -->
## L1.CONC.04: Goroutines, schedulers, channels (Go)
<!-- @id: l1-conc-04-goroutines-schedulers-channels-go -->
**Executive Summary:** *   **Горутины (Goroutines)** — это не системные потоки ОС. Это **Green Threads** (пользовательские потоки) с динамически растущим стеком, которыми полностью управляет рантайм Go (User-space scheduling). *   **GMP Model** — это математическое сердце планировщика Go: **G** (Goroutine), **M** (Machine / OS Thread), **P** (Processor / Логический контекст). Глубокое понимание этой троицы и механизма W

**Tags:** concurrency, golang, goroutines, channels, scheduling

- **Full Article Access:** [L1.CONC.04 Goroutines, schedulers, channels (Go).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.04 Goroutines, schedulers, channels (Go).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.04 Goroutines, schedulers, channels (Go).md`

---

<!-- @id: l1-conc-05-actor-model-akka-erlang-orleans -->
## L1.CONC.05: Actor model (Akka, Erlang, Orleans)
<!-- @id: l1-conc-05-actor-model-akka-erlang-orleans -->
**Executive Summary:** **Модель Акторов** — это мощный архитектурный паттерн, который концептуально решает проблему конкурентности (Concurrency) путем абсолютного отказа от **разделяемой памяти (Shared State)** и тяжелых системных блокировок (Locks/Mutex). *   **Erlang** — это родоначальник модели. Он исповедует философию "Let It Crash" и идеален для создания систем с фантастическим аптаймом 99.9999999% (Telecom/Messagi

**Tags:** concurrency, actor-model, erlang, akka, orleans, architecture

- **Full Article Access:** [L1.CONC.05 Actor model (Akka, Erlang, Orleans).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.05 Actor model (Akka, Erlang, Orleans).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.05 Actor model (Akka, Erlang, Orleans).md`

---

<!-- @id: l1-conc-06-lock-free-cas-aba -->
## L1.CONC.06: Lock-free структуры, CAS, ABA-проблема
<!-- @id: l1-conc-06-lock-free-cas-aba -->
**Executive Summary:** **Lock-free** — это парадигма, которая на самом деле вообще не про скорость (в большинстве случаев обычные Spinlocks или адаптивные Mutexes работают быстрее). Lock-free — это про **жесткую гарантию прогресса всей системы** (System-wide Progress). Отсутствие блокировок означает, что "заснувший", повисший на I/O или внезапно убитый ОС поток больше не сможет заморозить всю систему, заблокировав крити

**Tags:** concurrency, lock-free, cas, aba-problem, multithreading, memory-model

- **Full Article Access:** [L1.CONC.06 Lock‑free структуры, CAS, ABA‑проблема.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.06 Lock‑free структуры, CAS, ABA‑проблема.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.06 Lock‑free структуры, CAS, ABA‑проблема.md`

---

<!-- @id: l1-conc-07-java-memory-model-happens-before-volati -->
## L1.CONC.07: Java Memory Model, happens-before, volatile
<!-- @id: l1-conc-07-java-memory-model-happens-before-volatile -->
**Executive Summary:** **Java Memory Model (JMM)** — это не описание того, как физически работает кэш процессора (хотя они тесно связаны). Это строгая **спецификация (юридический контракт)** из JLS (Java Language Specification) Chapter 17, которая математически определяет частичный порядок (`partial order`) выполнения операций. Для инженера уровня Expert/Architect критически важно понимать не просто бытовую мантру "vola

**Tags:** concurrency, jmm, memory-model, happens-before, volatile, architecture

- **Full Article Access:** [L1.CONC.07 Java Memory Model, happens‑before, volatile.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.07 Java Memory Model, happens‑before, volatile.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.07 Java Memory Model, happens‑before, volatile.md`

---

<!-- @id: l1-conc-08-false-sharing-cache-coherence-mesi -->
## L1.CONC.08: False sharing, cache coherence (MESI)
<!-- @id: l1-conc-08-false-sharing-cache-coherence-mesi -->
**Executive Summary:** В современной вычислительной архитектуре наблюдается фундаментальный сдвиг парадигмы, который определяет большинство проблем производительности высоконагруженных систем (High-Load). С завершением эры масштабирования частот (Dennard scaling) и массовым переходом серверного железа к многоядерным процессорам, ответственность за финальную производительность сместилась с плеч аппаратного обеспечения на

**Tags:** concurrency, false-sharing, cache-coherence, mesi, architecture, performance

- **Full Article Access:** [L1.CONC.08 False sharing, cache coherence (MESI).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.08 False sharing, cache coherence (MESI).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.08 False sharing, cache coherence (MESI).md`

---

<!-- @id: l1-conc-09-coroutine-frameworks-kotlin-net-async-a -->
## L1.CONC.09: Coroutine frameworks (Kotlin, .NET async-await)
<!-- @id: l1-conc-09-coroutine-frameworks-kotlin-net-async-await -->
**Executive Summary:** **Корутины (Coroutines)** — это абсолютно не "легкие потоки" в привычном смысле операционной системы (как процессы или системные треды). Это чистая **компиляторная магия**, алгоритмически превращающая ваш обычный, линейно написанный код в сложнейший асинхронный **Конечный Автомат (State Machine)** под капотом. *   В экосистеме **.NET (C#)** это синтаксический сахар вокруг объектов `Task`, структур

**Tags:** concurrency, coroutines, async-await, csharp, kotlin, architecture

- **Full Article Access:** [L1.CONC.09 Coroutine frameworks (Kotlin, .NET async-await).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.09 Coroutine frameworks (Kotlin, .NET async-await).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.09 Coroutine frameworks (Kotlin, .NET async-await).md`

---

<!-- @id: l1-conc-10-structured-concurrency-go-kotlin-c-java -->
## L1.CONC.10: Structured Concurrency (Go, Kotlin, C++, Java, Python)
<!-- @id: l1-conc-10-structured-concurrency-go-kotlin-c-java-python -->
**Executive Summary:** **Structured Concurrency (Структурная конкурентность)** относится к дикому миру многопоточности точно так же, как строгое структурное программирование (блоки `if/for/function`) относится к хаотичному оператору `GOTO`. Это фундаментальный архитектурный принцип, согласно которому **время жизни любого фонового потока (или асинхронной задачи) должно быть жестко и математически ограничено лексическим (

**Tags:** concurrency, structured-concurrency, project-loom, golang, coroutines, python, architecture

- **Full Article Access:** [L1.CONC.10 Structured Concurrency (Go, Kotlin, C++, Java, Python).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.CONC/L1.CONC.10 Structured Concurrency (Go, Kotlin, C++, Java, Python).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.CONC/L1.CONC.10 Structured Concurrency (Go, Kotlin, C++, Java, Python).md`

---

