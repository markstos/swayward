# Maintainer backlog

Migrated from the `mu -w swayward` workstream (last live triage
2026-10-28). That workstream is an archive; this file is the source of truth
for unfinished work.

**Re-verify on current `main` before picking anything up.** Many residual
titles cite scratch dirs and oracle rows that may no longer exist. Do not
promote a residual into `KNOWN_DEVIATIONS.md` or a user-facing issue until it
reproduces.

## How to file new work

| Kind | Where |
| --- | --- |
| Deliberate / refused sway behaviour (user-visible) | [`docs/KNOWN_DEVIATIONS.md`](../KNOWN_DEVIATIONS.md); oracle cited deviation |
| Confirmed user-visible bug still true on `main` | GitHub issue (or a row under [Open bugs](#open-bugs-candidates--re-verify-first) once verified) |
| Diff-family / oracle / harness engineering | [Engineering leftovers](#engineering-leftovers) below |
| Launch / announce / templates | [Launch ops](#launch-ops) below |
| COPR / AUR / post-beta features | [Post-beta](#post-beta) below |

Public docs must not link here. See [`README.md`](README.md).

## Launch ops

Beta1 and beta2 tags already shipped. Remaining announcement work:

| Item | Notes |
| --- | --- |
| Gap / migration issue templates + pinned issue | Was `beta-report-machinery`. `.github/ISSUE_TEMPLATE` still only `bug_report.md` + `config.yml`. |
| Announce plan (where to post, beta etiquette) | Was `launch-announce-and-beta`. |
| Interest / beta-tester strategy | Was `beta1-interest-strategy`. |
| Launch sequence | Was `launch-beta1`: swaywardlock r/unixporn → oracle post (+ sway crash reports) → swayward announcement. |
| GitHub Support: purge closed-PR refs that still serve `docs/internal/TONE.md` | Nice-to-have, not a release gate. Was `github-support-purge-pr-refs`. |

Also see [`launch-checklist.md`](launch-checklist.md) (parts are pre-beta1; trust the release notes for what already shipped).

## Open bugs (candidates — re-verify first)

Likely user-visible or command-gap. Confirm on current `main` + oracle/i3 harness before filing issues or fixing.

| Item | Issue | Hint |
| --- | --- | --- |
| `rename workspace 5 to 2` rejected where sway accepts | [#34](https://github.com/swayward-wm/swayward/issues/34) | i3 522; was `swayward-rename-workspace-assigned` |
| Floating split after scratchpad show: wrong view height | [#35](https://github.com/swayward-wm/swayward/issues/35) | Was `swayward-floating-split-scratchpad-height` |
| Focus after `[con_mark] move workspace to output` matching two containers | [#36](https://github.com/swayward-wm/swayward/issues/36) | i3 543; was `swayward-move-ws-multi-match-focus` |
| Implement `ipc_kill_timeout` (drop IPC clients that stop reading) | [#37](https://github.com/swayward-wm/swayward/issues/37) | Was `swayward-ipc-kill-timeout` |

## Hygiene (small, clear)

| Item | Hint |
| --- | --- |
| AGENTS.md vs `ci.yml` on 200k proptest cadence | Was `ci-proptest-cadence-truth` |
| Packaged builds: version string / commit; `swaywardmsg --version` | Was `version-string-packaged-builds` |
| `contrib/dev-run.sh` stray `/proc/PID/cmdline` at teardown | Was `devrun-stray-proc-error` |
| Nightly oracle sweep job (skip unless `main` moved) | Was `nightly-sway-ipc-sweep` |
| Capture-check empty log when a test launches sway | Was `capture-check-launch-with-config` |
| Border inner-arc follow-ups | Was `border-arc-followups` |
| Floating-group pointer test gaps | Was `fcg-pointer-group-test-gaps` |
| Flake candidate: `tests::xdg_shell::client_interactive_resize_requires_floating` | Was `flake_candidate_tests_xdg_shell_client` |
| Scratchpad stale-entry doc/oracle follow-ups | Was `scratchpad-stale-followups` |
| Divergence ledger cites missing oracle row (focused-flag) | Was `low_diff_fam_parity_f2_focused_flag` |
| Regression test doc cites missing oracle row (hinted cross-output) | Was `low_diff_fam_v3_hinted_cross_output_move` |

## Engineering leftovers

Not user docs. Re-run or close; do not paste into `KNOWN_DEVIATIONS.md`.

### Campaigns

| Item | Hint |
| --- | --- |
| Differential campaign (`random-v2` / G16) | Was `differential-campaign` |
| Post-beta IPC-shape compliance backlog (NON-BLOCKER) | Was `post-beta-compliance-backlog` |

### Diff-family residuals

Was: `diff-fam-parity-f8l-stale-split-share-residual-1`,
`diff-fam-v3-floated-fs-sibling-residual-1`,
`diff-fam-f3-focus-order-residual-6`,
`diff-fam-f3-focus-order-residual-8`,
`diff_fam_f3_focus_order_residual_7`,
`diff-fam-parity-f2-focused-flag-residual-4`,
`diff-fam-v3-fullscreen-move-to-workspace-switches`,
`diff-fam-v3-floating-fullscreen-sibling-focus-residual-2`,
`diff-fam-v3-for-window-fs-floating-group-member-residual-1`,
`diff-fam-v3-hinted-floater-kill-focus-residual-1`,
`diff-fam-v3-urgent-criteria-move-fullscreen-scratchpad`,
`diff-fam-v3-urgent-focused-parent-residual-4`,
`diff_fam_v3_output_disable_workspace`,
`diff-fam-v3-layout-default-floated-split-command`.

Triage note (2026-10-28): scratch evidence under `scratch/g16` and
`scratch/beta-triage/` had already rotted.

### Oracle / provenance

| Item | Hint |
| --- | --- |
| Recapture sway tree fixtures inside pinned image | Was `oracle-recapture-host-fixtures` |
| Swayward adapter merges repeated workspace assignments | i3 297; was `oracle-swayward-adapter-dup-workspaces` |
| Validate i3 coverage exemption by scenario, not capture name | Was `oracle-validate-coverage-exemption-by-scenario` |
| Random corpus replayable on i3 | Was `oracle-i3-random-real-replay` |
| sway-ipc applicability gaps (hinted windows / size hints) | Was `sway-ipc-applicability-gaps` |
| Provenance: classify deps by kind, not output path | Was `provenance-classify-by-kind` |

## Post-beta

Parked on purpose until after the beta launch path. Several are already
declared in `KNOWN_DEVIATIONS.md` (e.g. global fullscreen spans one output).

| Item | Hint |
| --- | --- |
| Post-beta1 umbrella (refused until after beta) | Was `post-beta1-list` |
| Global fullscreen spans every output | Declared deviation; was `feature-global-fullscreen-span-outputs` |
| Floating-group residual random seeds | Was `fcg-random-residual-group-seeds` |
| Parity S2 output layout geometry | Was `parity-s2-output-layout-geometry` |
| Parity F9 / F8s / F11–F12 residuals | Was `parity-f9-arranged-tiled-rect`, `parity-f8s-percent-rounding`, `parity-f11-f12-tree-structure` |
| Per-view `allow_tearing` / `max_render_time` | Was `per-view-allow-tearing-render-path`, `per-view-max-render-time-deadline` |
| xwayland-satellite upstream protocol PRs | Was `satellite-upstream-standard-protocols` |
| Touchpad GET_INPUTS oracle row on real hardware | Was `touchpad-libinput-hardware-oracle-row` |
| Fedora COPR | Not a beta gate; GitHub RPMs ship. Was `deploy-copr-fedora` |
| AUR | Not a beta gate; Arch pkg on GitHub release. Was `deploy-aur` |

## mu archive

Workstream name: `swayward`. Tasks closed `superseded` on migration with a
pointer here. Do not dispatch from that workstream; open a fresh
`<project>-<purpose>` workstream when a crew actually runs.
