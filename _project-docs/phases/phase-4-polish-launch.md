
# Phase 4: Polish & Launch Preparation

## Scope
Perform final optimizations, bug fixes, and full AWS deployment. Create docs/demos quantifying improvements (e.g., time savings). Builds to polished, deployable product.

## Deliverables
- Optimized app with tests.
- AWS ECS deployment.
- Before/after demo (videos/screenshots/metrics).
- Migration/docs in docs/.

## Tasks/Features
### Task 1: Testing and Polish
1. Run full tests (bin/test, Cypress for Volto).
2. Fix bugs/optimize (e.g., async in Python 3.11+).
3. Polish UI per ui-rules.md/theme-rules.md.
4. Verify all synergies/no-breakage.
5. Benchmark metrics (e.g., 40% planning reduction).

### Task 2: AWS Deployment
1. Configure ECS task (EFS for ZODB).
2. Deploy 'edu-plone' image.
3. Set up load balancing/SSL.
4. Test cloud instance.
5. Document deployment guide.

### Task 3: Demo and Documentation
1. Capture 'before' (original-plone) vs. 'after' (edu-plone) demos.
2. Quantify improvements per project-overview.md.
3. Write migration notes/user guides.
4. Final commit to 'edu-plone'.
5. Prepare ai-usage.md (prompts).

## Impacted Files and Directories
- **Directories**: tests/ (suites), docs/ (guides/demos), root (AWS configs).
- **Files**: tests/test_all_features.py (comprehensive); docs/deployment-guide.md, docs/migration-notes.md, docs/ai-usage.md; Dockerfile (updates), ecs-task.json (AWS); demo files in docs/ (e.g., before-after.mp4).
- **Reasons**: Polish expands tests/docs; AWS extends deployment.

**Review Checklist**:
- Run full tests and fix issues.
- Verify optimizations (e.g., benchmarks).
- Test AWS deployment.
- Confirm demos show metrics.
- Final commit/push.

## Rules Adherence
- Follow project-rules.md (e.g., <500 lines files).
- Preserve core: Final tests ensure no breakage.
- Deploy per tech-stack.md (Docker/AWS).

## Iteration Notes
Completes relaunch-ready app; full project delivered. 