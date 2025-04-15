##  프로젝트
#  댕댕어디가 

**댕댕어디가**는 반려동물과 함께 외출할 때의 불편함을 줄이고, 더 많은 활동을 즐길 수 있도록 돕는 서비스입니다. 웹사이트를 통해 반려견과 동반 가능한 장소를 쉽게 검색하고, 다양한 추천 기능을 통해 맞춤형 장소 정보를 제공합니다. 또한, 실시간 **땅따먹기 시스템**으로 사용자들에게 재미와 보상을 제공합니다!

**기간**: 2024.11 ~ 2025.3
**Stack**: Spring Boot, Java, MySQL, ProxySQL,Redis, docker,Terrafrom,AWS (EKS,ECS, RDS, S3), GitHub Actions ,nginx,lua script

### 주요 기여
**사용자 맞춤 장소 추천 시스템 최적화**

- 위치 기반 정보와 사용자 선호도를 반영하는 추천 로직 설계
- 성능 최적화: 294.63ms에서 172.63ms로 약 **41.42%** 성능 개선
- Redis를 활용한 위치 기반 캐싱

**AWS 서버 구성, 고가용성 및 인프라 자동화(IaC):**

- Terraform을 활용한 AWS 인프라(VPC, EKS, ALB, RDS, ElastiCache 등) 코드 기반 구축 및 관리
- S3/DynamoDB 기반 Terraform 원격 상태 관리 및 잠금 구성
- GitHub Actions 기반 Terraform CI/CD 파이프라인 구축 (PR 시 Plan 검증, 환경별 Apply
- GitHub Actions를 활용한 애플리케이션 CI/CD 파이프라인 구축
- 컨테이너 배포 환경의 Amazon EKS 전환 및 CI/CD 기반 카나리 무중단 배포 및 롤백 자동화 구축 (Docker, EKS, Nginx Ingress, GitHub Actions)
- 리버스 프록시 서버 Nginx로 보안성을 고려한 rate limits 및 connection limits 설정
- Proxy SQL을 통한 RDS read/write 분산처리로 대규모 트래픽 및 고가용성 고려
- Prometheus + Grafana 기반 실시간 모니터링 구축

**시큐리티 & OAuth & 쿠키 관리**:
- OAuth2 인증 시스템 구현
- Redis를 이용한 리프레시 토큰 블랙리스트 관리
- Nginx와 Lua 스크립트를 활용한 쿠키 암호화 및 보안 강화

🔗 [프로젝트 링크](https://github.com/WHERE-ARE-YOU-GOING-DAENG-DAENG/WHERE_ARE_YOU_GOING_DAENG_DAENG_-)  

## 🏆 백준 프로필
[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=sh5017)](https://solved.ac/sh5017/)


## 💬 연락처
- **이메일**: [lixxce5017@gmail.com](lixxce5017@gmail.com)
--
