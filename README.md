# Chaos Enginnering

## 카오스 엔지니어링 정의

[PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/)와 같이 상용에서 비정상인 조건에서 시스템의 능력을 유지하기 위하여 사전에 시스템을 실험하는 훈련입니다. 

"Chaos Engineering is the discipline of experimenting on a system in order to build confidence in the system’s capability to withstand turbulent conditions in production.

2011년 netflix blog를 통해 알려진것처럼 scheduled된 agent(Netflix Chaos Monkey)가 아래의 동작을 수행하였고, 2015년 중반에 [PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/)에서 "Chaos engineering"으로 형상화됩니다. 

- Shut down services randomly
- Slow down performances
- Check conformity 
- Break an entire region
- Integrate with spinnaker (CI/CD)


Chaos engineering은 어플리케이션을 신뢰성을 확보할 수 있도록, 제어된 환경(Controlled environment)에서 잘 계획된 실험(experiment)을 통하여, 각 요소(thing)을 강제로 종료시킵니다.

- Chaos engineering is NOT about breaking things randomly without a purpose; chaos engineering is about breaking things in a controlled environment and through well-planned experiments in order to build confidence in your application to withstand turbulent conditions.

<!--
## Prerequisites to chaos engineering

### Software 
- Certificate expiration
- Memory leaks
- Licenses
- Versioning

### Infrastructure
- Redundancy (multi-AZ)
- Self-healing
- Isolation (bulkheads)
- Infrastructure as code

### Application
- Timeouts
- Retries w/backoff
- Exception handling
- Circuit breakers
- Load shedding

### Operations
- Human operators
- Monitoring and observability
- Incident response
- Measure, measure, measure
-->



## Chaos Engineering

### Phases of chaos engineering


<img width="541" alt="image" src="https://user-images.githubusercontent.com/52392004/204069568-45be3593-0e77-416f-a63e-c78b52ba3948.png">


주입되는 이벤트(Injected Event)는 state state를 망가트리는 아래와 같은 상황을 시뮬레이션 합니다. 

- Hardware failures, like servers dying
- Software failures, like malformed responses
- Nonfailure events, like spikes in traffic or scaling events

### Two rules to remember

#### Don't brame people for mistakes

#### There is no ioslated "cause" of an accident



### Usuful Commends

#### Simple 

$ docker stop 94a214bbeebd

#### DDos

```java
$ wrk -t12 -c400 -d30s http://127.0.0.1/api/health
```

#### Burn CPU with Stress(–ng)

[stress-ng](https://wiki.ubuntu.com/Kernel/Reference/stress-ng)

```java
$ stress-ng --cpu 0--cpu-method matrixprod -t 60s
```

#### Adding latency to the network

```java
$ tc qdisc add dev eth0 root netem delay 300ms
```

#### Blocks DNS resolution

```java
$ iptables -A INPUT -p tcp -m tcp --dport 53 -j DROP
```

#### Other fun things to do
- Fill up disk
- Network packet loss (using traffic-shaping)
- Network packet corruption (using traffic-shaping)
- Kills random processes
- Detach (force) all EBS volumes
- Mess with /etc/hosts


## Big challenges to chaos engineering

Mostly cultural  

- No time or flexibility to simulate disasters
- Teams already spending all of its time fixing things
- Can be very political
- Might force deep conversations
- Deeply invested in a specific technical roadmap (micro-services) that chaos engineering tests show is not as resilient to failures as originally predicted







## Reference

[Improving resiliency with chaos engineering](https://disaster-recovery.workshop.aws/en/intro/concepts/chaos-engineering.html)

[AWS re:Invent 2019: [REPEAT 1] Improving resiliency with chaos engineering (DOP309-R1)](https://www.youtube.com/watch?v=ztiPjey2rfY)

[DevOps 문화](https://www.redhat.com/ko/topics/devops)

[DevOps와 SRE 비교](https://www.redhat.com/ko/topics/devops/what-is-sre)

[PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/)
