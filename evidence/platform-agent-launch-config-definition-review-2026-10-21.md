# Platform and agent launch configuration definition review

- Review date: 2026-10-21.
- Source: [Henry-Avery/ascend-agent-skills](https://github.com/Henry-Avery/ascend-agent-skills), maintained by Henry-Avery, MIT.
- Source revision: `250fc8cd3da2a217ef0a4d84ff5ee5a9016a6f5a`.
- Definition: [skills/platform-agent-launch-config/SKILL.md](https://github.com/Henry-Avery/ascend-agent-skills/blob/250fc8cd3da2a217ef0a4d84ff5ee5a9016a6f5a/skills/platform-agent-launch-config/SKILL.md).
- Definition SHA-256: `cfeb98afdf5aab940a1b8f97c93fdd5e826818662ec0e0f74f5eeb1316e428c5`.
- Files inspected: the complete skill directory (one `SKILL.md`), source repository guidance, README entry, and license.
- Related requirement: [Issue #5](https://github.com/mindie-agent/awesome-mindie-skills/issues/5).

## Scope

The skill traces platform inputs through configuration storage, parameter calculation, script generation, environment setup, and launch wrapping. It produces platform field guidance and templates, per-node agent scripts with required dependencies and invocation context, and a comparison of shared values, necessary differences, conflicts, and unknowns. It distinguishes supplied values, statically derived values, and observations from a real execution.

The reviewed definition addresses source-versus-deployment revision uncertainty, changes in the inspected working tree, conflicting representations, dynamic launcher arguments, and reverse conversion of per-node values into reusable platform templates. It directs readiness and stopping back to the existing lifecycle workflow. It contains methods and relative source pointers, not platform implementation code.

Unlike the existing serving skills, this task ends at configuration generation and static inspection. It does not submit forms, assign devices, install environments, start or stop services, or require a UI/MCP integration. Host-side analysis needs user-supplied source and configuration artifacts; a PR link alone is insufficient.

## Validation limits

An independent local trial read the skill and used a synthetic preconstructed P/D configuration with the available platform's pure renderers. It produced field guidance, templates, node launch material, proxy dependencies, and textual differences; shell and Python syntax checks passed without executing the generated launch code. The trial exposed a calculator intermediate value that must be followed through launcher arguments before describing the final per-engine value; the definition now makes that distinction explicit.

That local trial is not a published reproducible runtime case. Its platform source correspondence to a deployed version is unverified, and no normal task's configuration, generated files, and logs were correlated. Real environment loading, variable expansion, CLI compatibility, startup, readiness, model correctness, and platform/agent runtime equivalence remain unverified. Local artifacts and platform implementation files are not included in this catalogue submission. The entry therefore remains `validation.status: not-recorded` with no cases; this contribution does not complete all acceptance criteria of Issue #5.
