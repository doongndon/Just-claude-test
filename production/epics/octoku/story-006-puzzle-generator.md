# Story 006: 퍼즐 생성기와 난이도 3단계

> **Epic**: Octoku
> **Status**: Ready
> **Layer**: Core
> **Type**: Logic
> **Estimate**: M
> **Manifest Version**: N/A (minimal — no control manifest)
> **Last Updated**: [set by /dev-story when implementation begins]

## Context

**GDD**: `design/game-brief.md`
**Requirement**: `Brief MVP feature 5`

**ADR Governing Implementation**: N/A (minimal — no ADRs)
**ADR Decision Summary**: N/A (minimal — no ADRs)
**ADR Version**: N/A (minimal — no ADRs)

**Engine**: Godot 4.7 | **Risk**: HIGH
**Engine Notes**: none (no ADR engine-compatibility analysis at minimal)

**Control Manifest Rules (this layer)**: N/A (minimal — no control manifest)

---

## Acceptance Criteria

*From `design/game-brief.md` (MVP 5, Player goal & fail state: "정답은 항상 하나뿐이다"), scoped to this story:*

- [ ] 생성된 완성판은 24줄(링 8, 방사선 8, 구역 8) 모두에 1~8이 한 번씩 들어 있다.
- [ ] 생성된 퍼즐은 정답이 정확히 하나다. 풀이기가 해를 2개까지 세어 1개임을 확인한다.
- [ ] 같은 시드로는 항상 같은 퍼즐이 나온다. 테스트는 고정 시드를 쓴다.
- [ ] 난이도 쉬움, 보통, 어려움은 시작 숫자 개수로 정하고, 각 개수는 설정 파일 값이다.
- [ ] 정답이 하나로 유지되는 한도까지만 시작 숫자를 줄이고, 실제로 남은 개수를 퍼즐에 기록한다.
- [ ] 화면에서 난이도를 골라 새 퍼즐을 시작할 수 있고, `새 퍼즐`은 이제 생성기를 쓴다.
- [ ] 어려움 난이도 퍼즐 하나를 만드는 데 1초를 넘지 않는다 (개발 PC 기준).
- [ ] 단위 테스트: 완성판 유효성, 유일해, 결정성, 난이도별 시작 숫자 개수.

---

## Implementation Notes

N/A (minimal — no ADRs).

---

## Out of Scope

- 매일 퍼즐, 랭킹 (brief Out of scope)

---

## Files

- `src/core/puzzle_solver.gd`
- `src/core/puzzle_generator.gd`
- `src/core/puzzle_source.gd`
- `src/ui/hud.gd`
- `assets/data/game_config.tres`
- `tests/unit/puzzle/puzzle_solver_test.gd`
- `tests/unit/puzzle/puzzle_generator_test.gd`

---

## QA Test Cases

*N/A — no qa-lead specs at this tier; implement against the Acceptance Criteria above*

---

## Test Evidence

*`qa.level: minimal`: tests are waived (advisory); the screenshot of a generated puzzle with the difficulty picker is not.*

**Story Type**: Logic
**Required evidence**:
- Logic: `tests/unit/puzzle/puzzle_solver_test.gd`, `tests/unit/puzzle/puzzle_generator_test.gd` (advisory at `qa.level: minimal`)
- Screenshot of a generated puzzle in `production/qa/evidence/`

**Status**: [ ] Not yet created

---

## Dependencies

- Depends on: `production/epics/octoku/story-005-result-screens.md`
- Unlocks: None
