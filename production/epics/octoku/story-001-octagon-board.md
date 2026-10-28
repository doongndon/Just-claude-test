# Story 001: 팔각 보드 그리기

> **Epic**: Octoku
> **Status**: Ready
> **Layer**: Foundation
> **Type**: Logic
> **Estimate**: M
> **Manifest Version**: N/A (minimal — no control manifest)
> **Last Updated**: [set by /dev-story when implementation begins]

## Context

**GDD**: `design/game-brief.md`
**Requirement**: `Brief MVP feature 1`

**ADR Governing Implementation**: N/A (minimal — no ADRs)
**ADR Decision Summary**: N/A (minimal — no ADRs)
**ADR Version**: N/A (minimal — no ADRs)

**Engine**: Godot 4.7 | **Risk**: HIGH
**Engine Notes**: none (no ADR engine-compatibility analysis at minimal)

**Control Manifest Rules (this layer)**: N/A (minimal — no control manifest)

---

## Acceptance Criteria

*From `design/game-brief.md` (MVP 1, Player goal & fail state), scoped to this story:*

- [ ] 보드는 링 8겹(안쪽 0 ~ 바깥 7) x 방사선 8줄 = 64칸이고, 각 칸은 안쪽 팔각형의 한 변과 바깥 팔각형의 같은 변 사이의 사다리꼴로 그려진다.
- [ ] 칸 번호 `cell = ring * 8 + spoke`에서 링, 방사선, 구역을 얻을 수 있다. 구역은 (안쪽 4링 / 바깥 4링) x 사분면(방사선 2줄씩)으로 8개다.
- [ ] 24줄(링 8, 방사선 8, 구역 8)이 각각 정확히 8칸이고, 모든 칸은 링·방사선·구역에 하나씩 속한다.
- [ ] 구역 경계(안쪽과 바깥을 나누는 팔각형, 사분면을 나누는 방사선 4줄)는 일반 칸 경계보다 굵게 그려진다.
- [ ] 고정 퍼즐 파일 1개를 불러와 시작 숫자를 칸 중앙에 표시하고, 빈 칸은 비워 둔다.
- [ ] 화면의 한 점이 속한 칸 번호를 구할 수 있고, 보드 밖이나 중앙 빈 공간이면 -1이다.
- [ ] 보드 크기, 중앙 빈 공간, 선 굵기는 설정 파일 값이다 (코드에 고정하지 않는다).
- [ ] 1280x720 창에서 실행하면 보드 전체가 화면 안에 보이고, 그 스크린샷이 `production/qa/evidence/`에 남는다.

---

## Implementation Notes

N/A (minimal — no ADRs). Brief Build order step 1 names this the riskiest part: whether the circular board reads clearly.

---

## Out of Scope

- Story 002: 칸 선택과 하이라이트
- Story 003: 숫자 입력
- Story 006: 퍼즐 생성 (이 스토리는 고정 퍼즐 파일만 쓴다)

---

## Files

- `src/core/board_topology.gd`
- `src/core/board_geometry.gd`
- `src/core/game_config.gd`
- `assets/data/game_config.tres`
- `src/core/puzzle.gd`
- `assets/data/puzzles/fixed_001.json`
- `src/ui/board_view.gd`
- `src/main.gd`, `src/main.tscn`
- `tests/unit/board/board_topology_test.gd`
- `tests/unit/board/board_geometry_test.gd`

---

## QA Test Cases

*N/A — no qa-lead specs at this tier; implement against the Acceptance Criteria above*

---

## Test Evidence

*`qa.level: minimal`: tests are waived (advisory); the retained screenshot is not, because the board is player-observable.*

**Story Type**: Logic
**Required evidence**:
- Logic: `tests/unit/board/board_topology_test.gd`, `tests/unit/board/board_geometry_test.gd` (advisory at `qa.level: minimal`)
- Screenshot of the board at 1280x720 in `production/qa/evidence/`

**Status**: [ ] Not yet created

---

## Dependencies

- Depends on: None
- Unlocks: `production/epics/octoku/story-002-cell-highlight.md`
