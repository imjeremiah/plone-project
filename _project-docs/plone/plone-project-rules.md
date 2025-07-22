
# Project Rules for Educational Content Platform

This document defines rules for directory structure, file naming, and other guidelines in our AI-first modernization of Plone (1M+ lines legacy codebase). It ensures modularity, scalability, and navigability for AI tools (e.g., semantic search, code exploration). Rules promote compatibility with Volto frontend, ZCA for extensions, and no breakage to core Plone functionality (e.g., workflows, ZODB). Derived from project docs for consistency.

## Directory Structure
Structure follows Plone/Volto conventions for add-ons, emphasizing separation of concerns (backend Python/Zope, frontend React/Volto) to aid scalability (e.g., ZEO clustering) and AI navigability (e.g., clear folders for components/behaviors).

- **Root Level**:
  - `src/`: Core source code (Python/JS).
  - `docs/`: Documentation (e.g., user-flow.md, ui-rules.md).
  - `tests/`: Unit/integration tests (plone.testing for backend, Jest/Cypress for Volto).
  - `setup.py` / `setup.cfg` / `pyproject.toml`: Package config (PEP 621 standards).
  - `Dockerfile` / `docker-compose.yml`: For containerized deployment (AWS ECS compatibility).

- **Backend (Plone/Zope Extensions)**:
  - `src/plone_addon/`:
    - `content/`: Custom content types (Dexterity schemas).
    - `behaviors/`: Reusable behaviors (e.g., standards alignment).
    - `vocabularies/`: Dropdown options (e.g., Common Core tags).
    - `workflows/`: Custom workflow definitions.
    - `profiles/`: Installation profiles (GenericSetup).
    - `rest/`: API extensions (plone.restapi serializers).

- **Frontend (Volto React)**:
  - `src/volto-addon/`:
    - `components/`: Reusable React components (e.g., dashboard blocks).
    - `blocks/`: Custom Volto blocks (e.g., standards tagging block).
    - `views/`: Content type views (e.g., lesson display).
    - `theme/`: Styling (LESS/CSS Modules, overrides).
    - `reducers/`: Redux state management (e.g., analytics metrics).
    - `actions/`: Redux actions (e.g., Google sync).

- **Best Practices for Structure**: Use ZCA for modularity (register components in ZCML); separate concerns (e.g., API in rest/ for headless); scale with ZEO/RelStorage in deployment folders.
- **Scalability Considerations**: Folders support horizontal scaling (e.g., multiple Volto instances); avoid deep nesting for AI navigability.

## File Naming Conventions
Conventions ensure consistency, readability, and AI tool compatibility (e.g., semantic search on names).

- **General**:
  - Lowercase with underscores (snake_case) for Python files (e.g., standards_behavior.py).
  - CamelCase for JS/React components (e.g., StandardsTagger.jsx).
  - Descriptive names: Prefix with purpose (e.g., lesson_content_type.py, search_block.jsx).
  - Extensions: .py (Python), .jsx (React), .less (styles), .md (docs), .zcml (configs).

- **Specific Rules**:
  - Interfaces: I prefix (e.g., IStandardsAlignment.py).
  - Tests: test_ prefix (e.g., test_search.py).
  - Configs: setup.py, rules.xml (theming), manifest.cfg.
  - Docs: Hyphenated lowercase (e.g., user-flow.md).

- **Best Practices**: Use consistent casing; include docstrings/comments for AI understanding; version files if needed (e.g., via Git).
- **Pitfalls to Avoid**: Inconsistent naming hindering search; overly generic names (e.g., use google_sync_action.js not util.js).

## Other Rules and Guidelines
Additional rules cover coding, integration, and AI-first practices to maintain legacy compatibility while modernizing.

- **Modularity and Extensibility**:
  - Use ZCA (interfaces/adapters) for backend; Volto shadowing for frontend overrides.
  - Rule: Extend via add-ons—never modify core Plone files to avoid breakage.
  - Consideration: Ensure features integrate synergistically (e.g., standards alignment enhances search/dashboard per user flows).

- **Scalability and Performance**:
  - Leverage ZODB MVCC/caching (plone.memoize); use Docker for AWS deployment.
  - Rule: Optimize queries (e.g., batch API calls in Volto); pack ZODB regularly.
  - Pitfall: Unoptimized indexes causing slow search in large educational datasets.

- **UI/Theme Consistency**:
  - Follow ui-rules.md (e.g., accessibility-first, responsive) and theme-rules.md (e.g., primary #007eb6).
  - Rule: Use Semantic UI classes; test responsiveness for mobile lesson planning.

- **AI-First Engineering**:
  - Rule: Keep files <500 lines; use clear docstrings/parameters for functions (e.g., describe purpose/params in code).
  - Consideration: Structure for navigability (e.g., one concern per file); comment interconnections (e.g., how a block links to workflow).
  - Pitfall: Dense code without comments limiting AI-assisted debugging.

- **Testing and Preservation**:
  - Rule: Run bin/test after changes; ensure no breakage to core (e.g., workflows, permissions).
  - Consideration: Align with user journeys (e.g., test cyclical flows in Volto).

These rules enable easy understanding/navigation of the codebase, supporting our AI-first approach in this legacy modernization. 