# Chaos Enginnering

## 카오스 엔지니어링 정의

[PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/)와 같이 상용에서 비정상인 조건에서 시스템의 능력을 유지하기 위하여 사전에 시스템을 실험하는 훈련입니다. 

"Chaos Engineering is the discipline of experimenting on a system in order to build confidence in the system’s capability to withstand turbulent conditions in production.

2011년 netflix blog를 통해 알려진것처럼 scheduled된 agent가 아래의 동작을 수행하였고, 2015년 중반에 [PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/)에서 "Chaos engineering"으로 형상화됩니다. 

- Shut down services randomly
- Slow down performances
- Check conformity 
- Break an entire region
- Integrate with spinnaker (CI/CD)


Chaos engineering은 어플리케이션을 신뢰성을 확보할 수 있도록, 제어된 환경(Controlled environment)에서 잘 계획된 실험(experiment)을 통하여, 각 요소(thing)을 강제로 종료시킵니다.

- Chaos engineering is NOT about breaking things randomly without a purpose; chaos engineering is about breaking things in a controlled environment and through well-planned experiments in order to build confidence in your application to withstand turbulent conditions.



## Reference

[Improving resiliency with chaos engineering](https://disaster-recovery.workshop.aws/en/intro/concepts/chaos-engineering.html)

[AWS re:Invent 2019: [REPEAT 1] Improving resiliency with chaos engineering (DOP309-R1)](https://www.youtube.com/watch?v=ztiPjey2rfY)

[DevOps 문화](https://www.redhat.com/ko/topics/devops)

[DevOps와 SRE 비교](https://www.redhat.com/ko/topics/devops/what-is-sre)

[PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/)
