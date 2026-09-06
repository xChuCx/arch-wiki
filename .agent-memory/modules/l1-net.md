# L1 Networking & Protocols
<!-- @id: l1-networking-protocols -->

<!-- @id: l1-net-01-osi-vs-tcp-ip-l2-l7-encapsulation -->
## Пример вывода для нагруженного соединения
<!-- @id: section -->
**Executive Summary:** Если вы откроете любой академический учебник, первые 50 страниц будут посвящены модели OSI. **Инженерная реальность:** В современном интернете нет ни одного устройства, которое работало бы по "чистому" стеку протоколов OSI. Интернет работает на **TCP/IP**.  Почему же мы продолжаем учить OSI? Потому что OSI — это идеальная *языковая и концептуальная модель* (Reference Model). Это общий словарь, поз

- **Full Article Access:** [L1.NET.01 OSI vs TCP-IP, L2–L7, Encapsulation.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.01 OSI vs TCP-IP, L2–L7, Encapsulation.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.01 OSI vs TCP-IP, L2–L7, Encapsulation.md`

---

<!-- @id: l1-net-02-ethernet-vlan-stp-link-aggregation -->
## L1.NET.02: Ethernet, VLAN, STP, Link Aggregation
<!-- @id: l1-net-02-ethernet-vlan-stp-link-aggregation -->
**Executive Summary:** Данный материал представляет собой глубокое погружение в технологии 2-го уровня модели OSI (Канальный уровень). Понимание этих концепций критически важно для сетевых инженеров, DevOps-специалистов и системных архитекторов. Без знания "нижнего" уровня невозможно эффективно проектировать высоконагруженные облачные инфраструктуры (VPC, Kubernetes CNI) и траблшутить сетевые аномалии.

**Tags:** networking, ethernet, vlan, stp, lacp, l2

- **Full Article Access:** [L1.NET.02 Ethernet, VLAN, STP, link aggregation.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.02 Ethernet, VLAN, STP, link aggregation.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.02 Ethernet, VLAN, STP, link aggregation.md`

---

<!-- @id: l1-net-03-ip-addressing-subnetting-cidr-routing-ba -->
## L1.NET.03: IP addressing, subnetting, CIDR, routing basics
<!-- @id: l1-net-03-ip-addressing-subnetting-cidr-routing-basics -->
**Executive Summary:** Сетевой уровень (L3 модели OSI) — это кровеносная система любой инфраструктуры. Ошибки на уровне коммутации (L2) приводят к локальным сбоям, но ошибки проектирования L3 (IP-адресации и маршрутизации) закладывают фундаментальный технический долг. В этом материале мы разбираем, как мыслят Staff-архитекторы при планировании адресного пространства облаков, как аппаратно работают таблицы маршрутизации 

**Tags:** networking, ipam, cidr, routing, architecture, vpc

- **Full Article Access:** [L1.NET.03 IP addressing, subnetting, CIDR, routing basics.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.03 IP addressing, subnetting, CIDR, routing basics.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.03 IP addressing, subnetting, CIDR, routing basics.md`

---

<!-- @id: l1-net-04-bgp-path-selection-convergence-route-fla -->
## L1.NET.04: BGP - Path Selection, Convergence, Route Flapping, Communities (Максимально детализированный конспект)
<!-- @id: l1-net-04-bgp-path-selection-convergence-route-flapping-communit -->
**Executive Summary:** Данный материал покрывает продвинутые аспекты работы протокола BGP (Border Gateway Protocol) — клея, на котором держится весь интернет. Для Staff/Expert инженера понимание "магии" выбора пути (Path Selection Algorithm), механик быстрой сходимости (BGP PIC), деградации сетей из-за флаппинга и принципов маркировки трафика (Communities) является критическим. Вы научитесь управлять трафиком (Traffic E

**Tags:** networking, bgp, routing, architecture, convergence

- **Full Article Access:** [L1.NET.04 BGP - Path Selection, Convergence, Route Flapping, Communities (Detailed).md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.04 BGP - Path Selection, Convergence, Route Flapping, Communities (Detailed).md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.04 BGP - Path Selection, Convergence, Route Flapping, Communities (Detailed).md`

---

<!-- @id: l1-net-05-anycast-ecmp-routing-for-large-scale-ser -->
## Включаем multipath для BGP
<!-- @id: multipath-bgp -->
**Executive Summary:** **TL;DR**:  сеть — это не просто «труба». Это распределенная система с конкуренцией за ресурсы. *   **Anycast** превращает географию в топологию, позволяя использовать один IP на всех континентах, но ломает TCP-сессии при нестабильном BGP. *   **ECMP** позволяет масштабировать пропускную способность горизонтально (CLOS-сети), но страдает от "Hash P

- **Full Article Access:** [L1.NET.05 Anycast, ECMP, routing for large‑scale services.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.05 Anycast, ECMP, routing for large‑scale services.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.05 Anycast, ECMP, routing for large‑scale services.md`

---

<!-- @id: l1-net-06-tcp-3-way-handshake-connection-states-ti -->
## L1.NET.06: TCP 3-Way Handshake, Connection States, TIME_WAIT
<!-- @id: l1-net-06-tcp-3-way-handshake-connection-states-time-wait -->
**Executive Summary:** Для Staff/Senior инженера TCP — это не просто абстрактный транспортный протокол. Это сложный автомат состояний (State Machine), который тесно и жестко интегрирован с ядром операционной системы (Linux). В этом материале мы глубоко разбираем механику выделения памяти под сокеты, физику `TIME_WAIT` и защиту от SYN-флуда. Понимание этих процессов позволяет с первого взгляда отличать баги в коде прилож

**Tags:** networking, tcp, kernel, sysctl, architecture

- **Full Article Access:** [L1.NET.06 TCP 3‑way handshake, connection states, TIME_WAIT.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.06 TCP 3‑way handshake, connection states, TIME_WAIT.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.06 TCP 3‑way handshake, connection states, TIME_WAIT.md`

---

<!-- @id: l1-net-07-tcp-congestion-control-tahoe-reno-cubic- -->
## L1.NET.07 TCP congestion control Tahoe-Reno, CUBIC, BBR, BDP
<!-- @id: l1-net-07-tcp-congestion-control-tahoe-reno-cubic-bbr-bdp -->
**Executive Summary:** **TL;DR**: Эволюция Congestion Control (CC) — это история перехода от **реактивного** поведения (увидел потерю — затормозил) к **проактивному моделированию** канала. *   **Reno/Tahoe** управляют перегрузкой, заполняя буферы до отказа (Loss-based). *   **CUBIC** оптимизирует утилизацию на "толстых и длинных" каналах (LFN), но все еще заполняет буфер

- **Full Article Access:** [L1.NET.07 TCP congestion control Tahoe-Reno, CUBIC, BBR, BDP.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.07 TCP congestion control Tahoe-Reno, CUBIC, BBR, BDP.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.07 TCP congestion control Tahoe-Reno, CUBIC, BBR, BDP.md`

---

<!-- @id: l1-net-08-tcp-flow-control-sliding-window-nagle-de -->
## -i показывает внутреннюю TCP информацию, -t (tcp), -e (extended)
<!-- @id: i-tcp-t-tcp-e-extended -->
**Executive Summary:** **TL;DR**: TCP Flow Control — это механизм защиты **получателя** от переполнения (Backpressure). Не путать с Congestion Control (защитой сети). Критически важно понимать конфликт **Nagle + Delayed ACK**, который убивает latency в микросервисах (RPC), и уметь тюнить буферы под **Bandwidth-Delay Product (BDP)**, иначе ваш гигабитный канал будет работ

- **Full Article Access:** [L1.NET.08 TCP flow control, sliding window, Nagle, delayed ACK.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.08 TCP flow control, sliding window, Nagle, delayed ACK.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.08 TCP flow control, sliding window, Nagle, delayed ACK.md`

---

<!-- @id: l1-net-09-udp-quic-congestion-control-0-rtt -->
## L1.NET.09 UDP, QUIC - отличие по надёжности, congestion control, 0‑RTT
<!-- @id: l1-net-09-udp-quic-congestion-control-0-rtt -->
**Executive Summary:** **TL;DR**: *   **UDP** — это "сырая глина". В нем нет ничего, кроме портов и чексуммы. Используется, когда вам нужна полная свобода (свой протокол) или когда потеря пакетов допустима (VoIP, DNS). *   **QUIC** — это "космический корабль", построенный из глины UDP. Это **надежный**, **защищенный**, **мультиплексированный** транспорт, который работает

- **Full Article Access:** [L1.NET.09 UDP, QUIC - отличие по надёжности, congestion control, 0‑RTT.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.09 UDP, QUIC - отличие по надёжности, congestion control, 0‑RTT.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.09 UDP, QUIC - отличие по надёжности, congestion control, 0‑RTT.md`

---

<!-- @id: l1-net-10-tls-1-2-vs-1-3-handshake-session-resumpt -->
## L1.NET.10: TLS 1.2 vs 1.3, Handshake, Session Resumption, ALPN
<!-- @id: l1-net-10-tls-1-2-vs-1-3-handshake-session-resumption-alpn -->
**Executive Summary:** Переход с TLS 1.2 на 1.3 — это не просто смена мажорной версии протокола. Это фундаментальное изменение архитектуры сетевого рукопожатия (Handshake), безжалостное удаление устаревшей криптографии (смерть статического RSA Key Exchange) и введение концепции **0-RTT** (Zero Round Trip Time), которая является одновременно святым Граалем для латентности и проклятием для безопасности (из-за Replay Attac

**Tags:** networking, tls, security, handshake, cryptography

- **Full Article Access:** [L1.NET.10 TLS 1.2 vs 1.3, handshake, session resumption, ALPN.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.10 TLS 1.2 vs 1.3, handshake, session resumption, ALPN.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.10 TLS 1.2 vs 1.3, handshake, session resumption, ALPN.md`

---

<!-- @id: l1-net-11-http-1-1-vs-http-2-vs-http-3-multiplexin -->
## L1.NET.11: HTTP/1.1 vs HTTP/2 vs HTTP/3, Multiplexing, HoL Blocking (Максимально детализированный конспект)
<!-- @id: l1-net-11-http-1-1-vs-http-2-vs-http-3-multiplexing-hol-blocking -->
**Executive Summary:** Переход от HTTP/1.1 к HTTP/2 был амбициозной попыткой обмануть протокол TCP, но фундаментальную физику сети не обманешь. Последующий переход от HTTP/2 к HTTP/3 (на базе QUIC) — это историческая капитуляция инженеров перед ограничениями старого ядра ОС и "окаменелой" инфраструктурой (Ossified Middleboxes). Для Staff Architect разница между протоколами заключается не в банальной "скорости загрузки к

**Tags:** networking, http, quic, performance, architecture

- **Full Article Access:** [L1.NET.11 HTTP-1.1 vs HTTP-2 vs HTTP-3, multiplexing, HoL blocking.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.11 HTTP-1.1 vs HTTP-2 vs HTTP-3, multiplexing, HoL blocking.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.11 HTTP-1.1 vs HTTP-2 vs HTTP-3, multiplexing, HoL blocking.md`

---

<!-- @id: l1-net-12-dns-dnssec-load-balancing-via-dns -->
## L1.NET.12: DNS, DNSSEC, Load Balancing via DNS
<!-- @id: l1-net-12-dns-dnssec-load-balancing-via-dns -->
**Executive Summary:** В этом материале мы глубоко погружаемся в систему доменных имен (DNS) — самую критичную точку отказа (SPOF) современного интернета. Вы узнаете, почему DNS является ужасным балансировщиком соединений, но гениальным диспетчером глобального трафика. Мы разберем анатомию DNSSEC, чтобы понять, почему внедрение криптографии в старый протокол порождает кошмары эксплуатации (усиление DDoS и проблемы MTU),

**Tags:** networking, dns, dnssec, load-balancing, architecture

- **Full Article Access:** [L1.NET.12 DNS, DNSSEC, load balancing via DNS.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.12 DNS, DNSSEC, load balancing via DNS.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.12 DNS, DNSSEC, load balancing via DNS.md`

---

<!-- @id: l1-net-13-grpc-http-2-framing-streaming-deadlines- -->
## L1.NET.13: gRPC - HTTP/2 Framing, Streaming, Deadlines, Interceptors
<!-- @id: l1-net-13-grpc-http-2-framing-streaming-deadlines-interceptors -->
**Executive Summary:** На уровне Junior разработчик воспринимает gRPC просто как "удаленный вызов функции". На уровне Staff/Expert архитектора gRPC — это сложный бинарный **протокол поверх HTTP/2**, использующий мультиплексирование, жесткое управление окном передачи (Flow Control) и распределенный контекст. Вы обязаны понимать, как `LPM` (Length-Prefixed Message) упаковывается в `DATA` фреймы, почему HTTP-заголовки `Tra

**Tags:** networking, grpc, http2, streaming, architecture

- **Full Article Access:** [L1.NET.13 gRPC - HTTP-2 framing, streaming, deadlines, interceptors.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.13 gRPC - HTTP-2 framing, streaming, deadlines, interceptors.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.13 gRPC - HTTP-2 framing, streaming, deadlines, interceptors.md`

---

<!-- @id: l1-net-14-service-mesh-envoy-sidecar-mtls-xds-apis -->
## L1.NET.14: Service Mesh - Envoy, sidecar, mTLS, xDS APIs
<!-- @id: l1-net-14-service-mesh-envoy-sidecar-mtls-xds-apis -->
**Executive Summary:** Service Mesh (в реализации Envoy / Istio) радикально меняет парадигму разработки. Он агрессивно выносит всю сетевую логику (повторные попытки, Circuit Breaking, шифрование mTLS, телеметрию) из кода самого приложения в независимый инфраструктурный слой. На уровне **Expert Архитектора** недостаточно знать, как написать YAML-манифест. Вы должны понимать: 1.  **Threading Model Envoy:** Почему этот C++

**Tags:** networking, service-mesh, envoy, mtls, architecture

- **Full Article Access:** [L1.NET.14 Service Mesh - Envoy, sidecar, mTLS, xDS APIs.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.14 Service Mesh - Envoy, sidecar, mTLS, xDS APIs.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.14 Service Mesh - Envoy, sidecar, mTLS, xDS APIs.md`

---

<!-- @id: l1-net-15-sdn-openflow-control-plane-vs-data-plane -->
## L1.NET.15: SDN - OpenFlow, control plane vs data plane
<!-- @id: l1-net-15-sdn-openflow-control-plane-vs-data-plane -->
**Executive Summary:** **SDN (Software-Defined Networking)** — это радикальный архитектурный подход, при котором "мозги" сети (Control Plane) физически и логически отделяются от "мышц" (Data Plane). Вместо того чтобы вручную настраивать каждый железный роутер отдельно через CLI по протоколу SSH, вы программируете всю инфраструктуру целиком через центральный контроллер. Для современного IT-Архитектора важно понимать: есл

**Tags:** networking, sdn, openflow, vxlan, architecture

- **Full Article Access:** [L1.NET.15 SDN - OpenFlow, control plane vs data plane.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.15 SDN - OpenFlow, control plane vs data plane.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.15 SDN - OpenFlow, control plane vs data plane.md`

---

<!-- @id: l1-net-16-anycast-cdn-edge-pop-geo-routing -->
## L1.NET.16: Anycast-CDN, edge-pop, geo-routing
<!-- @id: l1-net-16-anycast-cdn-edge-pop-geo-routing -->
**Executive Summary:** В этом материале мы глубоко погружаемся в архитектуру глобальной доставки контента. Чтобы ваш сервис работал молниеносно в Австралии, пока его главный сервер (Origin) физически стоит во Франкфурте, вы не можете просто "оптимизировать код бэкенда". Вам нужно обмануть саму физику и скорость света в оптоволокне. *   **Edge PoP** — это архитектурный паттерн выноса тяжелого "рукопожатия" (TCP/TLS) макс

**Tags:** networking, cdn, anycast, geo-routing, bgp, architecture

- **Full Article Access:** [L1.NET.16 Anycast‑CDN, edge‑pop, geo‑routing.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.16 Anycast‑CDN, edge‑pop, geo‑routing.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.16 Anycast‑CDN, edge‑pop, geo‑routing.md`

---

<!-- @id: l1-net-17-network-virtualization-vxlan-geneve-over -->
## L1.NET.17: Network Virtualization - VXLAN, Geneve, Overlay networks internals
<!-- @id: l1-net-17-network-virtualization-vxlan-geneve-overlay-networks-i -->
**Executive Summary:** Современный глобальный дата-центр (или публичное облако AWS/GCP/Azure) — это уже давно не просто куча медных проводов, воткнутых в один гигантский свитч. Это строгая, двухуровневая архитектура: **Underlay** (физическая железная сеть, работающая как простое, скоростное IP-такси) и **Overlay** (виртуальная программная сеть, которая "возит" пакеты ваших виртуальных машин в инкапсулированных туннелях)

**Tags:** networking, vxlan, sdn, overlay, underlay, architecture

- **Full Article Access:** [L1.NET.17 Network Virtualization - VXLAN, Geneve, Overlay networks internals.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.17 Network Virtualization - VXLAN, Geneve, Overlay networks internals.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.17 Network Virtualization - VXLAN, Geneve, Overlay networks internals.md`

---

<!-- @id: l1-net-18-vpn-vless-xray -->
## L1.NET.18: VPN, VLESS, XRAY
<!-- @id: l1-net-18-vpn-vless-xray -->
**Executive Summary:** Если вы, как инженер, искренне думаете, что современный VPN — это IPsec, OpenVPN или даже новенький WireGuard, вы застряли архитектурно в 2015 году. В современных условиях тотального и агрессивного DPI (Deep Packet Inspection), машинного обучения на трафике и государственной цензуры (GFW в Китае, ТСПУ в РФ, корпоративные ML-фаерволы) любые классические VPN-протоколы блокируются по сигнатурам загол

**Tags:** networking, vpn, xray, vless, xtls, architecture

- **Full Article Access:** [L1.NET.18 VPN, VLESS, XRAY.md](file:///i:/TestProj/arch-wiki/4Layers/L1. Foundations/L1.NET/L1.NET.18 VPN, VLESS, XRAY.md)
- **Repository Path:** `4Layers/L1. Foundations/L1.NET/L1.NET.18 VPN, VLESS, XRAY.md`

---

