# L1 Operating Systems & Linux Kernel
<!-- @id: l1-operating-systems-linux-kernel -->

<!-- @id: l1-os-01-linux-user-kernel-space-syscalls-extreme- -->
## profiling_read.py (Python BPF wrapper)
<!-- @id: profiling-read-py-python-bpf-wrapper -->
**Executive Summary:** --- ## 1. Аппаратная реализация: Protection Domains & Privilege Levels

- **Full Article Access:** [L1.OS.01 Архитектура ядра Linux - user-kernel space, syscalls Extreme Expansion.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.01 Архитектура ядра Linux - user-kernel space, syscalls Extreme Expansion.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.01 Архитектура ядра Linux - user-kernel space, syscalls Extreme Expansion.md`

---

<!-- @id: l1-os-02-cfs-cgroups-extreme-expansion-redux -->
## Посмотреть текущую политику и приоритет PID 1234
<!-- @id: pid-1234 -->
**Executive Summary:** **TL;DR**: Если вы считаете, что Linux делит процессор поровну по времени — вы застряли в 90-х. Современный планировщик **CFS (Completely Fair Scheduler)** оперирует понятием **Virtual Runtime (`vruntime`)**. Для Staff Architect критически важно понимать механику **Cgroups Throttling**, из-за которой ваши Kubernetes-поды получают latency spikes даж

- **Full Article Access:** [L1.OS.02 Планировщик задач (CFS), приоритеты, cgroups Extreme Expansion REDUX.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.02 Планировщик задач (CFS), приоритеты, cgroups Extreme Expansion REDUX.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.02 Планировщик задач (CFS), приоритеты, cgroups Extreme Expansion REDUX.md`

---

<!-- @id: l1-os-03-virtual-memory-paging-page-cache-numa-awa -->
## L1.OS.03 Virtual memory, paging, page cache, NUMA awareness Extreme Expansion REDUX
<!-- @id: l1-os-03-virtual-memory-paging-page-cache-numa-awareness-extreme -->
**Executive Summary:** **TL;DR**: Для Staff Architect память — это не просто `malloc`. Это слоеный пирог абстракций, где каждый слой имеет свою цену. *   **Virtual Memory** — это иллюзия, которая стоит тактов CPU (TLB misses). *   **Page Cache** — это причина, почему ваша БД работает быстро (или почему она встает колом при `fsync`). *   **NUMA** — это физическая реальнос

- **Full Article Access:** [L1.OS.03 Virtual memory, paging, page cache, NUMA awareness Extreme Expansion REDUX.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.03 Virtual memory, paging, page cache, NUMA awareness Extreme Expansion REDUX.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.03 Virtual memory, paging, page cache, NUMA awareness Extreme Expansion REDUX.md`

---

<!-- @id: l1-os-04-memory-reclaim-swapping-oom-killer-extrem -->
## L1.OS.04 Memory Reclaim, Swapping & OOM Killer Extreme Expansion REDUX
<!-- @id: l1-os-04-memory-reclaim-swapping-oom-killer-extreme-expansion-re -->
**Executive Summary:** **TL;DR**: Swapping — это не просто "медленная память на диске", это механизм управления анонимными страницами. OOM Killer — это не случайный убийца, а детерминированный алгоритм, управляемый через cgroups. Для Staff Architect важно понимать разницу между **kswapd** (фоновая очистка) и **Direct Reclaim** (блокирующая очистка), а также уметь использ

- **Full Article Access:** [L1.OS.04 Memory Reclaim, Swapping & OOM Killer Extreme Expansion REDUX.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.04 Memory Reclaim, Swapping & OOM Killer Extreme Expansion REDUX.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.04 Memory Reclaim, Swapping & OOM Killer Extreme Expansion REDUX.md`

---

<!-- @id: l1-os-05-copy-on-write-fork-exec-overcommit-extrem -->
## L1.OS.05 Copy-on-write, fork-exec, overcommit Extreme Expansion REDUX
<!-- @id: l1-os-05-copy-on-write-fork-exec-overcommit-extreme-expansion-re -->
**Executive Summary:** **TL;DR**: Для уровня Staff Architect вы должны понимать, что `fork()` — это **не** копирование памяти (сразу), а операция над **таблицами страниц** (Page Tables). Вы должны видеть связь между `fork`, латентностью записи (COW faults) и фрагментацией Huge Pages. Если вы не понимаете `overcommit_memory`, ваши базы данных (Redis, Postgres) будут падат

- **Full Article Access:** [L1.OS.05 Copy-on-write, fork-exec, overcommit Extreme Expansion REDUX.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.05 Copy-on-write, fork-exec, overcommit Extreme Expansion REDUX.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.05 Copy-on-write, fork-exec, overcommit Extreme Expansion REDUX.md`

---

<!-- @id: l1-os-06-filesystems-basics-vfs-inodes-journaling- -->
## L1.OS.06 Filesystems basics - VFS, inodes, journaling Extreme Expansion REDUX
<!-- @id: l1-os-06-filesystems-basics-vfs-inodes-journaling-extreme-expans -->
**Executive Summary:** **TL;DR**: Для Staff Architect файловая система (ФС) — это не просто дерево папок. Это **база данных**, встроенная в ядро. *   **VFS** — это уровень полиморфизма, цена которого — CPU cycles на лукапы. *   **Inode** — это источник проблем с конкуренцией (lock contention) и фрагментацией. *   **Journaling** — это компромисс между скоростью записи (`d

- **Full Article Access:** [L1.OS.06 Filesystems basics - VFS, inodes, journaling Extreme Expansion REDUX.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.06 Filesystems basics - VFS, inodes, journaling Extreme Expansion REDUX.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.06 Filesystems basics - VFS, inodes, journaling Extreme Expansion REDUX.md`

---

<!-- @id: l1-os-07-ext4-journaling-modes-delayed-allocation -->
## L1.OS.07 ext4 journaling modes, delayed allocation
<!-- @id: l1-os-07-ext4-journaling-modes-delayed-allocation -->
**Executive Summary:** **TL;DR**: Ext4 — это не просто контейнер для файлов, это транзакционная система. **Delayed Allocation** превращает файловую систему в "умный кэш", оптимизируя раскладку на диске, но повышая риск потери данных при панике ядра. **Journaling Modes** определяют контракт целостности: вы должны выбирать между двойной записью всего (`journal`), гарантией

- **Full Article Access:** [L1.OS.07 ext4 journaling modes, delayed allocation.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.07 ext4 journaling modes, delayed allocation.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.07 ext4 journaling modes, delayed allocation.md`

---

<!-- @id: l1-os-08-zfs-cow-snapshots-checksums-arc-l2arc -->
## 1. Создаем пул из 3 зеркал (Striped Mirrors) с правильным выравниванием
<!-- @id: 1-3-striped-mirrors -->
**Executive Summary:** **TL;DR**: ZFS — это не просто файловая система, это гибрид LVM (Logical Volume Manager) и FS. *   **CoW** гарантирует, что вы никогда не увидите поврежденный файл после отключения питания (прощай, `fsck`). *   **Checksums** спасают от тихой порчи данных (bit rot), чего не делает аппаратный RAID. *   **ARC** — это самый умный алгоритм кэширования в

- **Full Article Access:** [L1.OS.08 ZFS - CoW, snapshots, checksums, ARC-L2ARC.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.08 ZFS - CoW, snapshots, checksums, ARC-L2ARC.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.08 ZFS - CoW, snapshots, checksums, ARC-L2ARC.md`

---

<!-- @id: l1-os-09-io-schedulers-blk-mq-async-io -->
## /etc/udev/rules.d/60-ioschedulers.rules
<!-- @id: etc-udev-rules-d-60-ioschedulers-rules -->
**Executive Summary:** **TL;DR**: Если ваш сервер "тормозит диском", но `iostat` показывает утилизацию 50%, скорее всего, вы уперлись не в диск, а в **планировщик ядра** или архитектуру очередей. Для современных NVMe SSD старые подходы (CFQ, Single Queue) — это бутылочное горлышко. Практик должен знать, как включить `blk-mq`, почему `io_uring` меняет правила игры для баз

- **Full Article Access:** [L1.OS.09 IO schedulers, blk‑mq, async IO.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.09 IO schedulers, blk‑mq, async IO.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.09 IO schedulers, blk‑mq, async IO.md`

---

<!-- @id: l1-os-10-ebpf-bpf-vm-maps-hooks-kprobe-tracepoint -->
## Генерация заголовка из текущего ядра
<!-- @id: section -->
**Executive Summary:** **TL;DR**: Для уровня Staff/Expert eBPF — это не просто «инструмент трассировки» или «tcpdump на стероидах». Это **программируемое ядро** (kernel programmability interface). Это способ исполнять вашу логику в пространстве ядра (Ring 0) безопасно и эффективно, без написания модулей ядра (Kernel Modules), которые могут вызвать Kernel Panic. Вы должны

- **Full Article Access:** [L1.OS.10 eBPF - BPF VM, maps, hooks (kprobe, tracepoint).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.10 eBPF - BPF VM, maps, hooks (kprobe, tracepoint).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.10 eBPF - BPF VM, maps, hooks (kprobe, tracepoint).md`

---

<!-- @id: l1-os-11-containers-vs-vms-namespaces-cgroups-secc -->
## Запускаем bash в новых пространствах имен:
<!-- @id: bash -->
**Executive Summary:** **TL;DR**: Для Staff Architect фраза "Контейнер — это легковесная VM" — это профессиональная непригодность. *   **VM** — это виртуализация **Hardware**. У вас есть Guest Kernel, которое общается с виртуальным железом. Граница безопасности — это гипервизор (Ring -1). *   **Контейнер** — это виртуализация **OS Userspace**. Это обычные процессы Linux,

- **Full Article Access:** [L1.OS.11 Containers vs VMs - namespaces, cgroups, seccomp.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.OS/L1.OS.11 Containers vs VMs - namespaces, cgroups, seccomp.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.OS/L1.OS.11 Containers vs VMs - namespaces, cgroups, seccomp.md`

---

