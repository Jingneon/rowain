# 사내 프로젝트용 로봇팔 제어 SW 개발

> **기간**: 2024.11.12 ~ 2025.01.06  
> **역할**: UI/UX 설계 · 프론트엔드 개발

<img width="7000" alt="rowain_blur_ver 1" src="https://github.com/user-attachments/assets/746524b3-22f8-4e38-953f-dd11a7c88dab" />


## 프로젝트 개요
Flutter 기반의 프론트엔드 환경에서 **6자유도 로봇팔 제어 UI**를 구축한 사내용 소프트웨어입니다.  
사용자 직관성을 높이기 위해 3D 모델 기반의 인터페이스를 적용하고, **UDP 통신**을 통한 실시간 제어 및 상태 모니터링 기능을 구현했습니다.



## 기술 스택
- **Frontend**: Flutter, Dart  
- **State Management**: Cubit  
- **Network**: UDP, Datagram  
- **UI/UX**: Responsive Design, 3D Interaction



## 주요 기능

### 1. Usecase & Cubit 기반 상태 관리
- 버튼 이벤트와 제어 요청을 **상태(State)**로 구조화
- `Cubit`과 `BlocBuilder`를 활용한 UI-상태 동기화
- 유지보수와 확장성을 고려한 코드 모듈화

### 2. 네트워크 통신 모듈
- UDP 기반 제어 패킷 송수신
- 연결 상태(Ping) 실시간 모니터링

### 3. 직관적인 UI/UX
- 창 크기에 따라 **자동 리사이징**
- 3D 모델 기반 직관적인 버튼 배치
- 비상 정지(EMO) · 전원 토글 버튼 즉시 반응

### 4. 학습 모드 & 로그 관리
- 최대 **500건** 동작 로그 저장
- 기록된 동작 재실행 가능
- 학습 모드 실행/중지 및 UI 반영

### 5. 센서 데이터 모니터링
- UDP 통신 기반 실시간 센서 데이터 표시
- 데이터 스트림 UI 연동



## 개발 과정 & 고려사항
- **UI/UX 최적화**: 초기 단순 버튼 UI → 3D 모델 기반 인터페이스로 개선
- **성능 최적화**: 불필요한 상태 변경 최소화, 렌더링 최적화
- **통신 안정성 강화**: UDP 패킷 구조 개선, 연결 상태 확인 로직 추가
- **안전성**: 비상 정지 및 전원 토글의 즉각 반응 구조 설계



## 실행 예시

### 네트워크 상태 모니터링 & 센서 데이터 모니터링
<img width="246" alt="rowain_blur_ver_11111" src="https://github.com/user-attachments/assets/28c49fe2-9c1f-4002-9e9e-634189cd641c" />

- **Ping**을 활용해 네트워크 연결 상태를 실시간으로 확인
- **UDP 통신**으로 센서 데이터 수집
- 각 데이터는 **UseCase**와 **Cubit**으로 개별 Stream 처리
- 실시간 데이터 UI 반영, 데이터 변경 시 자동 업데이트
- 불필요한 UI 리빌드는 Cubit으로 상태관리


### 로봇 제어 버튼 UI
<img src="https://github.com/user-attachments/assets/e0909539-a86b-4bcb-8811-91392da643a7" width="600">

- 직관적인 버튼 배치로 제어 효율 향상
- 버튼 클릭 시 즉시 반응
- 기능별 색상 구분 및 아이콘 표시



### 학습 모드
<img src="https://github.com/user-attachments/assets/f4e3144a-0258-43d1-8212-bcdea5839d40" width="400">

- 최대 **500건** 동작 기록 저장
- 기록된 동작 재실행 가능
- 실행/중지 시 UI 상태 변경



### 비상 정지(EMO) / 전원 토글
<img src="https://github.com/user-attachments/assets/b8bc8dc2-1cf6-4309-9a41-bb04e9d34e20" width="400">

- 비상 정지 시 즉각 모든 동작 중단
- 전원 토글 버튼으로 장비 전원 관리
- 상태 변경 시 UI와 네트워크 패킷 동기화

### 리사이징 가능한 UI
<img src="https://github.com/user-attachments/assets/f6cbe7b0-fddf-4b65-9d16-c34a1edb5176" width="600">

- 16:9 비율 유지
- 위젯 폰트 깨짐 x (보안상 blur 처리)


## 라이선스
해당 프로젝트는 사내용으로 개발되었으며, 외부 배포가 제한됩니다.
