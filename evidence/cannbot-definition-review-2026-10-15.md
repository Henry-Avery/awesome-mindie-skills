# CANNBot initial catalogue review

- Review date: 2026-10-15.
- Source: [cann/cannbot-skills](https://gitcode.com/cann/cannbot-skills).
- Upstream revision: `393564ae43f304426db2c206e361cd43b2811413`, resolved from GitCode's master ref and commit API.
- Maintainer: CANNBot SIG in the CANN community.
- License: CANN Open Software License Agreement Version 2.0, read from the pinned source LICENSE.
- Scope: 36 entrypoints selected for Ascend inference engineering.

## Inspection method

The local collection's README, feature catalogue, and entrypoint metadata were used to discover candidates. The selected definitions were then fetched from GitCode's raw-content endpoint at the upstream revision above. Of those definitions, 30 matched the local files byte for byte; the six updated definitions were inspected at the public revision. Each catalogue entry stores the SHA-256 of the pinned upstream bytes.

Inspection covered frontmatter, declared task scope, overviews, workflow sections, and relevant prerequisites. Summaries and execution labels reflect those declarations. The catalogue links to original source files and retains the upstream license attribution in [source metadata](../catalog/sources.yaml).

## Selected coverage

| Upstream area | Entries | Catalogue coverage |
|---|---:|---|
| `ops/` | 15 | CANN setup, device checks, Ascend C templates and tiling, CATLASS/PyPTO/TileLang/Triton implementation, review, simulation, accuracy criteria, and operator profiling. |
| `model/` | 13 | Model migration, parallel planning and implementation, quantization, fusion, graph mode, KV caches, multistream guidance, prefetch, profiling, and debugging. |
| `graph/` | 5 | npugraph_ex triage, custom operator integration, GE memory, dynamic-shape diagnosis, and fusion passes. |
| `tools/` | 3 | asys, msaicerr, and msnpureport diagnostics. |

## Scope and dependencies

- Model workflows use PyTorch and may depend on the `cann-recipes-infer` deployment contracts. The quantization entry covers existing `compressed-tensors` artifacts.
- Parallel analysis describes Atlas A2/A3 planning. Parallel implementation must follow the supported dimensions in its own entrypoint.
- TileLang development routes by device evidence to the appropriate platform instructions. Preserve sibling skills and references when installing.
- CANN Simulator runs on a host with the simulator toolchain. Simulation results have their own scope and do not constitute device performance measurements.
- asys and msnpureport declare Ascend EP requirements; msaicerr uses the runtime environment that produced the logs. Detailed permissions and platform restrictions remain in the pinned definitions.
- Source inspection does not establish runtime correctness, software-version compatibility, or performance. All 36 entries use `validation.status: not-recorded`.
