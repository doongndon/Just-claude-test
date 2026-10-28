# Epic: Octoku

> **Source**: `design/game-brief.md` (workflow: minimal — no GDDs or ADRs)
> **Engine**: Godot 4.7 (GDScript)

## Goal

다트판처럼 생긴 팔각 보드에 1~8을 채워, 모든 링과 방사선과 구역이 8로 딱 맞아떨어지게 만드는 수도쿠.

## Scope (Brief MVP)

1. 팔각 보드 그리기
2. 칸 선택 하이라이트
3. 숫자 패드 입력과 지우기
4. 오답 처리와 실수 3회 실패
5. 퍼즐 생성기와 난이도 3단계
6. 메모(후보 숫자) 입력
7. 클리어/실패 화면과 다시 하기, 새 퍼즐

## Order (Brief Build order)

1. 보드 그리기, 칸 선택, 하이라이트 (가장 불확실: 원형 보드가 읽히는가)
2. 숫자 입력, 정답 비교, 실수 3회 규칙
3. 클리어/실패 화면
4. 퍼즐 생성기와 난이도 3단계
5. 메모 입력

## Stories

| # | Story | Type | Status | ADR |
|---|-------|------|--------|-----|
| 001 | 팔각 보드 그리기 | Logic | Ready | N/A |
| 002 | 칸 선택 하이라이트 | Visual/Feel | Ready | N/A |
| 003 | 숫자 패드 입력과 지우기 | UI | Ready | N/A |
| 004 | 오답 처리와 실수 3회 실패 | Logic | Ready | N/A |
| 005 | 클리어/실패 화면, 다시 하기와 새 퍼즐 | UI | Ready | N/A |
| 006 | 퍼즐 생성기와 난이도 3단계 | Logic | Ready | N/A |
| 007 | 메모(후보 숫자) 입력 | UI | Ready | N/A |
