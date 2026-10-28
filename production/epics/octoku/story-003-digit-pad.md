# Story 003: 숫자 패드 입력과 지우기

> **Epic**: Octoku
> **Status**: Ready
> **Layer**: Core
> **Type**: UI
> **Estimate**: S
> **Manifest Version**: N/A (minimal — no control manifest)
> **Last Updated**: [set by /dev-story when implementation begins]

## Context

**GDD**: `design/game-brief.md`
**Requirement**: `Brief MVP feature 3`

**ADR Governing Implementation**: N/A (minimal — no ADRs)
**ADR Decision Summary**: N/A (minimal — no ADRs)
**ADR Version**: N/A (minimal — no ADRs)

**Engine**: Godot 4.7 | **Risk**: HIGH
**Engine Notes**: none (no ADR engine-compatibility analysis at minimal)

**Control Manifest Rules (this layer)**: N/A (minimal — no control manifest)

---

## Acceptance Criteria

*From `design/game-brief.md` (MVP 3, Core loop step 2), scoped to this story:*

- [ ] 화면에 1~8 숫자 버튼 8개와 지우기 버튼이 있다.
- [ ] 빈 칸을 선택하고 숫자 버튼을 누르면 그 칸에 숫자가 들어간다. 키보드 1~8도 같은 동작을 한다.
- [ ] 플레이어가 넣은 숫자가 있는 칸에서 지우기(또는 Delete, Backspace)를 누르면 빈 칸이 된다.
- [ ] 시작 숫자가 있는 고정칸에서는 숫자 입력과 지우기가 무시되고 내용이 바뀌지 않는다.
- [ ] 선택한 칸이 없으면 숫자 버튼과 지우기는 아무 일도 하지 않는다.
- [ ] 플레이어가 넣은 숫자는 시작 숫자와 다른 색으로 보인다.
- [ ] 숫자 패드 버튼 크기는 설정 파일 값이다.
- [ ] 숫자를 넣은 화면의 스크린샷이 `production/qa/evidence/`에 남는다.

---

## Implementation Notes

N/A (minimal — no ADRs). Correct-answer locking and mistakes belong to story 004.

---

## Out of Scope

- Story 004: 정답 비교, 정답 고정, 실수 세기
- Story 007: 메모 입력

---

## Files

- `src/core/game_state.gd`
- `src/ui/digit_pad.gd`
- `src/ui/board_view.gd`
- `src/main.gd`, `src/main.tscn`
- `tests/unit/game/game_state_input_test.gd`

---

## QA Test Cases

*N/A — no qa-lead specs at this tier; implement against the Acceptance Criteria above*

---

## Test Evidence

**Story Type**: UI
**Required evidence**:
- UI: a retained screenshot of the board with the digit pad in `production/qa/evidence/`

**Status**: [ ] Not yet created

---

## Dependencies

- Depends on: `production/epics/octoku/story-002-cell-highlight.md`
- Unlocks: `production/epics/octoku/story-004-mistakes.md`, `production/epics/octoku/story-007-notes.md`
