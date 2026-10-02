# EZCable 웹앱

장치와 모듈의 단자를 시각적으로 연결하고, 배선도·BOM·배선 리스트를 한 프로젝트에서 관리하는 웹 기반 편집기입니다.

현재 저장소는 구현 전 기획 단계입니다. 참고 서비스 분석, 권장 기술 스택, MVP 범위와 단계별 일정은 [개발 계획 초안](docs/development-plan.md)을 참고하세요.

## 제안하는 첫 번째 릴리스

- 부품 이미지 등록 및 캔버스 배치
- 부품별 단자 생성·이름 지정·위치 편집
- 단자 간 직선/직각 배선과 색상·굵기·배선 라벨 설정
- 선택, 이동, 확대/축소, 스냅, 실행 취소/다시 실행
- 프로젝트 자동 저장, JSON 파일 내보내기/가져오기
- BOM 및 배선 리스트 자동 생성과 CSV 내보내기
- PNG/PDF 출력

## 권장 시작 명령

구현 착수 시 다음 구성을 권장합니다.

```bash
pnpm create vite@latest . --template react-ts
pnpm add zustand immer dexie zod nanoid
pnpm add -D vitest @testing-library/react playwright eslint prettier
```

캔버스 편집 계층은 DOM/SVG 기반으로 먼저 구현하고, 실제 성능 측정 후 필요한 경우에만 Konva 또는 PixiJS로 전환합니다.

