# Google Cloud ACE 자격증 10일 완성 (상세 버전)

## 1일차: GCP 기본 구조 & IAM

### ✅ 1. GCP 리소스 계층 구조

- 조직(Organization) > 폴더(Folder) > 프로젝트(Project) > 리소스
- 리소스는 반드시 프로젝트 안에 있어야 하며, IAM 정책은 상속된다.

### ✅ 2. IAM 기본 개념

- IAM = 사용자의 권한을 제어하는 시스템
- 역할(Role) 부여 대상: 사용자 / 그룹 / 서비스 계정
- 역할 유형:
  - 기본 역할: Owner, Editor, Viewer
  - 사전 정의 역할: 예) roles/compute.instanceAdmin
  - 사용자 정의 역할: 필요한 권한만 조합

### ✅ 3. 서비스 계정

- VM이나 Cloud Function이 GCP API를 사용할 수 있게 해주는 비인간 사용자
- 키(JSON) 발급, 역할 부여, 키 노출 시 보안 사고 주의

### 🧠 실전 문제 예시

- Q: 특정 사용자가 VM을 만들 수 있도록 권한 부여 → A: compute.instanceAdmin
- Q: 서비스 계정이 Cloud Storage에 접근하려면? → A: roles/storage.objectViewer 권한 필요

---

## 2일차: Compute Engine

### ✅ 핵심 개념 요약

- VM 인스턴스는 여러 머신 타입 제공 (e2, n2 등), 커스텀 가능
- 디스크: 부트 디스크(OS), 추가 디스크(Persistent Disk)
- 인스턴스 템플릿 + MIG로 자동 복구, 자동 확장 가능
- Preemptible VM: 일시적 사용, 24시간 유지 불가, 매우 저렴

### 🧠 실전 문제 예시

- Q: VM이 실패 시 자동 복구되도록 설정하려면? → A: Managed Instance Group + Auto-healing
- Q: 동일한 설정으로 100개의 VM을 생성하려면? → A: Instance Template + MIG

---

## 3일차: VPC, Firewall, NAT

### ✅ VPC 개념

- VPC는 전역 리소스, 서브넷은 리전 단위
- Default VPC: 기본 제공, 방화벽 규칙 포함
- Custom VPC: 서브넷/방화벽 수동 설정, 실무에 적합

### ✅ 방화벽 규칙

- 방향(Ingress/Egress), 우선순위(Priority), 태그 기반(Target Tags)
- 기본은 모두 차단, 명시적으로 허용해야 함

### ✅ Cloud NAT

- 내부 IP만 있는 VM이 인터넷에 아웃바운드 연결 가능하게 함
- 외부에서 해당 VM으로 접근은 불가

### 🧠 실전 문제 예시

- Q: VM은 인터넷으로 나가야 하지만 외부 접근은 차단해야 함 → A: 내부 IP + Cloud NAT

---

## 4일차: GKE

### ✅ 핵심 구성

- 클러스터 → 노드풀(Node Pool) → 노드(VM)
- 파드(Pod) = 컨테이너 집합, 서비스(Service) = 파드 그룹에 접근
- Ingress: 외부에서 들어오는 HTTP 트래픽 처리

### ✅ 보안/관리 기능

- Auto-upgrade, Auto-repair, Node auto-scaling
- Workload Identity: GCP IAM 연동 보안 방식

### 🧠 실전 문제 예시

- Q: HTTP 요청을 외부에서 GKE로 보내고 싶다면? → A: Ingress 설정
- Q: Pod별로 권한 제어 필요 → A: RBAC

---

## 5일차: Cloud Storage

### ✅ 구조 및 클래스

- 객체 스토리지: Bucket → Object 구조
- 클래스: Standard / Nearline / Coldline / Archive
- Nearline = 30일 1회 이하, Coldline = 90일 1회 이하, Archive = 1년 이하

### ✅ 기능

- 버전 관리(Versioning), 수명주기(Lifecycle), Signed URL
- IAM 또는 ACL을 통한 권한 설정

### 🧠 실전 문제 예시

- Q: 월 1회 접근하는 백업 저장용 → A: Coldline
- Q: 외부 사용자가 파일을 일정 시간만 다운로드 가능하게 → A: Signed URL

---

## 6일차: Cloud SQL / Firestore / Bigtable

### ✅ Cloud SQL

- 관리형 RDBMS: MySQL, PostgreSQL, SQL Server
- 자동 백업, PITR(시점 복원), SSL 연결

### ✅ Firestore

- 문서 기반 NoSQL, 모바일 앱 실시간 동기화에 적합
- 구조: 컬렉션 → 문서 → 필드
- 보안 규칙 제공

### ✅ Bigtable

- 초고속 시계열 데이터 저장용 NoSQL
- HBase API 호환, 수평 확장성 우수

### 🧠 실전 문제 예시

- Q: 실시간 게임 데이터 저장 → A: Firestore
- Q: 로그 수집 및 시계열 분석 → A: Bigtable

---

## 7일차: App Engine / Cloud Functions / Cloud Run

### ✅ 비교

| 항목      | App Engine | Cloud Functions | Cloud Run |
| --------- | ---------- | --------------- | --------- |
| 배포 단위 | 전체 앱    | 함수 단위       | 컨테이너  |
| 트리거    | HTTP       | 이벤트 기반     | HTTP      |
| 유연성    | 낮음       | 중간            | 높음      |
| 사용 예   | 웹앱       | 트리거 작업     | REST API  |

### 🧠 실전 문제 예시

- Q: GCS 업로드 시 백그라운드 작업 수행 → A: Cloud Functions
- Q: 언어 자유로운 서버리스 앱 → A: Cloud Run

---

## 8일차: 모니터링 & 로깅

### ✅ Monitoring

- Uptime Check: 외부에서 가용성 확인
- Alert Policy: 조건 만족 시 알림

### ✅ Logging

- 시스템 로그, 사용자 로그 수집
- 로그 기반 메트릭 → Alert 연동 가능
- 필터: severity="ERROR"

### 🧠 실전 문제 예시

- Q: 웹 서비스의 외부 상태 확인 + 알림 → A: Uptime Check + Alert

---

## 9일차: 배포 자동화

### ✅ gcloud CLI

- VM 생성, 버킷 생성, Cloud Run 배포 등 가능

### ✅ Deployment Manager

- GCP 전용 IaC 도구, YAML 기반 구성

### ✅ Terraform

- 멀티클라우드 지원, `.tf` 파일로 리소스 선언

### 🧠 실전 문제 예시

- Q: 코드로 인프라 재현하려면? → A: Terraform

---

## 10일차: 보안 / 비용 관리

### ✅ 보안

- IAM 역할 상속 구조
- 서비스 계정 키는 최소화하고 주기적 회전 필요
- Workload Identity 사용 권장

### ✅ 비용 관리

- Budget 설정 + 알림 채널
- Cloud Billing 보고서

### 🧠 실전 문제 예시

- Q: 예산 초과 시 경고 → A: Budget 설정
- Q: 외부 IP 제한 정책 → A: Organization Policy

---
