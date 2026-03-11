# Changelog

All notable changes to Writers Room Story Engine will be documented in this file.

## v1.0.1

Packaging and registry-entry update.

### Added
- `SKILL.md` as the primary skill entrypoint for registries and runners

### Changed
- repositioned the package around orchestration-first architecture
- designated `MEGA-SKILL.md` as the fallback one-file version
- updated `README.md` to reflect `SKILL.md` as the main entrypoint
- simplified the public package structure for cleaner registry submission and GitHub presentation

### Removed
- `AGENT-BOSS-INSTRUCTIONS.md` as a redundant top-level entrypoint after moving orchestration into `SKILL.md`

## v1.0.0

Initial release of the Writers Room Story Engine package.

### Added
- `README.md`
- `AGENT-BOSS-INSTRUCTIONS.md`
- `TEST-PROMPTS.md`
- `PACKAGE-DESCRIPTION.md`
- `SOURCES.md`
- `CHANGELOG.md`
- `MEGA-SKILL.md`

### Added story-suite skills
- `story-suite/designing-stories.md`
- `story-suite/creating-story-foundations.md`
- `story-suite/building-storyworlds.md`
- `story-suite/writing-story-scenes.md`
- `story-suite/revising-stories.md`

### Added prompt files
- `prompts/system-prompt-writers-room-story-engine.md`
- `prompts/workflow-order.md`

### Included framework features
- audience-first story design
- story core and ending-direction development
- protagonist engine using want, need, lie, ghost, spine, comfort zone, pressure, and stakes
- Story Spine compression and structure testing
- therefore/but causal beat building
- worldbuilding in service of story pressure
- scene construction built around objective, obstacle, pressure, subtext, and turn
- revision workflows focused on highest-level story failure first
- optional mythic overlay for transformational or adventure stories
- modular skill routing through an orchestrator
- mega-skill fallback for simple testing and one-file deployment

### Design goals
- help agents create compelling stories from zero
- prevent agents from jumping straight into prose before structure exists
- encourage causal plotting over episodic plotting
- keep worldbuilding tied to conflict and choice
- improve revision honesty and structural diagnosis
- support both modular workflow use and one-file testing use