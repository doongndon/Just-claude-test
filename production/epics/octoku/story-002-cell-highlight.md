# Story 002: 칸 선택 하이라이트

> **Epic**: Octoku
> **Status**: Ready
> **Layer**: Presentation
> **Type**: Visual/Feel
> **Estimate**: S
> **Manifest Version**: N/A (minimal — no control manifest)
> **Last Updated**: [set by /dev-story when implementation begins]

## Context

**GDD**: `design/game-brief.md`
**Requirement**: `Brief MVP feature 2`

**ADR Governing Implementation**: N/A (minimal — no ADRs)
**ADR Decision Summary**: N/A (minimal — no ADRs)
**ADR Version**: N/A (minimal — no ADRs)

**Engine**: Godot 4.7 | **Risk**: HIGH
**Engine Notes**: none (no ADR engine-compatibility analysis at minimal)

**Control Manifest Rules (this layer)**: N/A (minimal — no control manifest)

---

## Acceptance Criteria

*From `design/game-brief.md` (MVP 2, Core loop step 1), scoped to this story:*

- [ ] 칸을 탭하거나 클릭하면 그 칸이 선택되고, 다른 칸을 누르면 선택이 옮겨지며, 보드 밖을 누르면 선택이 풀린다.
- [ ] 선택한 칸은 가장 진한 강조로 보인다.
- [ ] 선택한 칸과 같은 링, 같은 방사선, 같은 구역에 속한 17칸은 연한 강조로 보인다.
- [ ] 선택한 칸에 숫자가 있으면 보드 위의 같은 숫자 칸이 모두 별도 강조로 보인다.
- [ ] 세 가지 강조(선택, 같은 줄, 같은 숫자)는 서로 구분되고, 색은 설정 파일 값이다.
- [ ] 안쪽 링 칸 하나와 바깥 링 칸 하나를 각각 선택한 스크린샷 2장이 `production/qa/evidence/`에 남는다.

---

## Implementation Notes

N/A (minimal — no ADRs). The highlight is what makes rings, spokes and zones readable on a circular board (brief MVP 2).

---

## Out of Scope

- Story 003: 숫자 입력 (이 스토리는 선택과 강조만)

---

## Files

- `src/core/board_topology.gd` (peer cells)
- `src/ui/board_view.gd`
- `assets/data/game_config.tres`
- `tests/unit/board/board_topology_test.gd`

---

## QA Test Cases

*N/A — no qa-lead specs at this tier; implement against the Acceptance Criteria above*

---

## Test Evidence

**Story Type**: Visual/Feel
**Required evidence**:
- Visual/Feel: retained screenshots in `production/qa/evidence/` + sign-off in `production/qa/evidence/cell-highlight-evidence.md`

**Status**: [ ] Not yet created

---

## Dependencies

- Depends on: `production/epics/octoku/story-001-octagon-board.md`
- Unlocks: `production/epics/octoku/story-003-digit-pad.md`
