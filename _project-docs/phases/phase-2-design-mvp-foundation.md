
# Phase 2: Modernization Design & Foundation

## Scope
Design API-first architecture with Volto, set up deployment pipeline (local Docker), add Features 1/2/4 for core usability. Builds on Phase 1 to deliver MVP: Basic lesson planning with auth/standards/mobile. Functional for minimal teacher use.

## Deliverables
- Linked Volto frontend to Plone backend.
- Local Docker setup.
- Integrated Features 1/2/4 with tests.
- Updated 'after' instance for comparison.

## Tasks/Features
### Task 1: API-First and Volto Setup
1. Enable plone.restapi.
2. Set up Volto project (npm init).
3. Link Volto to backend (configure API endpoints).
4. Test basic flows in Volto (e.g., login/view).
5. Commit to 'edu-plone'.

### Feature 1: Modern Authentication (OAuth/SSO with Google)
1. Install PAS plugin for OAuth.
2. Configure Google SSO credentials.
3. Integrate with Volto login component.
4. Test secure access (preserve acl_users).
5. Verify no breakage (bin/test).

### Feature 2: Standards Alignment System
#### Sub-Feature 2.1: Taxonomy Setup
1. Create vocabulary using plone.app.vocabularies.
2. Define Common Core terms.
3. Register as utility in ZCML.
#### Sub-Feature 2.2: Tagging/Tracking
1. Add behavior to content types.
2. Implement Volto widget for tagging.
3. Enable compliance tracking in workflows.
4. Test integration.
5. Run bin/test.

### Feature 4: Mobile-Responsive Design
1. Customize Volto theme (LESS overrides).
2. Apply responsive styles per theme-rules.md.
3. Optimize for tablet (media queries).
4. Test cross-device (emulators).
5. Verify with user-flow.md segments.

### Task 2: Docker Foundation
1. Create Dockerfile for backend.
2. Set up docker-compose.yml (Plone + Volto).
3. Mount volumes for persistence.
4. Test local run.
5. Document basic deployment.

## Impacted Files and Directories
- **Directories**: src/volto-addon/ (components/theme), src/plone_addon/ (behaviors/vocabularies), docs/ (updates), root (deployment).
- **Files**: src/volto-addon/components/login.jsx (Feature 1); src/plone_addon/behaviors/standards.py, src/plone_addon/vocabularies/common_core.py, src/volto-addon/blocks/standards_widget.jsx (Feature 2); src/volto-addon/theme/custom.less (Feature 4); configure.zcml (regs); Dockerfile, docker-compose.yml (Task 2); tests/test_auth.py etc. (verifications).
- **Reasons**: Features create custom extensions; Docker adds root files.

**Review Checklist**:
- Verify features integrate without errors.
- Run bin/test after each addition.
- Test Volto linkage and mobile views.
- Confirm no core breakage.
- Commit to 'edu-plone' and test Docker run.

## Rules Adherence
- Extend via ZCA/add-ons (project-rules.md).
- No breakage: Test after each feature.
- Volto focus per ui-rules.md.

## Iteration Notes
MVP enables core planning; builds to Phase 3 for more features. 