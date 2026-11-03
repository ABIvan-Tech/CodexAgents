# Codex agent workflows

A local, editable adaptation of [copilot-agentic-workflows](https://github.com/ABIvan-Tech/copilot-agentic-workflows) for Codex. This directory is a source package; editing it does not change the active global Codex configuration.

## Layout

- `AGENTS.md`: proposed global communication and delegation instructions.
- `agents/`: Codex agent TOML files. The default routing uses `explorer` (Luna), `worker` (Terra), `reviewer` (Sol), and `verifier` (Luna). `planner` and `debugger` remain optional specialists for explicit use.
- `skills/`: 10 adapted or imported workflow and engineering skills.

Models and reasoning levels are starting points. Choose identifiers available in your Codex account and validate them with real tasks. Delegation depends on the client, applicable instructions, and current session permissions; instructions do not guarantee an agent will be invoked. Codex-specific behavior follows [the official subagent documentation](https://learn.chatgpt.com/docs/agent-configuration/subagents).

## Installing manually

1. Review the files and compare them with your existing `~/.codex/AGENTS.md`, `~/.codex/agents/`, and `~/.codex/skills/`. Several skills may have the same names as already-installed skills.
2. Merge the desired routing instructions into `~/.codex/AGENTS.md`, preserving your existing instructions.
3. Copy the desired TOML files to `~/.codex/agents/` and skill directories to `~/.codex/skills/`. Resolve naming conflicts deliberately; do not overwrite existing files blindly.
4. Start a new Codex session, confirm that the expected skills and agents are discoverable, and test a small delegated task. Some clients may require a restart to discover changes.

You can instead install skills in a project-supported discovery location when project-specific scope is desired. Do not assume copying this directory alone activates the configuration.

## Adaptation and source

Source: `ABIvan-Tech/copilot-agentic-workflows`, commit `174ce6d30bb610d6640b428c02b2bc02a6704352`. Agent instructions consolidate the source roles into the four-role routing above. Workflow skills were adapted to Codex: they do not assume VS Code tools, a Gemini reviewer, mandatory fan-out, or automatic changes to personal memory. Skill frontmatter was adjusted for Codex. Domain-specific skills retain source guidance; apply their architectural conventions only when suitable for the target project and user request. Recheck version-sensitive guidance before use.

The source repository did not contain a root LICENSE file at the inspected commit, although some source skills referred to one. No license is assigned here on that basis. Some original skills have separate license terms; those skills are not currently present in this directory. Review the provenance and applicable permissions before publishing or selecting a license for this repository.
