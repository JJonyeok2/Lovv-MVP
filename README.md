# Lovv MVP

Lovv MVP는 취향 기반 여행 테마 선택, 소도시 탐색, AI 일정 생성 흐름을 검증하기 위한 React 프론트엔드입니다.

이 저장소는 Vercel 배포를 위한 MVP UI 저장소입니다. 현재 구현은 프론트엔드 중심이며, 로그인, 선호도, 저장한 일정, 좋아요 상태는 브라우저 로컬 저장소와 정적 데이터 기반으로 동작합니다.

## 주요 기능

- 로그인 진입 화면과 온보딩 선호도 선택
- 선택한 여행 테마 기반 홈 화면과 월별 추천 콘텐츠
- 한국과 일본 소도시 지도 탐색, 필터, 상세 패널
- 추천 조건을 반영한 AI 일정 생성형 플래너 화면
- 생성된 일정 상세 보기와 저장한 일정 관리
- 마이페이지에서 선호도와 저장 상태 확인

## 기술 스택

- React
- TypeScript
- Vite
- Tailwind CSS
- Vitest
- Testing Library
- ESLint

## 실행 방법

```bash
npm ci
npm run dev
```

로컬 개발 서버는 Vite 기본 설정을 따릅니다.

## Vercel 배포

Vercel에서 이 저장소를 연결한 뒤 아래 설정을 사용합니다.

- Framework Preset: Vite
- Install Command: `npm ci`
- Build Command: `npm run build`
- Output Directory: `dist`

SPA 라우팅을 사용하므로 Vercel의 기본 Vite 배포 설정으로 각 화면 경로를 처리할 수 있습니다.

## 환경 변수

Google Maps 화면을 사용하려면 Vercel Project Settings의 Environment Variables에 아래 값을 등록합니다.

```bash
VITE_GOOGLE_MAPS_API_KEY=your_google_maps_browser_key_here
VITE_GOOGLE_MAPS_MAP_ID=your_google_maps_map_id_here
```

실제 키는 `.env.local`에만 두고 Git에 커밋하지 않습니다. 저장소에는 예시 값만 담은 `.env.example`을 유지합니다.

## 검증 명령

배포 전 아래 명령을 통과해야 합니다.

```bash
npm test
npm run lint
npm run build
```

현재 테스트는 라우팅, 소도시 데이터, API 어댑터 형태, 이미지 자산, 저장한 일정 관련 화면 동작을 확인합니다.

## 현재 범위

이 MVP는 사용자가 실제 서비스 흐름을 확인할 수 있는 UI 구현에 초점을 둡니다. 실제 운영 API, 데이터베이스, 인증 서버, 결제, 관리자 기능은 이 저장소의 현재 범위에 포함하지 않습니다.
