
# Plone User Journey Overview

This document outlines a typical user journey through Plone CMS, derived exclusively from the features, architecture, and capabilities described in plone-overview.md. It segments the journey into logical phases, highlighting how key features (e.g., content types, workflows, search, security) interconnect. The journey is generalized across user roles (e.g., viewers, editors, managers) with a slight emphasis on the end-user view (e.g., content discovery and viewing). It focuses primarily on the Volto React frontend, with backend components (Zope, ZODB) supporting all interactions. Granularity mixes high-level overviews with selected detailed steps.

## 1. Onboarding and Authentication
- **Entry Point**: User (e.g., end-user viewer) accesses the Plone site via browser (HTTP/REST API if headless).
- **Key Features Involved**:
  - Security System: Pluggable Authentication (e.g., LDAP, SAML, OAuth) for login.
  - Role/Permissions: Fine-grained access control determines available actions (e.g., view-only for end-users).
- **Detailed Steps** (Mix): Enter credentials; system verifies via security framework; grants session-based access.
- **Connections**: Links to Internationalization (multilingual interface) and Accessibility (WCAG-compliant login forms). Successful login directs to Volto React UI.
- **Next Segment**: Proceeds to navigation, emphasizing end-user content discovery.

## 2. Navigation and Content Discovery
- **Entry Point**: Post-login, user (emphasizing end-user viewer) lands on homepage or navigation structure in Volto React UI.
- **Key Features Involved**:
  - Navigation: Breadcrumbs, site structure via Zope traversal.
  - Search/Indexing: Portal Catalog for queries, full-text search, custom indexes.
- **Detailed Steps** (Mix): Browse hierarchy using Volto components; perform search with filters; view results with previews.
- **Connections**: Search integrates with Content Types (e.g., filtering viewable items) and Multilingual support (language-specific results). Accessibility ensures keyboard navigation and semantic HTML for end-users.
- **Next Segment**: User selects content for viewing, core to end-user experience.

## 3. Content Viewing and Interaction
- **Entry Point**: End-user selects a content item from navigation or search results in Volto React UI.
- **Key Features Involved**:
  - Content Types: Display of Dexterity-based items (e.g., schemas, behaviors).
  - Frontend: Volto (blocks system for composition, emphasizing React-based viewing).
  - Security: Permissions check for viewing (e.g., CSRF protection).
- **Detailed Steps** (Mix): Load item; render blocks (e.g., text, images); interact via comments if permitted.
- **Connections**: Relates to Workflow Engine (shows current state, e.g., published for viewing) and Content Relations (linked objects). Internationalization handles translations; Accessibility ensures screen reader compatibility for end-users.
- **Next Segment**: If editor role, proceed to editing; for viewers, cycle back to discovery.

## 4. Content Creation and Editing
- **Entry Point**: User (generalized, but noting viewer limitations) initiates creation via Volto React add menu or TTW tools.
- **Key Features Involved**:
  - Content Types/Schemas: Dexterity for schema-driven creation, behaviors for reusable functionality.
  - Fields/Widgets: 40+ types for input (e.g., rich text).
  - Volto Blocks: Drag-and-drop composition.
  - TTW Capabilities: Through-the-web content type creation and schema editing.
- **Detailed Steps** (Mix): Select type; fill fields/widgets; compose with blocks; save draft.
- **Connections**: Integrates with Workflow (initial state assignment) and Security (permission checks). Content Rules can automate actions (e.g., email on creation). Links to Versioning for history.
- **Next Segment**: Move to workflow for publishing, connecting back to viewer access.

## 5. Workflow and Publishing
- **Entry Point**: After creation/editing, user applies workflow actions, affecting end-user visibility.
- **Key Features Involved**:
  - Workflow Engine: State machine with transitions, permissions, and custom workflows.
  - Bulk Operations: Mass state changes.
  - Content Locking: Prevent concurrent edits.
- **Detailed Steps** (Mix): Select transition (e.g., submit for review); system applies permissions; update state.
- **Connections**: Ties back to Security (role-based transitions) and Content Features (e.g., working copies for collaboration, versioning for rollback). Affects Search (e.g., only published items viewable by end-users).
- **Next Segment**: Published content available for viewing/discovery.

## 6. Collaboration and Management
- **Entry Point**: User manages items or collaborates, supporting end-user sharing.
- **Key Features Involved**:
  - Content Rules: Event-driven automation (e.g., move/copy on events).
  - Working Copy Support: Check-in/check-out for editing.
  - Collections: Smart folders with criteria.
  - Audit Trail: Action logging.
- **Detailed Steps** (Mix): Set up rules; create working copy; manage collections for grouped viewing.
- **Connections**: Integrates with Workflow (state-based rules) and Search (faceted queries on collections). Security ensures role-based access; Multilingual for shared content.
- **Next Segment**: Administrative tasks if elevated role, or back to viewing.

## 7. Search and Advanced Querying
- **Entry Point**: User (emphasizing end-user) performs searches from any segment in Volto React.
- **Key Features Involved**:
  - Search/Indexing: ZCatalog for performance, text indexing, custom indexes.
  - External Search: Integration options (e.g., Solr).
- **Detailed Steps** (Mix): Enter query; apply filters; browse paginated results.
- **Connections**: Pulls from Content Types (indexed fields), Workflow (state filtering), and Relations (linked results). Enhances end-user discovery in navigation.
- **Next Segment**: Returns to viewing based on results.

## 8. Administration and Configuration
- **Entry Point**: Admin users access control panels in Volto React or ZMI, indirectly supporting end-user experience.
- **Key Features Involved**:
  - TTW: Workflow editor, schema editor, control panels.
  - Security: User/group management, roles/permissions.
  - Deployment: Scaling via ZEO, caching.
- **Detailed Steps** (Mix): Navigate to panels; edit workflows/schemas; manage users/roles.
- **Connections**: Affects all segments (e.g., custom workflows impact publishing and viewing). Integrates with Database Layer (ZODB management) and Internationalization (language setup).
- **Next Segment**: Cycles back to core usage or logout.

## 9. Logout and Session End
- **Entry Point**: User logs out or session expires.
- **Key Features Involved**: Security System (session management, CSRF cleanup).
- **Detailed Steps** (Mix): Click logout; system clears session; redirect to login.
- **Connections**: Ensures audit trail logging; preserves state in ZODB for next login.

This journey is cyclical, with search/navigation (emphasizing end-user discovery) connecting all segments. Features interconnect via Plone's component architecture (ZCA), ensuring modularity (e.g., workflows influence search visibility and viewing). 