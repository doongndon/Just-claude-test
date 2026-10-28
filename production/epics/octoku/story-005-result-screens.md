# Story 005: 클리어/실패 화면, 다시 하기와 새 퍼즐

> **Epic**: Octoku
> **Status**: Ready
> **Layer**: Presentation
> **Type**: UI
> **Estimate**: S
> **Manifest Version**: N/A (minimal — no control manifest)
> **Last Updated**: [set by /dev-story when implementation begins]

## Context

**GDD**: `design/game-brief.md`
**Requirement**: `Brief MVP feature 7`

**ADR Governing Implementation**: N/A (minimal — no ADRs)
**ADR Decision Summary**: N/A (minimal — no ADRs)
**ADR Version**: N/A (minimal — no ADRs)

**Engine**: Godot 4.7 | **Risk**: HIGH
**Engine Notes**: none (no ADR engine-compatibility analysis at minimal)

**Control Manifest Rules (this layer)**: N/A (minimal — no control manifest)

---

## Acceptance Criteria

*From `design/game-brief.md` (MVP 7, Core loop step 4, Player goal & fail state), scoped to this story:*

- [ ] 판 상태가 `WON`이 되면 보드 위에 클리어 화면이 뜨고, 그 판의 실수 횟수를 보여 준다.
- [ ] 판 상태가 `LOST`가 되면 실패 화면이 뜬다.
- [ ] 두 화면 모두 `다시 하기`와 `새 퍼즐` 버튼이 있다.
- [ ] `다시 하기`는 같은 퍼즐을 처음 상태(시작 숫자만, 실수 0)로 되돌린다.
- [ ] `새 퍼즐`은 퍼즐 공급원에서 다음 퍼즐을 받아 시작한다. Story 006 전까지 공급원은 고정 퍼즐 파일 목록이다.
- [ ] 결과 화면이 떠 있는 동안 보드와 숫자 패드 입력은 막힌다.
- [ ] 클리어 화면과 실패 화면의 스크린샷이 각각 `production/qa/evidence/`에 남는다.

---

## Implementation Notes

N/A (minimal — no ADRs).

---

## Out of Scope

- Story 006: 생성기 (이 스토리의 공급원은 고정 퍼즐 목록)

---

## Files

- `src/ui/result_overlay.gd`
- `src/core/puzzle_source.gd`
- `assets/data/puzzles/fixed_002.json`
- `src/main.gd`, `src/main.tscn`

---

## QA Test Cases

*N/A — no qa-lead specs at this tier; implement against the Acceptance Criteria above*

---

## Test Evidence

**Story Type**: UI
**Required evidence**:
- UI: retained screenshots of the win screen and the fail screen in `production/qa/evidence/`

**Status**: [ ] Not yet created

---

## Dependencies

- Depends on: `production/epics/octoku/story-004-mistakes.md`
- Unlocks: `production/epics/octoku/story-006-puzzle-generator.md`
