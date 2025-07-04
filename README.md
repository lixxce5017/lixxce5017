

##  프로젝트
#  댕댕어디가 

**댕댕어디가**는 반려동물과 함께 외출할 때의 불편함을 줄이고, 더 많은 활동을 즐길 수 있도록 돕는 서비스입니다. 웹사이트를 통해 반려견과 동반 가능한 장소를 쉽게 검색하고, 다양한 추천 기능을 통해 맞춤형 장소 정보를 제공합니다. 또한, 실시간 **땅따먹기 시스템**으로 사용자들에게 재미와 보상을 제공합니다!

**기간**: 2024.11 ~ 2025.3

### 주요 기여
**사용자 맞춤 장소 추천 시스템 최적화**

- 위치 기반 정보와 사용자 선호도를 반영하는 추천 로직 설계
- 성능 최적화: 294.63ms에서 172.63ms로 약 **41.42%** 성능 개선
- Redis를 활용한 위치 기반 캐싱

**AWS 서버 구성, 고가용성 및 인프라 자동화(IaC):**

- Terraform을 활용한 AWS 인프라(VPC, EKS, ALB, RDS, ElastiCache 등) 코드 기반 구축 및 관리
- GitHub Actions 기반 Terraform CI/CD 파이프라인 구축 (PR 시 Plan 검증, 환경별 Apply)
- GitHub Actions를 활용한 애플리케이션 CI/CD 파이프라인 구축
- 컨테이너 배포 환경의 Amazon EKS 전환 및 CI/CD 기반 카나리 무중단 배포 및 롤백 자동화 구축 (Docker, EKS, Nginx Ingress, GitHub Actions)
- Prometheus + Grafana 기반 실시간 모니터링 구축

**시큐리티 & OAuth & 쿠키 관리**:
- OAuth2 인증 시스템 구현
- Redis를 이용한 리프레시 토큰 블랙리스트 관리
- Nginx와 Lua 스크립트를 활용한 쿠키 암호화 및 보안 강화

### 아키텍쳐
  **AWS 서버 구성**
  ![compact_eks-based_aws_architecture](https://github.com/user-attachments/assets/cfe6d847-699a-45c2-8751-2489874fd60c)



  **배포 파이프라인**
  ![cd_with_github_actions_+_ecr_+_eks_+_argo_rollouts_+_eso](https://github.com/user-attachments/assets/ee4e1714-9e3f-4b0f-a575-bbdb3d646fed)

  
🔗 [프로젝트 링크](https://github.com/WHERE-ARE-YOU-GOING-DAENG-DAENG/WHERE_ARE_YOU_GOING_DAENG_DAENG_-)  
## Naviya
Naviya는 U+ 개발자 부트캠프의 팀 프로젝트 과제인 **개인 맞춤형 서비스** 와 더불어, **매일 오후 1시 정각부터 10분간, 분당 10만 건**의 대규모 트래픽을 안정적으로 처리해야 하는 도전적인 요구사항을 해결하기 위해 시작되었습니다. 사용자의 MBTI 성향과 독서 취향을 분석하여 맞춤형 도서를 추천하는 핵심 기능과 함께, 이 대규모 동시 요청이 발생하는 선착순 응모 이벤트를 안정적으로 처리하는 것을 기술적 목표로 삼았습니다.
단순한 추천 시스템을 넘어, 예측 불가능한 대규모 트래픽을 안정적으로 처리하고 비용을 최적화하는 현대적인 클라우드 네이티브 아키텍처를 설계하고 구현하는 데 중점을 두었습니다.

**기간**: 2024.10 ~ 2025.11


### 주요 기여
**동적 가중치 기반 추천 시스템 구현**:
  - 사용자의 MBTI, 피드백 등을 실시간으로 반영하는 동적 가중치 조정법을 적용하여 개인화 추천 시스템을 구축

**Redis를 이용한 동시성 제어 및 비동기 처리**:
 - 좋아요/싫어요 등 빈번한 쓰기 요청을 Redis 기반 큐로 비동기 처리하여 DB 경합 및 데드락을 방지하고, 응답 속도를 약 **97.5%** 단축

**서버리스 아키텍처 도입으로 비용 절감**:
- 트래픽 집중 구간을 Lambda 기반 서버리스 구조로 전환하여 EC2 증설 대비 **47%(월 36만원)이상 비용 절감**

**다중 캐싱 전략으로 DB 부하 99.99% 이상 감소**
- Redis와 CloudFront를 활용한 이중 캐싱 구조로, 읽기·쓰기 부하를 효과적으로 분산 처리
   - Redis (쓰기 캐싱)
     - 10분간 100만 건의 응모 요청을 DB 대신 Redis에 임시 저장 후, 당첨자 100명만 DB에 기록 → 쓰기 부하 **99.99% 감소**
  - CloudFront (읽기 캐싱)
    - 정적 페이지 및 당첨자 결과(JSON)를 CloudFront에서 캐싱하여 수십만 건의 요청을 서버와 DB 없이 처리 → 읽기 부하 **100% 차단**
  
**terraform 기반 인프라 자동화 (IaC)**:
- AWS 인프라 전체를 코드로 관리, 인프라의 재현성과 변경 관리의 효율성을 확보

## 🛠️ 기술 스택 

### Cloud & Infrastructure
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-%237B42BC.svg?style=for-the-badge&logo=terraform&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)
![Amazon RDS](https://img.shields.io/badge/Amazon%20RDS-527FFF?style=for-the-badge&logo=amazonrds&logoColor=white)
![Amazon S3](https://img.shields.io/badge/Amazon%20S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white)
![Amazon ElastiCache](https://img.shields.io/badge/Amazon%20ElastiCache-FF9900?style=for-the-badge&logo=amazonelasticache&logoColor=white)
### Containerization & Orchestration
![Docker](https://img.shields.io/badge/Docker-%232496ED.svg?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-%23326CE5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![Amazon EKS](https://img.shields.io/badge/Amazon%20EKS-FF9900?style=for-the-badge&logo=amazon-eks&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-%230F1689.svg?style=for-the-badge&logo=helm&logoColor=white)
![Argo Rollouts](https://img.shields.io/badge/Argo%20Rollouts-0075E8?style=for-the-badge&logo=argo&logoColor=white) 
### Backend & Programming Languages
![Java](https://img.shields.io/badge/Java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-%236DB33F.svg?style=for-the-badge&logo=spring-boot&logoColor=white)
![Python](https://img.shields.io/badge/Python-%233776AB.svg?style=for-the-badge&logo=python&logoColor=white)
![Lua](https://img.shields.io/badge/Lua-%232C2D72.svg?style=for-the-badge&logo=lua&logoColor=white)
![C++](https://img.shields.io/badge/C++-%2300599C.svg?style=for-the-badge&logo=cplusplus&logoColor=white)
### Databases & Caching
![MySQL](https://img.shields.io/badge/MySQL-%234479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-%23DC382D.svg?style=for-the-badge&logo=redis&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-%2347A248.svg?style=for-the-badge&logo=mongodb&logoColor=white)

### CI/CD & DevOps Tools
![GitHub](https://img.shields.io/badge/GitHub-%23181717.svg?style=for-the-badge&logo=github&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-%232088FF.svg?style=for-the-badge&logo=github-actions&logoColor=white)

### Monitoring
![Prometheus](https://img.shields.io/badge/Prometheus-%23E6522C.svg?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-%23F46800.svg?style=for-the-badge&logo=grafana&logoColor=white)

### Data Science / ML (Mentioned in Activities)
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=tensorflow&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%2311557c.svg?style=for-the-badge&logo=matplotlib&logoColor=white)

## 🏆 백준 프로필
[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=sh5017)](https://solved.ac/sh5017/)


## 💬 연락처
- **이메일**: [lixxce5017@gmail.com](lixxce5017@gmail.com)
--
