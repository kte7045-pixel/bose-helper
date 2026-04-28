# BOSE 도우미 (BOSE Helper)

BOSE 제품의 문제 해결 및 AS 안내를 위한 대화형 웹 애플리케이션

## 개요

BOSE 도우미는 BOSE 제품 사용자들이 겪는 일반적인 문제들을 해결하고, 공장 초기화 방법과 서비스센터 정보를 쉽게 찾을 수 있도록 돕는 챗봇 스타일의 웹 애플리케이션입니다.

## 주요 기능

### 1. 제품 지원
- **헤드폰**: QC Ultra 2세대, QC Ultra, QC, QC45, QC35, QC25
- **이어버드**: QC Ultra 이어버드 2세대, QC Ultra 이어버드, 울트라 오픈 이어버드, QC 이어버드 II
- **스피커**: 홈 스피커 시리즈, SoundLink Flex/Max/Revolve/Mini
- **홈시어터**: Soundbar Ultra/900/700/600/500/300, TV 스피커
- **홈오디오**: Wave SoundTouch, SoundTouch 10/20/30

### 2. 핵심 기능
- 제품별 공장 초기화 가이드
- 블루투스 연결 문제 해결
- AI 기반 제품 이미지 인식 (Claude Sonnet 4 API)
- 서비스센터 위치 및 교통편 안내
- AS 접수 절차 안내 (택배/방문)
- QC Ultra 2세대 상세 사용 매뉴얼

### 3. 사용자 경험
- 대화형 인터페이스
- 모바일 최적화 디자인
- 단계별 시각적 가이드
- 빠른 선택을 위한 칩 버튼
- 제품 사진 촬영/업로드 기능

## 기술 스택

### Frontend
- HTML5
- CSS3 (CSS Variables)
- Vanilla JavaScript

### API 연동
- **Claude Sonnet 4**: 제품 이미지 분석 및 인식
- **Kakao Map**: 서비스센터 위치 안내

### 디자인
- **폰트**: Bebas Neue (헤더), Noto Sans KR (본문)
- **컬러**: 미니멀 블랙/화이트 팔레트
- **레이아웃**: 최대 480px 너비, 모바일 우선

## 파일 구조

```
├── index.html              # 메인 애플리케이션 파일
├── docs/
│   ├── guide.pdf          # BOSE 도우미 가이드 (PDF)
│   └── guide.html         # BOSE 도우미 가이드 (HTML)
└── README.md              # 프로젝트 문서
```

## 사용 방법

### 로컬 실행
1. 저장소 클론
```bash
git clone https://github.com/[your-username]/bose-helper.git
cd bose-helper
```

2. 브라우저에서 `index.html` 열기

### API 키 설정
제품 이미지 인식 기능을 사용하려면 Claude API 키가 필요합니다. 현재 코드에서는 API 키 없이도 기본 기능들은 모두 작동합니다.

Claude API를 사용하려면:
1. [Anthropic](https://www.anthropic.com)에서 API 키 발급
2. `index.html`의 `analyzePhoto` 함수에서 API 호출 부분 수정

## 주요 데이터 구조

### BOSE_DATA.menus
제품 카테고리별 메뉴 정보
```javascript
{
  'screen-headphone': { 
    title: '헤드폰', 
    cat: 'headphone', 
    items: [...]
  }
}
```

### BOSE_DATA.guides
제품별 초기화 가이드
```javascript
{
  'screen-qcutra2': {
    tag: 'QC Ultra 헤드폰 2세대',
    cat: 'headphone',
    reset: {
      title: '공장 초기화',
      steps: [...],
      warning: '...'
    }
  }
}
```

### QC_ULTRA2_MANUAL
QC Ultra 2세대 상세 매뉴얼
- battery: 배터리 정보
- buttons: 버튼 조작법
- modes: 청취 모드
- bluetooth: 블루투스 연결
- charging: 충전 방법
- led: 상태등 안내
- wired: 유선 연결
- reset: 리셋 방법
- care: 관리 및 보관
- box: 박스 구성품

## 주요 기능 흐름

### 1. 제품 선택 방식
```
제품 목록 보기 → 카테고리 선택 → 제품 선택
내 제품 찾기 → 사진 촬영 → AI 인식 → 제품 확인
```

### 2. 문제 해결 흐름
```
증상 선택 → 제품 확인 → 공장 초기화 → 성공/실패 분기
  ├─ 성공 → 완료 안내
  └─ 실패 → AS 안내 → 접수 방법 선택
      ├─ 직접 방문 → 서비스센터 위치
      └─ 택배 접수 → 포장 안내 → 발송 안내
```

## 서비스센터 정보

### 세기HE BOSE 공식 서비스센터
- **주소**: 서울시 중구 소파로 127번지 (남산동 2가 23) 세기빌딩
- **전화**: 02-3446-3514
- **운영시간**: 평일 10:00~18:00 (주말·공휴일 휴무)

### 교통편
- **지하철**: 4호선 명동역 1번 출구 → 도보 약 10분
- **버스**: 104, 105, 263, 421, 507, 604, 6001, 6015, 7011번

## 고객센터 연락처
- **BOSE 공식 고객센터**: 1588-5044 (평일 09:00~18:00)
- **한진택배**: 1588-0011
- **서비스센터**: 02-3446-3514

## 브라우저 지원
- Chrome (권장)
- Safari
- Firefox
- Edge

모바일 브라우저 모두 지원

## 라이선스
MIT License

## 기여
이슈와 풀 리퀘스트를 환영합니다!

## 작성자
BOSE 도우미 개발팀

## 업데이트 내역
- **v1.1** (2025-04-28)
  - QC Ultra 헤드폰 2세대 상세 매뉴얼 추가
  - 블루투스 연결 문제 해결 가이드 개선
  - AI 제품 인식 기능 추가
  - 제품 별칭/약칭 검색 지원 강화
  
- **v1.0** (2025-04-01)
  - 초기 버전 출시
  - 기본 제품 가이드 및 초기화 방법 제공
