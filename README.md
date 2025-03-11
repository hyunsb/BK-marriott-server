# BK Marriott <img width="100" alt="image" src="https://github.com/user-attachments/assets/9c9a13a4-3c97-4122-8ac4-94d105951a2a" align=left >


대용량 트래픽 처리와 동시성을 보장하는 대규모 호텔 체인의 예약 시스템

<br/>

## 📍 프로젝트 목표

> 개발 기간 : 2024.12.23 ~ 2025.01.27

- 5,000개 호텔과 100만 개 객실을 보유한 대규모 호텔 체인의 예약 시스템 구축
- 특정 기간 프로모션을 통해 선착순 쿠폰 발급, 객실 조회, 예약 및 결제 과정을 원활하게 처리할 수 있는 서비스 제공
- 서버의 안정성을 위해 트래픽 처리량을 모니터링하여 장애 예방
- 선착순 쿠폰 발급 및 호텔 예약 시 동시성 문제에 대한 고민 및 해결


<br/>

## ⚒️ 사용기술 및 개발환경

**Development**

<p>
<img src="https://img.shields.io/badge/JDK 17-E38836?style=flat-square&logo=openJdk&logoColor=white">
<img src="https://img.shields.io/badge/SpringBoot 3.4-6DB33F?style=flat-square&logo=springboot&logoColor=white"/>
<img src="https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white"/>
<br />
<img src="https://img.shields.io/badge/JPA-6DB33F?style=flat-square&logo=hibernate&logoColor=white"/> 
<img src="https://img.shields.io/badge/SpringDataJPA-6DB33F?style=flat-square&logo=spring&logoColor=white"/>
<img src="https://img.shields.io/badge/QueryDSL-6DB33F?style=flat-square&logo=spring&logoColor=white"/>
<img src="https://img.shields.io/badge/Spring Batch-6DB33F?style=flat-square&logo=spring&logoColor=white"/>
<img src="https://img.shields.io/badge/OpenFeign-6DB33F?style=flat-square&logo=spring&logoColor=white"/>

</p>

**Database**

<p>
<img src="https://img.shields.io/badge/MySQL 8-08668E?style=flat-square&logo=mysql&logoColor=white">
<img src="https://img.shields.io/badge/Redis-FF0000?style=flat-square&logo=redis&logoColor=white">
<img src="https://img.shields.io/badge/H2 Database-004088?style=flat-square&logo=h2&logoColor=white"/>
</p>

**Server**

<p>
<img src="https://img.shields.io/badge/Eureka-6DB33F?style=flat-square&logo=spring&logoColor=white"/>
<img src="https://img.shields.io/badge/SpringGateway-6DB33F?style=flat-square&logo=spring&logoColor=white"/>
<img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white"/>
<img src="https://img.shields.io/badge/Resilience4j-000000?style=flat-square&logo=&logoColor=white"/>
</p>

**Test**

<p>
<img src="https://img.shields.io/badge/JUnit 5-25A162?style=flat-square&logo=junit5&logoColor=white"/>
<img src="https://img.shields.io/badge/JaCoCo-B7178C?style=flat-square&logo=&logoColor=white"/>
<img src="https://img.shields.io/badge/Mockito-00B4AB?style=flat-square&logo=&logoColor=white"/>
<img src="https://img.shields.io/badge/SonarQube-4E9BCD?style=flat-square&logo=sonarqube&logoColor=white"/>
<img src="https://img.shields.io/badge/JMeter-D22128?style=flat-square&logo=apachejmeter&logoColor=white"/>
<p />

**Monitoring**

<p>
<img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white"/>
<img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white"/>
<img src="https://img.shields.io/badge/Zipkin-FE5F50?style=flat-square&logo=&logoColor=white"/>
</p>

**CI/CD**

<p>
<img src="https://img.shields.io/badge/GitHub Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/Docker Compose-2496ED?style=flat-square&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/AWS EC2-FF9900?style=flat-square&logo=amazonec2&logoColor=white"/>
<img src="https://img.shields.io/badge/AWS RDS-527FFF?style=flat-square&logo=amazonrds&logoColor=white"/>
</p>

<br/><br/>

## 🌐 아키텍처 설계도
<img width="1518" alt="image" src="https://github.com/user-attachments/assets/adb32952-8bcb-4677-9a54-a30b57d2eead" />

<br/>

## 🧩 서비스 구성

### 📢 Promotion Service

> * 프로모션 등록
> * 선착순 쿠폰 발급

### 🎟 Coupon Service

> * 쿠폰 발급 및 조회
> * 쿠폰 유효성 검증

### 🏨 Hotel Service

> * 호텔 정보 등록 및 관리
> * 호텔 검색

### 📅 Reservation Service

> * 예약 가능한 객실 정보 조회
> * 객실 예약 및 취소 처리
> * 예약 상태 확인 및 변경

### 💰 Charge Service

> * 3개월치 호텔 객실 별 요금 데이터 관리
> * 호텔 객실 별 요금 조회

### 💳 Payment Service

> * 결제 및 환불 처리
> * 결제 이력 조회

### 🛡 Gateway Service

> * JWT를 이용한 인증/인가 처리
> * 로드밸런싱 및 서비스 라우팅

### 🔑 Auth Service

> * 로그인 및 회원가입
> * JWT 토큰 발급
> * 사용자 관리

<br/>

## ⚙️ 기술적 의사 결정

### [✨ DDD와 애플리케이션 아키텍처 설계](https://www.notion.so/teamsparta/DDD-164ff65aa200432ab8f8d011876a500a?pvs=4) <br />
### [✨ Jacoco와 SonarQube 적용](https://www.notion.so/teamsparta/JaCoCo-SonarQube-13d0075e532d42c3a49d6d775ecf9d6d?pvs=4) <br />
### [✨ 선착순 쿠폰 발급 동시성 처리 방법](https://www.notion.so/teamsparta/db834834d52f4e699eaef609b8fd0867?pvs=4) <br />

<br/>

## 🔍 트러블 슈팅

### [🚀 선착순 쿠폰 발급 서비스 설계기](https://www.notion.so/teamsparta/84351178213c4b718dd564c4685684f4?pvs=4) <br />
### [🚀 도메인 로직과 이벤트 발행의 원자성 보장하기](https://www.notion.so/teamsparta/1ba43d212aaf4f6e86733795327a7cc8?pvs=4) <br />
### [🚀 조건부 속성 문제 해결기 (DDD + Factory Method)](https://www.notion.so/teamsparta/DDD-Factory-Method-0b993e2e7aa6469aadc1de9ca3f1bdc8?pvs=4) <br />

<br/><br/>

## 🗂 ERD

<img width="1518" alt="image" src="https://github.com/user-attachments/assets/20ecb364-83c7-4242-b999-3bbeb35f7069" />

<br/>

### 🧑🏻‍💻 개발 인원 및 역할

|<img src="https://avatars.githubusercontent.com/u/96504592?v=4" width="100px;" alt=""/><br /><sub><b>[정현수](https://github.com/hyunsb)</b></sub></a><br />|<img src="https://avatars.githubusercontent.com/u/158719845?v=4" width="100px;" alt=""/><br /><sub><b>[연이현](https://github.com/DISNOTACAT)</b></sub></a><br />|<img src="https://avatars.githubusercontent.com/u/119548924?v=4" width="100px;" alt=""/><br /><sub><b>[권현준](https://github.com/Kwonhyunjun)</b></sub></a><br />|<img src="https://avatars.githubusercontent.com/u/48899055?v=4" width="100px;" alt=""/><br /><sub><b>[이주희](https://github.com/zoohee)</b></sub></a><br />|<img src="https://avatars.githubusercontent.com/u/68426501?v=4" width="100px;" alt=""/><br /><sub><b>[연제민](https://github.com/yjm07)</b></sub></a><br />|
|:---:|:---:|:---:|:---:|:---:|
| ▶ 아키텍처 설계 <br> ▶ 프로모션, 쿠폰 서비스 <br> ▶ 게이트웨이, 유저 서비스 <br> ▶ JaCoCo 및 SonarQube | ▶ 예약 서비스 <br> ▶ 결제 서비스 | ▶ 예약 서비스 <br> ▶ 호텔 서비스 |  ▶ 쿠폰 서비스 <br> ▶ 인프라 구축 및 CI/CD | ▶ 예약 서비스 <br> ▶ 객실 요금 서비스 |
<br/>
