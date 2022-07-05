# Awesome Network Protocol Fuzzing

![Last Update](https://img.shields.io/github/last-commit/andreia-oca/awesome-network-protocol-fuzzing)

---

- [Description](#description)
- [Labels Indexes](#labels-indexes)
    - [By Type](#by-type)
    - [By Purpose](#by-purpose)
- [Papers](#papers)
- [Resources](#resources)
- [Contribution](#contribution)
- [Credits](#credits)

---

## Description

A **list of helpful fuzzing tools and research materials** for network protocols can be found in this repository.

All resources are alphabetically organized and labeled, making it simple to locate them simply searching one item from the index on the entire page (with `CTRL+F`). The ones not having a link attached are present in the `documents/` folder.

## Labels Indexes

### By Type



### By Purpose



## Papers

| Paper Title | Open Source Project | Abstract | Venue | Publication Date |
| --- | --- | --- | --- | --- |
| **[AFLNET](https://mboehme.github.io/paper/ICST20.AFLNet.pdf)** | [Repository](https://mboehme.github.io/paper/ICST20.AFLNet.pdf) | <details> <summary>Click to see the abstract!</summary> Server fuzzing is difficult. Unlike simple command-line tools, servers feature a massive state space that can be traversed effectively only with well-defined sequences of input messages. Valid sequences are specified in a protocol. In this paper, we present AFLNET, the first greybox fuzzer for protocol implementations. Unlike existing protocol fuzzers, AFLNET takes a mutational approach and uses state-feedback to guide the fuzzing process. AFLNET is seeded with a corpus of recorded message exchanges between the server and an actual client. No protocol specification or message grammars are required. AFLNET acts as a client and replays variations of the original sequence of messages sent to the server and retains those variations that were effective at increasing the coverage of the code or state space. To identify the server states that are exercised by a message sequence, AFLNET uses the server's response codes. From this feedback, AFLNET identifies progressive regions in the state space, and systematically steers towards such regions. The case studies with AFLNET on two popular protocol implementations demonstrate a substantial performance boost over the state-of the-art. AFLNET discovered two new CVEs which are classified as critical (CVSS score CRITICAL 9.8). </details> | ICST20 | 2020 |
| **[EPF](https://ieeexplore.ieee.org/document/9647801)** | [Repository](https://github.com/fkie-cad/epf) | <details> <summary>Click to see the abstract!</summary> Network fuzzing is a complex domain requiring fuzzers to handle highly structured input and communication schemes. In fuzzer development, such protocol-dependent semantics usually cause a focus on applicability: Resulting fuzz engines provide powerful APIs to add new protocols but rarely incorporate algorithmic fuzz improvements like the successful coverage-guidance. This paper aims to combine applicability and well-established algorithms for increased network fuzzing effectiveness. We introduce EPF, a coverage-guided and protocol-aware network fuzzing framework. EPF uses population-based simulated annealing to heuristically schedule packet types during fuzzing. In conjunction with a genetic algorithm that uses coverage metrics as fitness function, the framework steers input generation towards coverage maximization. Users can add protocols by defining packet models and state graphs through a Scapy-powered API. We collect first data in a case study on fuzzing the IEC 60870-5-104 SCADA protocol and compare EPF with AFLNet. Based on a total of 600 CPU days of fuzzing, we measure effectiveness using bug and coverage metrics. We report promising results that a) indicate similar performance to AFLNet without any optimizations and b) point out the potential and shortcomings of our approach. </details> | PST 2021 | 2021 |
| **[Multifuzz](https://www.semanticscholar.org/paper/MultiFuzz%3A-A-Coverage-Based-Multiparty-Protocol-for-Zeng-Lin/270667ae047643d49f98bbeb04c76a6e3d71e368)** | Not found | <details> <summary>Click to see the abstract!</summary> The publish/subscribe model has gained prominence in the Internet of things (IoT) network, and both Message Queue Telemetry Transport (MQTT) and Constrained Application Protocol (CoAP) support it. However, existing coverage-based fuzzers may miss some paths when fuzzing such publish/subscribe protocols, because they implicitly assume that there are only two parties in a protocol, which is not true now since there are three parties, i.e., the publisher, the subscriber and the broker. In this paper, we propose MultiFuzz, a new coverage-based multiparty-protocol fuzzer. First, it embeds multiple-connection information in a single input. Second, it uses a message mutation algorithm to stimulate protocol state transitions, without the need of protocol specifications. Third, it uses a new desockmulti module to feed the network messages into the program under test. desockmulti is similar to desock (Preeny), a tool widely used by the community, but it is specially designed for fuzzing and is 10x faster. We implement MultiFuzz based on AFL, and use it to fuzz two popular projects Eclipse Mosquitto and libCoAP. We reported discovered problems to the projects. In addition, we compare MultiFuzz with AFL and two state-of-the-art fuzzers, MOPT and AFLNET, and find it discovering more paths and crashes </details> | Sensors | 2020 |
| **[Nyx-Net](https://arxiv.org/abs/2111.03013)** | [Repository](https://github.com/RUB-SysSec/nyx-net) | <details> <summary>Click to see the abstract!</summary> Coverage-guided fuzz testing ('fuzzing') has become mainstream and we have observed lots of progress in this research area recently. However, it is still challenging to efficiently test network services with existing coverage-guided fuzzing methods. In this paper, we introduce the design and implementation of Nyx-Net, a novel snapshot-based fuzzing approach that can successfully fuzz a wide range of targets spanning servers, clients, games, and even Firefox's Inter-Process Communication (IPC) interface. Compared to state-of-the-art methods, Nyx-Net improves test throughput by up to 300x and coverage found by up to 70%. Additionally, Nyx-Net is able to find crashes in two of ProFuzzBench's targets that no other fuzzer found previously. When using Nyx-Net to play the game Super Mario, Nyx-Net shows speedups of 10-30x compared to existing work. Under some circumstances, Nyx-Net is even able play 'faster than light': solving the level takes less wall-clock time than playing the level perfectly even once. Nyx-Net is able to find previously unknown bugs in servers such as Lighttpd, clients such as MySQL client, and even Firefox's IPC mechanism - demonstrating the strength and versatility of the proposed approach. Lastly, our prototype implementation was awarded a $20.000 bug bounty for enabling fuzzing on previously unfuzzable code in Firefox and solving a long-standing problem at Mozilla. </details> | PST 2021 | 2021 |
| **[ProFuzzBench](https://arxiv.org/abs/2101.05102)** | [Repository](https://github.com/profuzzbench/profuzzbench) | <details> <summary>Click to see the abstract!</summary> We present a new benchmark (ProFuzzBench) for stateful fuzzing of network protocols. The benchmark includes a suite of representative open-source network servers for popular protocols, and tools to automate experimentation. We discuss challenges and potential directions for future research based on this benchmark. </details> | ISSTA 2021 | 2021 |
| **[Snapfuzz](https://arxiv.org/abs/2201.04048)** | Not found | <details> <summary>Click to see the abstract!</summary> In recent years, fuzz testing has benefited from increased computational power and important algorithmic advances, leading to systems that have discovered many critical bugs and vulnerabilities in production software. Despite these successes, not all applications can be fuzzed efficiently. In particular, stateful applications such as network protocol implementations are constrained by their low fuzzing throughput and the need to develop fuzzing harnesses that reset their state and isolate their side effects. In this paper, we present SnapFuzz, a novel fuzzing framework for network applications. SnapFuzz offers a robust architecture that transforms slow asynchronous network communication into fast synchronous communication based on UNIX domain sockets, speeds up all file operations by redirecting them to an in-memory filesystem, and removes the need for many fragile modifications, such as configuring time delays or writing cleanup scripts, together with several other improvements. Using SnapFuzz, we fuzzed five popular networking applications: LightFTP, Dnsmasq, LIVE555, TinyDTLS and Dcmqrscp. We report impressive performance speedups of 72.4x, 49.7x, 24.8x, 23.9x, and 8.5x, respectively, with significantly simpler fuzzing harnesses in all cases. Through its performance advantage, SnapFuzz has also found 12 previously-unknown crashes in these applications. </details> | CoRR 2022 | 2022 |


## Resources



## Contribution

1. Edit the `resources.csv` file.
2. Push the changes into the GitHub repository.
3. Wait for the GitHub action to automatically recompile `README.md`.

## Credits

The template is inspired from this [repository](https://github.com/CyberReasoningSystem/awesome-binary-analysis).
