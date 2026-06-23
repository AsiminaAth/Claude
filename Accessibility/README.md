# Complete orchestration prompt with: 10 Parallel Sub-Agents

Use this prompt file to audit accessibility in your repo's components.
When it finishes it will generate a report alongside with suggestions to improve if needed. You can choose the report's format (e.g in Markdown or JSON).

## List of Sub-Agents

- Semantic HTML - structure correctness
- ARIA Compliance - ARIA attributes & roles
- Keyboard Navigation - Tab, Enter, Escape operability
- Screen Reader Support - accessibility announcements
- Color & Contrast - WCAG contrast ratios
- Focus Management - focus trap, return, visibility
- Motion & Animation - flashing, prefers-reduced-motion
- Language & Structure - clarity, headings, reading order
- Form Accessibility - labels, errors, required fields
- Media & Image - alt text, captions, transcripts

## Key Features

- WCAG 2.2 with all levels (A, AA, AAA)
- Hybrid execution - all agents run simultaneously
- Dual output - developer chooses Markdown OR JSON
- Dual platform - works with Claude Code + Claude API - Remediation included - not just "issue found," also "here's the fix"
- Severity levels - Critical, High, Medium, Low
- Specific criteria links - each issue maps to WCAG criterion

## How to Use

- _Save this file as accessibility-audit-agent.md in your project_
(optional):
- _You may want to add the instruction below to your Claude configuration:_
    '[context]
    include: accessibility-audit-agent.md'

_Claude Code:_
'@claude audit accessibility path/to/component.tsx --format markdown'
OR
'@claude audit accessibility path/to/component.tsx --format JSON'

_Claude API:_
Paste full prompt + component code → specify format ('JSON' or 'Markdown')

### Severity Definitions

- Critical: Blocks access or creates major barriers for users with disabilities. Fails Level A criteria.

- High: Significantly impacts usability. Fails Level AA criteria or causes confusion.

- Medium: Reduces efficiency or clarity. Fails Level AAA criteria or creates minor friction.

- Low: Minor improvements recommended. Best practices beyond WCAG or minor UX enhancements.

### Notes

1. _Latest WCAG: Always reference WCAG 2.2 (released in 2023)_
2. _All Levels: Audit against AA and AAA where applicable_
3. _Hybrid Execution: Sub-agents run in parallel, then consolidated_
4. _Dual Output: Developer chooses Markdown or JSON based on workflow needs_
5. _Context-Aware: Ignore irrelevant sub-agents (e.g., Form Auditor for non-form components, but run by default)_