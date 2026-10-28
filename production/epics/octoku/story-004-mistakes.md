# Story 004: 오답 처리와 실수 3회 실패

> **Epic**: Octoku
> **Status**: Ready
> **Layer**: Core
> **Type**: Logic
> **Estimate**: S
> **Manifest Version**: N/A (minimal — no control manifest)
> **Last Updated**: [set by /dev-story when implementation begins]

## Context

**GDD**: `design/game-brief.md`
**Requirement**: `Brief MVP feature 4`

**ADR Governing Implementation**: N/A (minimal — no ADRs)
**ADR Decision Summary**: N/A (minimal — no ADRs)
**ADR Version**: N/A (minimal — no ADRs)

**Engine**: Godot 4.7 | **Risk**: HIGH
**Engine Notes**: none (no ADR engine-compatibility analysis at minimal)

**Control Manifest Rules (this layer)**: N/A (minimal — no control manifest)

---

## Acceptance Criteria

*From `design/game-brief.md` (MVP 4, Player goal & fail state), scoped to this story:*

- [ ] 넣은 숫자가 정답과 같으면 그 칸은 정답으로 고정되어 더 이상 지우거나 바꿀 수 없다.
- [ ] 넣은 숫자가 정답과 다르면 그 칸이 빨갛게 표시되고 실수가 1 오른다.
- [ ] 틀린 숫자는 지우거나 다른 숫자로 바꿀 수 있다. 칸에 이미 있는 숫자를 다시 누르면 아무 일도 없고 실수도 늘지 않는다.
- [ ] 실수가 화면에 `실수 n/3`으로 보이고, 한도 3은 설정 파일 값이다.
- [ ] 실수가 한도에 도달하면 판 상태가 `LOST`가 되고, 그 뒤의 입력은 무시된다.
- [ ] 64칸이 모두 정답으로 채워지면 판 상태가 `WON`이 된다.
- [ ] 상태 변화는 signal(`mistake_made`, `game_won`, `game_lost`)로 알린다.
- [ ] 단위 테스트: 정답 입력, 오답 입력, 한도 도달 시 `LOST`, 마지막 칸 정답 시 `WON`.

---

## Implementation Notes

N/A (minimal — no ADRs).

---

## Out of Scope

- Story 005: 결과 화면 (이 스토리는 상태와 signal까지)

---

## Files

- `src/core/game_state.gd`
- `src/ui/hud.gd`
- `src/ui/board_view.gd`
- `assets/data/game_config.tres`
- `tests/unit/game/game_state_rules_test.gd`

---

## QA Test Cases

*N/A — no qa-lead specs at this tier; implement against the Acceptance Criteria above*

---

## Test Evidence

*`qa.level: minimal`: tests are waived (advisory); the screenshot of the red mistake cell and counter is not.*

**Story Type**: Logic
**Required evidence**:
- Logic: `tests/unit/game/game_state_rules_test.gd` (advisory at `qa.level: minimal`)
- Screenshot showing a wrong digit and the mistake counter in `production/qa/evidence/`

**Status**: [ ] Not yet created

---

## Dependencies

- Depends on: `production/epics/octoku/story-003-digit-pad.md`
- Unlocks: `production/epics/octoku/story-005-result-screens.md`
