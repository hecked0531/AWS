## 클라우딩 컴퓨팅
<details>
<summary>OPEN/CLOSE</summary>

### 배포 모델
 1. 클라우드 기반 배포
 2. 온프레미스 배포
 3. 하이브리드 배포

### 클라우드 컴퓨팅 이점
 1. 선행 비용을 가변 비용으로 대체
 2. 데이터 센터 운영 및 유지 관리에 비용 투자 불필요
 3. 용량 추정 불필요
 4. 규모의 경제로 얻게 되는 이점
 5. 속도 및 민첩성 향상
 6. 몇 분 만에 전 세계에 배포
</details>

## EC2 (Elastic Cloud Computer)
<details>
<summary>OPEN/CLOSE</summary>

### EC2 인스턴스 유형
 1. 범용
 2. 컴퓨팅 최적화
 3. 메모리 최적화
 4. 엑셀레이티드 컴퓨팅
 5. 스토리지 최적화

### EC2 요금
 1. 온디맨드
 2. Amazon EC2 Savings Plans
 3. 예약 인스턴스
 4. 스팟 인스턴스
 5. 전용 호스트

### EC2 확장
 1. Amazon EC2 Auto Scaling
 2. Elastic Load Balancing
 3. Amazon Simple Notification Service (SNS)
 4. Amazon Simple Queue Service (SQS)
 5. 서버리스 컴퓨팅 (AWS Lambda)
 6. 컨테이너
    - Amazon Elastic Container Service (ESC)
    - Amazon Elastic Kubernetes Service (EKS)
    + AWS Fargate
</details>

## AWS 글로벌 인프라
<details>
<summary>OPEN/CLOSE</summary>

### 리전 선택
 1. 데이터 거버넌스 및 법적 요구 사항 준수
 2. 고객과의 근접성
 3. 리전 내에서 사용 가능한 서비스
 4. 요금
### 가용 영역
### 엣지 로케이션

### Point
 1. 리전은 지리적으로 격리된 영역
 2. 리전은 두 개 이상의 가용 영역으로 구성됩니다.
 3. 엣지 로케이션은 Amazon CloudFront를 실행함

### AWS Outposts
 - AWS 인프라 및 서비스를 온프레미스 데이터 센터로 확장
</details>

## AWS 리소스를 프로비저닝 하는 방법
<details>
<summary>OPEN/CLOSE</summary>

### AWS 서비스와의 상호작용
 1. AWS Management Console
    - 테스트 환경
    - AWS 청구서 보기
    - 모니터링 보기
    - 기술과 무관한 리소스를 사용한 작업
 2. AWS 명령줄 인터페이스 (CLI)
 3. AWS 소프트웨어 개발 키트 (SDK)
 4. 기타 다양한 도구

### AWS Elastic Beantalk (code)
 - EC2
 - 용량 조정, 로드 밸런싱, 자동 조정, 애플리케이션 상태 모니터링등을 배포

### AWS CloudFormation (yaml, xml...)
 - EC2, 스토리지, 데이터베이스, 분석, 기계학습
</details>

## AWS 네트워킹
<details>
<summary>OPEN/CLOSE</summary>

### Amazon Virtual Private Cloud (VPC)
 1. Virtual Internet Gateway (IGW)
 2. Virtual Private Gateway -> Virtual Private Network (VPN)
 3. AWS Direct Connect

### 서브넷 및 네트워크 엑세스 제어 목록
 1. 네트워크 강화
 2. 애플리케이션 보안
 3. 사용자 자격 증명
 4. 인증 및 권한 부여
 5. 분산 서비스 거부 방지
 6. 데이터 무결성
 7. 암호화

### 네트워크 억세스 컨트롤 (NACL)
 - 리스트에 있는 것만 OK
 - IN OUT 둘다 검사
 - 상태 비저장 (언제든지 검사)

### 보안 그룹
 - 아웃 바운드는 모두 OK
 - 상태 저장 (저장된 패킷은 따로 검사 안함)

### 서브넷
 - 퍼블릭 서브넷
 - 프라이빗 서브넷

### 글로벌 네트워킹
 - Route 53 (DNS)
    - 지연 시간 기반 라우팅
    - 지리적 위치 DNS
    - 지리 근접 라우팅
    - 가중치 기반 라운드 로빈
 - Amazon CloudFront
    - Content Delivery Network (CDN)

</details>

## 스토리지 및 데이터베이스
<details>
<summary>OPEN/CLOSE</summary>

### 인스턴스 스토어 및 Amazon Elastic Block Store (EBS)
 - 블록 수준 스토리지 (하드 드라이브)
 - 인스턴스 스토리지 볼륨 (휘발성) 
 - EBS (비휘발성)
    - 크기 유형 구성
    - 스냅샷 (증분 백업)

### Amazon Simple Storage Service (Amazon S3)
 - 객체로 저장, 버킷, 5TB, 버전 관리
 - Amazon S3 스토리지 클래스 (검색 빈도, 가용성)
    - S3 Standard
    - S3 Standard-Infrequent Access (S3 standard-IA)
    - S3 One Zone-Infrequent Acess (S3 One Zone-IA)
    - S3 Interlligent-Tiering
    - S3 Glacier
    - S3 Glacier DDeep Archive

### Amazon EBS vs Amazon S3
 - 편집을 자주 하면 EBS (블록 방식이라서)
 - 모든 데이타를 처리를 한다면 S3

### Amaozn Elastic File System (Amazon EFS)
 - 관리형 파일 시스템
 - 여러 인스턴스가 동시에 접속 가능

### Amazon EBS vs Amazon EFS
 - EBS
    - EC2 인스턴스에 볼륨 연결
    - 가용 영역 수준 리소스
    - EC2 인스턴스를 연결하려면 동일한 가용영역에 있어야 함
    - 볼륨이 자동으로 확장되지 않음
 - EFS
    - 여러 인스턴스 동시 읽기 및 스기
    - Linux 파일 시스템
    - 리전 리소스
    - 자동 확장

### Amazon Relational Database Service (Amazon RDS)
 - 자동 패치, 백업, 이중화, 장애 조치, 재해 복구

### Amazon Aurora
 - MySQL, PostgreSQL
 - 상용데이터베이스 비용의 1/10
 - 데이터 복제, 지속적 백업, 특정 시점으로 복구

### Amazon DynamoDB (서버리스 데이터베이스)
 - 비관계형 데이터 베이스 NoSQL (키 - 값)
 - 특수 목적 설계
 - 밀리단위 응답
 - 완전 관리형
 - 높은 확장성

### Amazon RDS vs Amazon DynamoDB
 - 복잡하지 않는 일획적인 테이블 구성인 경우 전부 Dynamo

### Amazon Redshift
 - 빅 데이터 분석에 사용할 수 있는 데이터 웨어하우징 서비스
 - 확장성이 뛰어나다

### AWS Database Migration Service

### Amazon DocumentDB (MongoDB)
### Amaozn Neptune (그래프 데이터 베이스 서비스)
### Amazon Managed Blockchain
### Amazon Quantum Ledger Database (QLDB)
### Amazon ElasticCache (redis, Memcached)
### Amazon DynamoDB Accelerator 
</details>
