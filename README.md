## 프로젝트

## Kori (코리)

**Cori**는 언어의 장벽 없는 소통을 위한 **글로벌 실시간 채팅 플랫폼**입니다. 물리적 서버 증설 없이 **단일 서버(Single Instance)** 환경에서 극한의 성능 최적화를 통해, 1,000명 규모의 그룹 채팅 트래픽(Fan-out)을 안정적으로 처리하는 것을 목표 했습니다.

**기간**: 2025.07 ~ 2026.03 (현재 진행형)

### 주요 기여

**단일 서버 동시성 성능 최적화 (Zero-Copy)**:

* **Zero-Copy 브로드캐스팅**을 도입하여 1:N 채팅 구조의 직렬화(Serialization) 부하를 제거, 스케일 아웃 없이 동시 접속자 1,000명을 안정적으로 수용
* 기존 블로킹 방식 대비 응답 속도 **약 2,000배 단축 (52s → 0.02s)** 및 처리량(TPS) **77배** 향상 달성

**비동기 이벤트 기반 메시징 파이프라인**:

* 번역 API 호출 및 FCM 알림 등 고비용 작업을 **비동기(`CompletableFuture`)**로 분리하여 메인 스레드 블로킹(Thread Starvation) 방지
* 대규모 트래픽 유입 시 발생하던 '댐 붕괴 효과(Dam Burst Effect)' 및 DB 커넥션 고갈 문제를 해결하여 **에러율 0%** 달성

**인터랙티브 AI 페르소나(Agent) 개발**:

* 대화 참여도와 침묵 시간(Silence Threshold)을 분석하여 AI의 개입 확률을 동적으로 조절하는 알고리즘 적용
* 메시지 길이에 비례한 **Thinking & Typing Delay**를 시뮬레이션하여 실제 사람과 대화하는 듯한 자연스러운 UX 구현

**아키텍처 및 기술 스택**

* **Core**: Java, Spring Boot, WebSocket (STOMP),Postgre SQL
* **Infra**: Docker, Nginx 

---

## Naviya

Naviya는 U+ 개발자 부트캠프의 팀 프로젝트 요구사항 및 과제인 **개인 맞춤형 서비스**와 더불어, **매일 오후 1시 정각부터 10분간, 분당 10만 건**의 대규모 트래픽을 안정적으로 처리해야 하는 도전적인 요구사항을 해결하기 위해 시작되었습니다.

**기간**: 2024.10 ~ 2025.11

### 주요 기여

**서버리스 아키텍처 도입으로 비용 절감**:

* 트래픽 집중 구간을 Lambda 기반 서버리스 구조로 전환하여 EC2 증설 대비 **47%(월 36만원)이상 비용 절감**

**다중 캐싱 전략으로 DB 부하 99.99% 이상 감소**

* Redis와 CloudFront를 활용한 이중 캐싱 구조로, 읽기·쓰기 부하를 효과적으로 분산 처리
* **Redis (쓰기 캐싱)**: 10분간 100만 건의 응모 요청을 DB 대신 Redis에 임시 저장 후, 당첨자 100명만 DB에 기록 → 쓰기 부하 **99.99% 감소**
* **CloudFront (읽기 캐싱)**: 정적 페이지 및 당첨자 결과(JSON)를 CloudFront에서 캐싱하여 수십만 건의 요청을 서버와 DB 없이 처리 → 읽기 부하 **100% 차단**



**Redis를 이용한 동시성 제어 및 비동기 처리**:

* 좋아요/싫어요 등 빈번한 쓰기 요청을 Redis 기반 큐로 비동기 처리하여 DB 경합 및 데드락을 방지하고, 응답 속도를 약 **97.5%** 단축

**동적 가중치 기반 추천 시스템 구현**:

* 사용자의 MBTI, 피드백 등을 실시간으로 반영하는 동적 가중치 조정법을 적용하여 개인화 추천 시스템을 구축

**terraform 기반 인프라 자동화 (IaC)**:

* AWS 인프라 전체를 코드로 관리, 인프라의 재현성과 변경 관리의 효율성을 확보

---

## 댕댕어디가

**댕댕어디가**는 반려동물과 함께 외출할 때의 불편함을 줄이고, 더 많은 활동을 즐길 수 있도록 돕는 서비스입니다. 웹사이트를 통해 반려견과 동반 가능한 장소를 쉽게 검색하고, 다양한 추천 기능을 통해 맞춤형 장소 정보를 제공합니다. 또한, 실시간 **땅따먹기 시스템**으로 사용자들에게 재미와 보상을 제공합니다!

**기간**: 2024.11 ~ 2025.3

### 주요 기여

**사용자 맞춤 장소 추천 시스템 최적화**

* 위치 기반 정보와 사용자 선호도를 반영하는 추천 로직 설계
* 성능 최적화: 294.63ms에서 172.63ms로 약 **41.42%** 성능 개선
* Redis를 활용한 위치 기반 캐싱

**AWS 서버 구성, 고가용성 및 인프라 자동화(IaC):**

* Terraform을 활용한 AWS 인프라(VPC, EKS, ALB, RDS, ElastiCache 등) 코드 기반 구축 및 관리
* GitHub Actions 기반 Terraform CI/CD 파이프라인 구축 (PR 시 Plan 검증, 환경별 Apply)
* GitHub Actions를 활용한 애플리케이션 CI/CD 파이프라인 구축
* 컨테이너 배포 환경의 Amazon EKS 전환 및 CI/CD 기반 카나리 무중단 배포 및 롤백 자동화 구축 (Docker, EKS, Nginx Ingress, GitHub Actions)
* Prometheus + Grafana 기반 실시간 모니터링 구축

**시큐리티 & OAuth & 쿠키 관리**:

* OAuth2 인증 시스템 구현
* Redis를 이용한 리프레시 토큰 블랙리스트 관리
* Nginx와 Lua 스크립트를 활용한 쿠키 암호화 및 보안 강화

### 아키텍쳐

**AWS 서버 구성**
 ![compact_eks-based_aws_architecture](https://github.com/user-attachments/assets/cfe6d847-699a-45c2-8751-2489874fd60c)

**배포 파이프라인**
  ![cd_with_github_actions_+_ecr_+_eks_+_argo_rollouts_+_eso](https://github.com/user-attachments/assets/ee4e1714-9e3f-4b0f-a575-bbdb3d646fed)
  🔗 [프로젝트 링크](https://github.com/WHERE-ARE-YOU-GOING-DAENG-DAENG/WHERE_ARE_YOU_GOING_DAENG_DAENG_-)

---
## 🏆 백준 프로필
[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=sh5017)](https://solved.ac/sh5017/)


## 💬 연락처
- **이메일**: [lixxce5017@gmail.com](lixxce5017@gmail.com)
--
