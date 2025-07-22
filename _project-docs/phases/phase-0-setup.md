
# Phase 0: Barebones Setup

## Scope
This phase establishes the foundational setup of the Plone 6.1 instance, creating a minimal running framework without custom features. It sets up the 'before' state (original Plone) for comparison and forks for development. The output is a basic, functional CMS that isn't fully usable for teachers yet but serves as the starting point.

## Deliverables
- Installed Plone 6.1 instance running locally.
- Git repo forked with 'original-plone' branch (untouched 'before' state) and 'edu-plone' branch for enhancements.
- Basic verification (e.g., create/test a sample page).

## Tasks/Features

### Task 1: Environment and Installation
1. Install prerequisites (Python 3.11, Node.js) per plone-tech-stack.md.
2. Create project directory and virtual environment.
3. Install Plone via pip or buildout (setup.cfg rules).
4. Start instance and create site (localhost:8080).
5. Verify base functionality (login, add content).

### Task 2: Repo Forking and Branching
1. Fork Plone repo on GitHub.
2. Clone locally into project dir.
3. Create 'plone-project' branch for before state.
4. Create 'edu-plone' branch for after/development.
5. Commit initial setup to both.

## Impacted Files and Directories
- **Directories**: Root (project dir creation), venv/ (virtual env), src/ (from clone).
- **Files**: setup.py, setup.cfg, pyproject.toml (install/config); .git (for branches/commits); Dockerfile, docker-compose.yml (if prepping deployment, but minimal here).
- **Reasons**: Installation touches config for setup; forking/cloning creates base structure without custom changes.

**Review Checklist**:
- Verify installation succeeds without errors.
- Run basic instance test (e.g., access localhost:8080).
- Confirm branches ('original-plone' untouched, 'edu-plone' ready).
- Ensure no core Plone files modified.
- Commit and push to repo.

## Rules Adherence
- Follow project-rules.md: Use src/ for code, setup.py/cfg for config.
- Preserve core: No modifications yet—pure Plone.
- Tech boundaries: Stick to plone-tech-stack.md (e.g., Zope/ZODB).

## Iteration Notes
Builds to Phase 1 by providing a baseline instance for mastery/analysis. Functional but minimal—no teacher-specific features. 