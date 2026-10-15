# Initial source definition review

- Review date: 2026-10-15.
- Method: local source inspection while constructing the initial catalogue.
- Source project: [pisceskkk/vllm-ascend-skills](https://github.com/pisceskkk/vllm-ascend-skills).
- Source revision: `4e7417c3d88847a17ba6d61d6a9b748ad8e0bbc3`.
- Declared upstream license: MIT.
- Inputs inspected: upstream README and all 17 `skills/*/SKILL.md` definitions.

The inspection mapped each definition's declared task and core workflow to one primary category, a short bilingual summary, technology tags, and an execution condition. Each [catalogue entry](../catalog/skills/) records the inspected definition's exact SHA-256 hash. The [source record](../catalog/sources.yaml) pins the collection revision.

## Scope

The definitions cover serving, correctness, benchmarking, profiling, multistream overlap, Triton operator development, debugging, and change validation. Offline profiling analysis consumes existing artifacts. Full collection, service, kernel, and optimization workflows include device execution. Change validation selects hardware requirements from the required checks.

This is a definition-level review. Referenced implementation files and runtime behavior require their own review and execution evidence. The initial catalogue records no hardware reproduction, framework-version compatibility matrix, or measured performance result. All initial entries therefore use `validation.status: not-recorded`.
