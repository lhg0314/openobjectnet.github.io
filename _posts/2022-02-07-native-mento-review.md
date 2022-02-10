---
title: "오픈오브젝트 멘토링 수행(네이티브개발자)"
last_modified_at: 2022-02-07T18:01:04-04:00
categories: 
  - Mentoring
tags:
  - Mentoring
toc: true
toc_label: "시기별"
author: 네이티브 개발자   
---

## 실습 개발환경  
- iOS : 
  - XCode 최신버전
  - Swift(주력)
  - Objective-C (2가지 언어 혼합 사용 환경)
- AOS : 
  - Android Studio 최신버전
  - Kotlin(주력)
  - Java (2가지 언어 혼합 사용 환경)
- API : 
  - PMS(오픈오브젝트) 개발서버 (http://dpms.openobject.net:4003/api/..)
  - Google Open API
- 웹페이지 
  - PMS (오픈오브젝트) 개발서버 (http://dpms.openobject.net:4003)
- Firebase
  - push, dynamic link, analytics
- 소스관리 : 
  - Git (http://git.openobject.net:8880/) personal project 생성, 멤버 초대
  - merge시 마다 PR(MR)요청하여 각 파트 멤버들에게 리뷰 요청

## 기간
- 언어 습득 및 앱제작 1,2,3,4 번 기능을 총 8~10주간 실습 (진행속도에 따라 단축)
- 앱제작 기능별 내용을 정리하여 인수인계 형식으로 각 파트 동료들과 리뷰 진행

|   항목                  |   상세                          |   1주  |   2주  |   3주  |   4주  |   5주  |   6주  |   7주  |   8주  |   9주  |   10주  |
|----------------|-----------------------|------|------|------|------|------|------|------|------|------|------|
|   개발환경 세팅  |   IDE, SDK 설치, Git 생성   |   O    |        |        |        |        |        |        |        |        |         |
|   언어 습득        |   Swift, Kotlin             |   O    |   O    |        |        |        |        |        |        |        |         |
|   앱제작-방리스트 화면  |   MVC, MVVM 패턴 조사       |        |        |   O    |        |        |        |        |        |        |         |
|                         |   파일 JSON fetch           |        |        |   O    |        |        |        |        |        |        |         |
|                         |   리스트 화면 구성          |        |        |   O    |        |        |        |        |        |        |         |
|                         |   필터링 , 소팅 기능        |        |        |        |   O    |        |        |        |        |        |         |
|                         |   페이징 기능               |        |        |        |   O    |        |        |        |        |        |         |
|   앱제작-책검색     |   통신모듈 작성             |        |        |        |        |   O    |        |        |        |        |         |
|                         |   구글 API 통신             |        |        |        |        |   O    |        |        |        |        |         |
|                         |   검색, 리스트 화면 구성    |        |        |        |        |        |   O    |        |        |        |         |
|                         |   상세화면 구성             |        |        |        |        |        |   O    |        |        |        |         |
|   앱제작-firebase활용   |   firebase앱등록            |        |        |        |        |        |        |   O    |        |        |         |
|                         |   앱내 SDK 적용             |        |        |        |        |        |        |   O    |        |        |         |
|                         |   푸시 기능                 |        |        |        |        |        |        |   O    |        |        |         |
|                         |   다이나믹 링크 기능        |        |        |        |        |        |        |        |   O    |        |         |
|                         |   애널리틱스 기능           |        |        |        |        |        |        |        |   O    |        |         |
|   앱제작-웹뷰연동       |   PMS 로그인 화면 구성      |        |        |        |        |        |        |        |        |   O    |         |
|                         |   PMS 로그인 API            |        |        |        |        |        |        |        |        |   O    |         |
|                         |   PMS 웹뷰 열기             |        |        |        |        |        |        |        |        |   O    |         |
|                         |   웹뷰 브릿지 환경 구성     |        |        |        |        |        |        |        |        |        |   O     |
|                         |   웹뷰 요청 기능 화면 구성  |        |        |        |        |        |        |        |        |        |   O     |
   
## 개발 언어 습득
- swift, kotlin에 익숙치 않은경우 언어 습득 부터 진행
- 해당 언어에 익숙하다면 앱 제작 실습 부터 진행
- 책 구입 혹은 온라인 강의 지원

## 앱 제작 실습

### 1. 방(Room) 리스트 화면
- MVVM 패턴을 조사하고 해당 방식으로 제작
- 주어진 파일에서 JSON 모델 fetch
- 이미지, 방 타입, 가격, 날짜 정보등을 전체 리스트 화면으로 표시
- 특정 데이타 타입별로 필터링된 리스트 표시하는 기능
- 높은 가격, 낮은 가격별로 소팅 하는 기능
- 리스트 전부를 한번에 표시하지 않고, 10개씩 데이타를 가져와서 표시 (paging 기능)

### 2. 책(Book) 검색 화면
- HTTP get, post 할수 있는 통신모듈 작성
- HTTP API 통해서 Json model fetch
- google book api 사용하여 책을 검색 조회
- 책 제목, 설명, 이미지등을 리스트 화면으로 표시
- 해당 책을 선택했을때 해당 책 상세 화면 표시

### 3. Firebase 활용
 - Google Firebase 앱등록
 - push 발송
  - FCM 등록 
  - 앱 라우팅정보, 기타정보 포함
  - 콘솔에서 테스트 발송
  - 앱에서 푸시 수신 후, 라우팅 정보를 파악하여 앱 화면 이동
   - 앱애서 푸시 수신 후, 수신된 정보를 앱에 저장하여 푸시 메시지함 제작
 - Dynamic 링크
  - 앱 라우팅정보를 포함하여 링크 제작
  - 링크 클릭시 앱 연결 및 라우팅 정보를 파악하여 앱 화면 이동
 - Analytics
  - 모든 버튼 동작시 애널리틱스 전송

### 4. 하이브리드 웹뷰 
- ID, PW를 입력받는 로그인 화면 제작하고, PMS 로그인 API를 이용하여 로그인 
- 로그인 이후 웹뷰에 로그인 정보를 세팅하여 PMS 웹페이지 열기
- PMS 웹페이지와 네이티브간의 정보를 공유하는 환경 세팅
 -  네이티브와 웹페이지간의 정보 공유하는 방식 조사
 -  오픈소스 FlexHybridApp을 적용
- 웹뷰에서 원하는 데이타를 전달
- 네이티브가 원하는 데이타를 웹뷰에서 전달받음
 
## 기술 기록
- 앱 제작 실습 시, 조사했던 것중, 개인적으로 흥미로웠던 내용이나, 유의미한 기술 내용을 개인 블로그 기록하여 공유한다.

## 기타
- 실습, 교육내용은 멘토에 의해 변경, 추가 될수 있음
- 각 앱화면의 디자인 가이드 제작 예정