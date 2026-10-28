# Story 007: 메모(후보 숫자) 입력

> **Epic**: Octoku
> **Status**: Ready
> **Layer**: Feature
> **Type**: UI
> **Estimate**: S
> **Manifest Version**: N/A (minimal — no control manifest)
> **Last Updated**: [set by /dev-story when implementation begins]

## Context

**GDD**: `design/game-brief.md`
**Requirement**: `Brief MVP feature 6`

**ADR Governing Implementation**: N/A (minimal — no ADRs)
**ADR Decision Summary**: N/A (minimal — no ADRs)
**ADR Version**: N/A (minimal — no ADRs)

**Engine**: Godot 4.7 | **Risk**: HIGH
**Engine Notes**: none (no ADR engine-compatibility analysis at minimal)

**Control Manifest Rules (this layer)**: N/A (minimal — no control manifest)

---

## Acceptance Criteria

*From `design/game-brief.md` (MVP 6, Core loop step 2: "확신이 없으면 메모해 둔다"), scoped to this story:*

- [ ] 메모 모드 토글 버튼이 있고, 켜져 있는지 화면에서 알 수 있다. 키보드 N도 토글한다.
- [ ] 메모 모드에서 빈 칸에 숫자를 누르면 그 숫자 메모가 켜지거나 꺼진다 (칸마다 1~8 각각).
- [ ] 메모는 칸 안에 작은 숫자로 보이고, 숫자가 들어간 칸에서는 보이지 않는다.
- [ ] 메모 입력은 정답 비교와 실수 수에 영향을 주지 않는다.
- [ ] 메모 모드에서 지우기를 누르면 그 칸의 메모가 모두 지워진다.
- [ ] `다시 하기`와 `새 퍼즐`은 메모를 모두 지운다.
- [ ] 메모가 있는 보드의 스크린샷이 `production/qa/evidence/`에 남는다.

---

## Implementation Notes

N/A (minimal — no ADRs).

---

## Out of Scope

- 후보 자동 정리, 힌트 (brief Out of scope: 힌트)

---

## Files

- `src/core/game_state.gd`
- `src/ui/board_view.gd`
- `src/ui/digit_pad.gd`
- `tests/unit/game/game_state_notes_test.gd`

---

## QA Test Cases

*N/A — no qa-lead specs at this tier; implement against the Acceptance Criteria above*

---

## Test Evidence

**Story Type**: UI
**Required evidence**:
- UI: a retained screenshot of a board with notes in `production/qa/evidence/`

**Status**: [ ] Not yet created

---

## Dependencies

- Depends on: `production/epics/octoku/story-003-digit-pad.md`
- Unlocks: None
