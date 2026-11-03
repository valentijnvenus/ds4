# ds4 lane

lane/main is a merge-only branch: antirez/ds4 upstream + the 1BP v5 delta.

| source | sha | note |
|---|---|---|
| 1BP base | `5b013dc1bb75` | 1BP v5 packages (reader, converter, checker) |
| antirez upstream main | `890898cfb437` | merged 2026-11-03 |

kyuz0/ds4 `main-gfx1151` (`2998e965991a`) is kept as `snapshot/kyuzo-gfx1151` and is **not** merged
here: upstream already ships ROCm/gfx1151 (`ds4_rocm*.cu`, `rocm/*.cuh`, `make strix-halo`), while
kyuz0's branch is 130 commits behind and merging it produced 50 conflict hunks across 9 files with no
compiler at hand to validate. Its perf work (incl. PR #7 `rocm-short-prefill`, head `4a0e2fce2e83`)
is a later, build-validated cherry-pick, not a blind merge.

Build: `make -j$(nproc) strix-halo`
