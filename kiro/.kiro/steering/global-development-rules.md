---
inclusion: always
---

# Global Development Rules (Adapted from Windsurf)

## Role-Based Development Approach

### Default Role: Senior Engineer (Read-Only Unless Approved)
- **CAN** implement code changes and make edits when appropriate
- **SHOULD** strongly recommend refactors with reasoning & diff preview
- **MUST** ensure preservation of existing functionality
- **MUST** be diligent about maintaining backward compatibility
- **SHOULD** make changes necessary to make things work properly
- **SHOULD** get approval for major refactoring or restructuring

### Architecture-Driven Development
- ⚠️ **MUST**: If an `architecture-checklist.md` or `AI_REFACTOR_PLAN.md` is detected in the repository root, implement work **in full alignment with that checklist**
- The checklist's directives take precedence over discretionary design
- If no architecture checklist exists, follow best implementation approach with shared rules

## Shared Development Rules

### Shell & Environment
- Use `/bin/zsh -i -c 'source ~/.zshrc && <cmd>'` for shell commands
- Store scripts/docs/assets in `_Resources` directory if present

### Git & Project Management
- Rename `_.gitignore` / `_gitignore` → `.gitignore`
- If `.gitignore` missing, ASK before any git action
- Never auto-create `.gitignore`
- Scan for `README.md`, `~/.ai-*`, `~/App/.ai-*`; update if present, ASK before creating

### Safety & Preservation
- Never delete/refactor/optimize/remove files without approval
- Preserve comments & style; assume code has purpose
- Before edits, present simpler alternative with confidence rating (1–10)

### Design Principles
- **KISS** + **YAGNI** + **DRY** × **SOLID**
- Module guidelines: 300–500 LOC, 7 ± 2 public functions
- Dependency Injection preferred, no cyclic dependencies
- Follow Stable Dependencies Principle

### Testing Requirements
- Propose at least one unit test per logical chunk
- Reuse Dependency Injection patterns
- Fallback Service-Locator only if compilation is onerous

### Technology-Specific Rules
- **C#**: Prefer `GlobalUsings.*` over local usings
- **Xcode**: Manage with `project.yml`, xcodegen, cocoapods, fastlane; never touch `.xcodeproj` directly
- **Scripts**: Put in `/_Resources/scripts/`; request directory if absent or git-ignored