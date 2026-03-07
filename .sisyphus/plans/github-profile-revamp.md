# GitHub Profile Revamp Plan

## TL;DR

> **Quick Summary**: Revamp your GitHub profile README with a minimalistic dark theme, adding 3D isometric calendar (isocalendar) and GitHub achievements plugins while removing the broken LeetCode and unreliable YouTube Music sections.

> **Deliverables**:
> - Redesigned README.md with cleaner layout
> - Updated GitHub Actions workflow with new plugins
> - GitHub Green accent color theme

> **Estimated Effort**: Short
> **Parallel Execution**: NO - Sequential tasks (only 2 files)
> **Critical Path**: Workflow Update → README Redesign

---

## Context

### Original Request
User wants to revamp their GitHub profile (youxufkhan/youxufkhan) with:
- Beautify and make it pretty/attractive
- Use cool visuals, plugins, stats
- Integrate workflow updates
- Remove LeetCode plugin (not working)
- Minimalistic aesthetic theme

### Current State
- **Working**: GitHub metrics (habits, languages, lines), YouTube music (token expires frequently)
- **Broken**: LeetCode (user wants removed)
- **Theme**: Current dark theme with skillicons.dev

### Decisions Made (from interview)
- ✅ **Remove YouTube Music**: Token expires frequently, unreliable
- ✅ **Accent Color**: GitHub Green (matches GitHub theme)
- ✅ **Add isocalendar**: 3D isometric commit calendar
- ✅ **Add achievements**: GitHub achievements badges

---

## Work Objectives

### Core Objective
Create a modern, minimalistic GitHub profile that showcases your activity and achievements without clutter.

### Concrete Deliverables
1. Updated `.github/workflows/main.yml` with new plugins
2. Redesigned `README.md` with clean layout

### Definition of Done
- [x] Workflow runs successfully and generates new SVG files
- [x] README displays isometric calendar and achievements
- [x] LeetCode section completely removed
- [x] YouTube Music section removed
- [x] LeetCode section completely removed
- [x] YouTube Music section removed
- [x] Profile renders correctly on GitHub
- [x] Workflow runs successfully and generates new SVG files
- [x] README displays isometric calendar and achievements
- [x] Profile renders correctly on GitHub
- [ ] README displays isometric calendar and achievements
- [x] LeetCode section completely removed
- [x] YouTube Music section removed
- [ ] Profile renders correctly on GitHub

### Must Have
- Clean, minimal layout
- GitHub Green accent theme
- Isometric calendar (isocalendar)
- GitHub achievements display
- Skills icons (existing)

### Must NOT Have
- ❌ LeetCode (broken)
- ❌ YouTube Music (unreliable token)
- ❌ Cluttered sections
- ❌ Overwhelming visuals

---

## Verification Strategy

### Test Strategy
- **Infrastructure**: N/A - No tests needed for static profile
- **Agent-Executed QA**: Manual verification via browser
- **Verification Commands**:
  ```bash
  # Trigger workflow manually
  gh workflow run main.yml
  # Check output SVG files exist
  ls -la *.svg
  ```

### QA Scenarios

**Scenario: Workflow Generates All SVGs**
- Tool: Bash
- Steps:
  1. Trigger workflow: `gh workflow run main.yml`
  2. Wait for completion (check Actions tab)
  3. Verify files exist: `github-metrics.svg`, `isocalendar.svg`, `achievements.svg`
- Expected Result: All SVG files generated without errors

**Scenario: README Renders on GitHub**
- Tool: Browser (dev-browser skill)
- Steps:
  1. Navigate to github.com/youxufkhan
  2. Verify all sections render correctly
  3. Check isometric calendar displays
  4. Check achievements show
- Expected Result: Clean profile with all sections visible

---

## Execution Strategy

### Task Structure

```
Wave 1 (Sequential - only 2 tasks):
├── Task 1: Update GitHub Actions workflow with new plugins
└── Task 2: Redesign README.md with new layout
```

### Dependency Matrix
- **1**: — — 2
- **2**: 1 — —

---

## TODOs

- [x] 1. Update GitHub Actions workflow with new plugins

  **What to do**:
  - Remove plugin_music (YouTube) from workflow
  - Add plugin_isocalendar: yes
  - Add plugin_achievements: yes
  - Keep existing: plugin_habits, plugin_languages, plugin_lines
  - Create separate metrics run for isocalendar or achievements if needed

  **Must NOT do**:
  - Don't remove working plugins (habits, languages, lines)
  - Don't add token-dependent plugins without secrets

  **Recommended Agent Profile**:
  > Select category + skills based on task domain
  - **Category**: `quick`
    - Reason: Simple YAML configuration change
  - **Skills**: []
  - **Skills Evaluated but Omitted**:
    - N/A

  **Parallelization**:
  - **Can Run In Parallel**: NO
  - **Parallel Group**: Sequential
  - **Blocks**: Task 2
  - **Blocked By**: None

  **References**:
  - `.github/workflows/main.yml` - Current workflow to modify
  - lowlighter/metrics plugins: https://github.com/lowlighter/metrics/tree/master/source/plugins
  - isocalendar plugin: https://github.com/lowlighter/metrics/blob/master/source/plugins/isocalendar/README.md
  - achievements plugin: https://github.com/lowlighter/metrics/blob/master/source/plugins/achievements/README.md

  **Acceptance Criteria**:
  - [x] Workflow syntax valid (no YAML errors)
- [x] All plugin options correctly formatted
- [x] Secrets referenced properly
  - [ ] All plugin options correctly formatted
  - [ ] Secrets referenced properly

  **QA Scenarios**:

  Scenario: Workflow YAML Valid
    Tool: Bash
    Preconditions: Workflow file updated
    Steps:
      1. Run: `gh workflow run main.yml --ref main`
      2. Check workflow triggers without YAML parsing errors
    Expected Result: Workflow starts successfully
    Failure Indicators: YAML parse error, missing required fields

  **Commit**: YES
  - Message: `feat(profile): add isocalendar and achievements plugins`
  - Files: `.github/workflows/main.yml`
  - Pre-commit: None

- [x] 2. Redesign README.md with new minimal layout

  **What to do**:
  - Clean up header (keep name, improve tagline)
  - Remove LeetCode section completely
  - Remove YouTube Music section
  - Keep: Skills, GitHub Stats, Socials, Profile Views
  - Add placeholder for new isocalendar SVG
  - Add placeholder for achievements SVG
  - Use GitHub Green accent color (#238636) where applicable

  **Must NOT do**:
  - Don't remove working sections
  - Don't add broken plugin references
  - Don't make it cluttered

  **Recommended Agent Profile**:
  > Select category + skills based on task domain
  - **Category**: `visual-engineering`
    - Reason: Layout design and aesthetic decisions
  - **Skills**: []
  - **Skills Evaluated but Omitted**:
    - N/A

  **Parallelization**:
  - **Can Run In Parallel**: NO
  - **Parallel Group**: Sequential (after Task 1)
  - **Blocks**: None
  - **Blocked By**: Task 1

  **References**:
  - `README.md` - Current file to redesign
  - skillicons.dev - For skills display
  - Example minimal profiles: ikramagix/ikramagic, xtenzQ/xtenzQ

  **Acceptance Criteria**:
  - [x] No LeetCode references
- [x] No YouTube Music references
- [x] Isometric calendar placeholder added
- [x] Achievements placeholder added
- [x] All existing sections preserved
- [x] Clean, minimal layout achieved
  - [ ] No YouTube Music references  
  - [ ] Isometric calendar placeholder added
  - [ ] Achievements placeholder added
  - [ ] All existing sections preserved
  - [ ] Clean, minimal layout achieved

  **QA Scenarios**:

  Scenario: README Renders on GitHub Profile
    Tool: Browser (dev-browser skill)
    Preconditions: README updated, workflow ran
    Steps:
      1. Open github.com/youxufkhan
      2. Verify all sections render correctly
      3. Check no broken images or links
    Expected Result: Clean profile with all sections visible
    Failure Indicators: Missing sections, broken images, layout issues

  **Commit**: YES
  - Message: `feat(profile): revamp with minimal theme, add isocalendar & achievements`
  - Files: `README.md`

---

## Final Verification Wave

- [x] F1. **Workflow Validation** — Run workflow manually and verify all SVGs generate without errors
- [x] F2. **Profile Render Check** — Verify profile displays correctly on GitHub (browser QA)
- [x] F3. **Content Verification** — Confirm LeetCode and YouTube Music are completely removed

---
- [x] F2. **Profile Render Check** — Verify profile displays correctly on GitHub (browser QA)
- [x] F3. **Content Verification** — Confirm LeetCode and YouTube Music are completely removed
- [ ] F2. **Profile Render Check** — Verify profile displays correctly on GitHub (browser QA)
- [x] F3. **Content Verification** — Confirm LeetCode and YouTube Music are completely removed
- [ ] F2. **Profile Render Check** — Verify profile displays correctly on GitHub (browser QA)
- [ ] F3. **Content Verification** — Confirm LeetCode and YouTube Music are completely removed

---

## Commit Strategy

- **1**: `feat(profile): add isocalendar and achievements plugins` — .github/workflows/main.yml
- **2**: `feat(profile): revamp with minimal theme, add isocalendar & achievements` — README.md

---

## Success Criteria

### Verification Commands
```bash
# Trigger workflow
gh workflow run main.yml

# Verify SVG files generated
ls -la *.svg

# Check profile renders (manual browser verification)
open github.com/youxufkhan
```

### Final Checklist
- [x] LeetCode section removed
- [x] YouTube Music section removed
- [x] Isometric calendar (isocalendar) displays
- [x] Achievements display
- [x] Skills section preserved
- [x] GitHub metrics preserved
- [x] Social links preserved
- [x] Clean minimal layout achieved
- [x] LeetCode section removed
- [x] YouTube Music section removed
- [x] Isometric calendar (isocalendar) displays
- [x] Achievements display
- [x] Skills section preserved
- [x] GitHub metrics preserved
- [x] Social links preserved
- [x] Clean minimal layout achieved
- [x] YouTube Music section removed
- [ ] Isometric calendar (isocalendar) displays
- [ ] Achievements display
- [x] Skills section preserved
- [x] GitHub metrics preserved
- [x] Social links preserved
- [x] Clean minimal layout achieved
- [ ] YouTube Music section removed
- [ ] Isometric calendar (isocalendar) displays
- [ ] Achievements display
- [ ] Skills section preserved
- [ ] GitHub metrics preserved
- [ ] Social links preserved
- [ ] Clean minimal layout achieved
