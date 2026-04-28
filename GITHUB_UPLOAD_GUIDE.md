# GitHub 업로드 가이드

## 리포지토리 구조

```
bose-helper/
├── index.html              # 메인 애플리케이션 파일
├── docs/
│   ├── guide.pdf          # BOSE 도우미 가이드 (PDF)
│   └── guide.html         # BOSE 도우미 가이드 (HTML)
├── README.md              # 프로젝트 문서
├── LICENSE                # MIT 라이선스
└── .gitignore            # Git 무시 파일
```

## GitHub에 업로드하는 방법

### 방법 1: GitHub 웹사이트에서 직접 업로드

1. **GitHub 로그인**
   - https://github.com 접속
   - 로그인

2. **새 리포지토리 생성**
   - 우측 상단 `+` 버튼 클릭
   - `New repository` 선택
   - Repository name: `bose-helper`
   - Description: `BOSE 제품 문제 해결 및 AS 안내 챗봇`
   - Public/Private 선택
   - `Create repository` 클릭

3. **파일 업로드**
   - `uploading an existing file` 클릭
   - `/mnt/user-data/outputs/bose-helper/` 폴더의 모든 파일을 드래그 앤 드롭
   - Commit message 입력: "Initial commit"
   - `Commit changes` 클릭

### 방법 2: Git CLI 사용 (권장)

```bash
# 1. 다운로드한 bose-helper 폴더로 이동
cd bose-helper

# 2. Git 초기화
git init

# 3. 모든 파일 추가
git add .

# 4. 첫 커밋
git commit -m "Initial commit: BOSE Helper v1.1"

# 5. GitHub 리포지토리와 연결 (리포지토리 생성 후)
git remote add origin https://github.com/[your-username]/bose-helper.git

# 6. 푸시
git branch -M main
git push -u origin main
```

### 방법 3: GitHub Desktop 사용

1. GitHub Desktop 다운로드 및 설치
2. `File` → `Add Local Repository`
3. `bose-helper` 폴더 선택
4. `Publish repository` 클릭
5. 리포지토리 정보 입력 후 업로드

## GitHub Pages로 배포하기

웹사이트로 바로 배포하려면:

1. 리포지토리 페이지에서 `Settings` 클릭
2. 좌측 메뉴에서 `Pages` 선택
3. Source: `Deploy from a branch` 선택
4. Branch: `main` / `/ (root)` 선택
5. `Save` 클릭
6. 약 1-2분 후 `https://[your-username].github.io/bose-helper/` 에서 접속 가능

## 추천 리포지토리 URL

- `https://github.com/[your-username]/bose-helper`
- `https://github.com/[your-username]/bose-assistant`
- `https://github.com/[your-username]/bose-support-helper`

## 다음 단계

업로드 후:
1. README.md에 스크린샷 추가
2. GitHub Topics 추가: `bose`, `chatbot`, `troubleshooting`, `korean`
3. About 섹션 작성
4. GitHub Pages 링크 추가

## 필요한 파일

다운로드해야 할 파일:
- `/mnt/user-data/outputs/bose-helper/` 폴더 전체

모든 파일이 준비되었습니다!
