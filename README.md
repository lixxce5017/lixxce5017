##  프로젝트
#  댕댕어디가 

**댕댕어디가**는 반려동물과 함께 외출할 때의 불편함을 줄이고, 더 많은 활동을 즐길 수 있도록 돕는 서비스입니다. 웹사이트를 통해 반려견과 동반 가능한 장소를 쉽게 검색하고, 다양한 추천 기능을 통해 맞춤형 장소 정보를 제공합니다. 또한, 실시간 **땅따먹기 시스템**으로 사용자들에게 재미와 보상을 제공합니다!

**기간**: 2024.11 ~ 2025.1  
**Stack**: Spring Boot, Java, MySQL, ProxySQL,Redis, docker,AWS (ECS, RDS, S3), Pinpoint, GitHub Actions ,nginx,lua script

### 주요 기여

- **장소 추천 시스템 최적화**:
    - 위치 기반 정보와 사용자 선호도를 반영하는 추천 로직 설계
    - 시간복잡도를 고려한 최적화로 294.63ms에서 172.63ms로 약**41.42%**로 성능 상향
    - 레디스를 이용한 위치기반 캐싱 
- **CI/CD 파이프라인 구축 및 무중단 배포**:
  - github action을 이용한 cicd 파이프라인 구축
  - docker와 Nginx를 활용한 blue-green 무중단 배포 구현
- **시큐리티&OAuth & 쿠키 관리**:
  - OAuth2 인증 시스템을 구현
  - redis를 이용한 리프레시 토큰 블랙리스트 관리
  - Nginx와 Lua를 활용한 쿠키 암호화로 보안을 강화
- **보안성 및 트래픽을 고려한 AWS 서버 구성**
  - 리버스 프록시 서버 nginx로 보안성을 고려한 rate limits 및 connection limits 설정,
  - GoAccess를 통한 실시간 사용자 통계 분석,
  - Proxy SQL을 통한 RDS read/write 분산처리로 대규모 트래픽 및 고가용성을 고려한 서버 구성
- **리뷰 금칙어 로직**
  - 아호 코라식 알고리즘을 이용한 리뷰 금칙어 로직 설계 및 구현
- **DB 커넥션 풀 최적화**  
    - DB 커넥션 풀과 스레드 풀을 재설계하여 효율성 극대화  

🔗 [프로젝트 링크](https://github.com/WHERE-ARE-YOU-GOING-DAENG-DAENG/WHERE_ARE_YOU_GOING_DAENG_DAENG_-)  
🔗 [블로그 링크:반려동물 동반 시설 플랫폼 유저 맞춤 장소추천 구현](https://velog.io/@lixxce/%EB%8C%95%EB%8C%95%EC%96%B4%EB%94%94%EA%B0%80-%EB%B0%98%EB%A0%A4%EB%8F%99%EB%AC%BC-%EB%8F%99%EB%B0%98-%EC%8B%9C%EC%84%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9C%A0%EC%A0%80-%EB%A7%9E%EC%B6%A4-%EC%9E%A5%EC%86%8C%EC%B6%94%EC%B2%9C-%EA%B5%AC%ED%98%84)
[블로그 링크:CI/CD 파이프라인 구축 및 무중단 배포](https://velog.io/@lixxce/%EB%8C%95%EB%8C%95%EC%96%B4%EB%94%94%EA%B0%80%EA%B3%A0%EA%B0%80%EC%9A%A9%EC%84%B1%EA%B3%BC-%EB%B3%B4%EC%95%88%EC%9D%84-%EA%B3%A0%EB%A0%A4%ED%95%9C-AWS-%EC%84%9C%EB%B2%84-%EC%84%A4%EA%B3%84-%EB%B0%8F-%EB%AC%B4%EC%A4%91%EB%8B%A8-%EB%B0%B0%ED%8F%AC-%EC%A0%84%EB%9E%B5)


## 🏆 백준 프로필
[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=sh5017)](https://solved.ac/sh5017/)


## 💬 연락처
- **이메일**: [lixxce5017@gmail.com](lixxce5017@gmail.com)
--
