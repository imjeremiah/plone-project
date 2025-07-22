
# Phase 1: Legacy System Mastery

## Scope
Analyze and map Plone's core architecture/business logic (e.g., ZODB flows, ZCA components, workflows) on the 'edu-plone' branch. Reproduce base functionality for the 'before' state comparison. Builds on Phase 0's setup, delivering documented insights without changes.

## Deliverables
- Architecture map (e.g., ZODB/ZCA diagrams).
- Tested reproduction of core flows (e.g., content creation/publishing).
- 'Before' demo snapshot on 'original-plone' branch.

## Tasks/Features
### Task 1: Architecture Mapping
1. Review plone-overview.md/tech-stack.md for layers (frontend/backend/database).
2. Map ZODB flows (e.g., object persistence).
3. Document ZCA components (interfaces/adapters/utilities).
4. Outline workflows/permissions.
5. Save maps in docs/ (per project-rules.md).

### Task 2: Reproduce Base Functionality
1. Run instance from Phase 0.
2. Test core flows (e.g., add/view content per plone-user-flow.md).
3. Verify no breakage (bin/test).
4. Document pain points for teachers (e.g., fragmentation).
5. Commit to 'edu-plone'; tag 'before' state.

## Impacted Files and Directories
- **Directories**: docs/ (for new maps/notes), tests/ (if running tests).
- **Files**: New Markdown in docs/ (e.g., architecture-map.md, pain-points.md); plone-overview.md/tech-stack.md (read-only); bin/test (run, no edit); Git files (commits/tags on 'edu-plone').
- **Reasons**: Mapping creates docs; testing accesses but doesn't modify core.

**Review Checklist**:
- Verify maps accurately reflect Plone core.
- Run bin/test with no failures.
- Confirm 'before' tag on branch.
- Ensure all touches are read-only or new (no core changes).
- Commit docs to 'edu-plone'.

## Rules Adherence
- Use project-rules.md naming (e.g., docs/ for maps).
- Preserve all: No code changes—pure analysis.
- Tech boundaries: Focus on Volto for UI mapping.

## Iteration Notes
Provides baseline for Phase 2 foundation; 'before' state ready for demos. 