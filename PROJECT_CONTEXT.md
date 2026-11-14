# Project Context and Handover

> **Purpose:** This is the durable handover document for transferring project context between ChatGPT conversations, Claude sessions, or human contributors. Read this file first before planning or changing the repository.
>
> **Last audited:** 2026-11-14  
> **Repository:** `JennyJoshua/universal-ebook-publishing-system`  
> **Status:** Architecture/documentation stage; no executable publishing system has been implemented.

## 1. Project identity and purpose

The Universal eBook Publishing System is a reusable, free-first publishing toolchain for producing professional educational and reference eBooks in **PDF and EPUB** formats.

It is a platform/tooling repository, not an individual book repository. It must be reusable by multiple independent book projects. Each book retains ownership of its own research, manuscript, references, assets, editorial decisions, and publication approvals.

The first intended consuming project is:

- `JennyJoshua/png-financial-markets-ebook`

That repository remains separate. Its existing research workflow and phase approvals remain authoritative. The existence of this publishing-system repository does **not** authorize manuscript drafting, production integration, phase advancement, or changes to the Financial Markets repository.

## 2. Current repository state — verified 2026-11-14

### Repository metadata
- GitHub repository: `JennyJoshua/universal-ebook-publishing-system`
- URL: https://github.com/JennyJoshua/universal-ebook-publishing-system
- Visibility: **Public**
- Default branch: `main`
- Connected GitHub account has admin, maintain, and push permissions.
- Repository is not archived.

### Branches and pull request
- `main`: contains only the initial `README.md` at the time of this audit.
- `docs/initial-system-architecture`: contains the initial architecture/documentation package.
- Pull request [#1 — Add initial publishing system architecture and governance](https://github.com/JennyJoshua/universal-ebook-publishing-system/pull/1) is **open and not merged**.
- PR #1 targets `main`; its head branch is `docs/initial-system-architecture`.
- The PR was reported mergeable at the time of inspection.
- PR #1 contains 12 documentation files (438 additions at the initial PR snapshot); this handover file is being added to that branch and will update the PR.
- No review submissions, inline review threads, or PR conversation comments were returned during this audit.
- No merge has been performed.

### Current file inventory on the architecture branch
1. `README.md`
2. `SYSTEM_REQUIREMENTS.md`
3. `ARCHITECTURE.md`
4. `DESIGN_SYSTEM.md`
5. `CONTENT_SCHEMA.md`
6. `PDF_PIPELINE.md`
7. `EPUB_PIPELINE.md`
8. `CANVA_ASSET_GUIDE.md`
9. `ACCESSIBILITY_QA.md`
10. `BUILD_AND_RELEASE.md`
11. `INTEGRATION_CONTRACT.md`
12. `DECISIONS.md`
13. `CHANGELOG.md`
14. `PROJECT_CONTEXT.md` (this handover; added by this audit)

The branch tree contained only Markdown documentation. No executable source code, schema files, LaTeX templates, sample book, scripts, tests, dependency manifests, CI workflows, or generated publishing outputs were present at the time of audit.

## 3. Owner-approved decisions — treat as authoritative

### Architecture
1. **Separate repository:** the reusable system lives here; each book remains in its own repository.
2. **Hybrid publishing architecture:**
   - Structured Markdown is the canonical manuscript source.
   - LaTeX is the primary professional PDF typesetting/build engine.
   - EPUB is produced by a separate reflowable pipeline from the same Markdown source. Do not convert the finished PDF into EPUB.
   - Canva is for visual assets, not the manuscript source or build engine.
   - GitHub is the permanent source of truth, version control, and automation/release coordination point.
3. **Formats:** PDF and EPUB are both required outputs.
4. **Visual direction:** **AB — Modern Editorial foundation with selected Illustrated Learning elements.**
5. **Series identity:** one common series identity with subject-specific accent colours.
6. **Free-first constraint:** no paid service, API, or mandatory proprietary authoring platform in the baseline workflow.
7. **Repository visibility:** public.

### Design direction
- Core palette: deep navy/ink, warm neutral paper/background tones, restrained grey, and one subject accent.
- Financial Markets is the first reference subject and uses a muted teal accent.
- Use illustration to explain concepts rather than as decoration.
- Keep layouts readable, accessible, print-aware for PDF, and reflow-friendly for EPUB.

### Governance and scope boundaries
- Do not automatically publish or release a book.
- A successful CI build is not publication approval.
- Keep the Financial Markets book's research and editorial process in its own repository.
- Figma is optional and paused; it is not a dependency.
- Overleaf compatibility has not been verified and is not a dependency.
- The final Canva template has not been selected.

## 4. User operating and collaboration requirements

These constraints matter when proposing implementation steps or handovers:

- The owner prefers free tools, existing accounts, and no paid APIs/services.
- The owner currently works from an Android phone and prefers workflows that do not require desktop-only setup, installs, screenshots, or repetitive manual copying.
- Give clear, sequential, one-step-at-a-time instructions when owner action is needed.
- ChatGPT's role is Chief Planner/Architect and reviewer: requirements, architecture, phases, module breakdown, dependencies, acceptance criteria, audit, review, and handover.
- Claude's mobile/cloud conversational app may implement approved work and return ZIP files. Do not assume Claude Code desktop, direct repository access, or a connected GitHub account.
- If a ZIP handover is used, it should contain repository-relative files without an enclosing wrapper folder, and must not overwrite protected paths or workflow files without explicit approval.
- Routine, low-risk work can proceed after clear authorization. Stop and obtain explicit approval before main merges, production deployments/publication, destructive actions, paid services, material scope changes, or repeated failure/retry loops.
- Do not merge PR #1 or any later PR merely because it is technically mergeable. Owner review/approval is required.

## 5. Canva workspace and prior visual exploration

Canva folder:
https://www.canva.com/folder/FAHakry9ipY

Four editable exploratory candidates were created:
1. https://www.canva.com/d/Z8iATR1V3bGMc40
2. https://www.canva.com/d/3sd9OCZJ3bOfvsv
3. https://www.canva.com/d/bE2MQrWWYtdIpcn
4. https://www.canva.com/d/ST8xvHe6YmEMxGM

None is approved as the final system template. Treat them as exploratory references only. No Brand Kit was found during the earlier check. Canva is optional: exported, approved assets must be committed to the relevant book repository so builds do not require Canva access.

## 6. Prior feasibility test — do not overstate it

A previous conversation reported a small LaTeX PDF sample compiled locally and a separate EPUB generated from Markdown. The PDF included a sample cover, contents/chapter opening, educational text, key-idea box, simple market-flow diagram, comparison table, and references.

Important qualifications:
- The test used a local LaTeX engine, not Overleaf.
- The PDF and EPUB were generated as separate outputs from separate source preparation; a synchronised shared-source pipeline was not proven.
- Those test files are not part of this repository's current tree.
- The earlier experiment is a feasibility signal only. It does not prove that this repository has a working build system, that the process is reproducible from a clean checkout, or that Overleaf compatibility exists.
- Do not claim Overleaf was tested.

## 7. Audit findings and assessment

### Overall assessment
**The repository is a sound initial architecture/documentation scaffold, not yet a functioning publishing system.** The high-level separation of manuscript, rendering engines, visual assets, and book repositories is appropriate. The most important remaining work is to turn proposals into a tested content contract and reproducible end-to-end build.

### Positive findings
- Clear separation between reusable platform and individual book repositories.
- Correctly identifies Markdown as the shared source and avoids treating PDF as the EPUB source.
- Distinguishes Canva's visual role from the production build pipeline.
- Includes accessibility and human publication review as explicit concerns.
- States that tools, schemas, and commands are proposals until implemented.
- Protects the Financial Markets project's separate editorial approvals.
- Keeps automated release/publication approval-gated.

### Gaps and risks
1. **No implementation exists yet.** There are no executable templates, scripts, schemas, tests, sample manuscript, or workflows.
2. **`CONTENT_SCHEMA.md` is a prose contract, not a machine-readable schema.** Required/optional metadata rules and allowed values are unresolved.
3. **Build commands are illustrative only.** `publisher validate` and `publisher build` are not implemented CLI commands.
4. **Toolchain is not selected or pinned.** TeX engine/distribution, Pandoc version, EPUB validator, runtime, and package set remain open.
5. **Reproducibility is unproven.** There is no clean-checkout build, dependency lock/pinning, or test evidence in this repository.
6. **No CI exists.** There are no GitHub Actions workflows for linting, validation, PDF/EPUB builds, or artifact previews.
7. **No sample project exists.** The first release acceptance criteria cannot yet be tested.
8. **Integration strategy is undecided.** Submodule, reusable workflow, or pinned release archive are still candidates; each has different maintenance and permission trade-offs.
9. **Licence is undecided.** A public repository without an explicit licence does not clearly grant reuse rights. Choose a suitable licence before encouraging public reuse; also record licences for fonts, images, and sample assets.
10. **Accessibility checks are currently mostly manual guidance.** Define practical automated checks and a repeatable human review procedure. Do not claim full PDF accessibility based only on a successful compile.
11. **README could be more explicit about the current state.** It should link to this handover and state clearly that only architecture documentation exists until implementation lands.
12. **No formal contribution/security policy exists.** Add lightweight contribution instructions and safe handling guidance before accepting external contributions or secrets.
13. **Canva exports need an asset specification.** Define supported formats, resolution/dimensions, SVG sanitization/security expectations, alternative-text metadata, and rights/attribution records.
14. **Format parity needs a content-feature matrix.** Define how tables, citations, callouts, equations, diagrams, footnotes, cross-references, and code are rendered in PDF versus EPUB, including graceful fallbacks.

### Audit limitations
This audit inspected GitHub repository metadata, the recursive tree on `main` and the architecture branch, the complete contents of the current Markdown documents, PR #1 metadata/diff/file list, review submissions, review threads, and PR conversation comments. Since the repository has no executable application or build pipeline, no code tests, security scans, dependency audits, PDF builds, EPUB validation, or CI runs were possible. Repository branch protection and all account-level GitHub settings were not independently assessed.

## 8. Recommended implementation roadmap

Proceed in small reviewable phases. Do not jump directly to a full production engine.

### Phase 0 — Approve and stabilize documentation
- Review PR #1 and this handover.
- Resolve wording/architecture issues and choose a repository licence.
- Merge only after owner approval.
- Keep the main branch as the approved stable baseline.

### Phase 1 — Define the actual content contract
- Select a minimal Markdown feature set and extension policy.
- Define a machine-readable `book.yml` schema.
- Define manuscript entry-point and chapter ordering rules.
- Define asset paths, captions, alt text, citations, references, and cross-reference conventions.
- Create a small synthetic sample book (not the Financial Markets manuscript).
- Add positive and negative metadata/content validation tests.

### Phase 2 — Build the PDF prototype
- Compare Pandoc-to-LaTeX with the required design outcomes.
- Select LuaLaTeX or XeLaTeX based on language/font needs and CI reliability.
- Add a reusable LaTeX class/template.
- Pin tool versions and package dependencies.
- Build the sample PDF from a clean environment and visually inspect representative pages.

### Phase 3 — Build the independent EPUB pipeline
- Generate reflowable EPUB from the same canonical Markdown.
- Include metadata, cover, navigation, CSS, and images.
- Run EPUBCheck or another selected validator.
- Test navigation and reflow in at least one reader; record limitations.

### Phase 4 — Shared validation and QA
- Validate metadata, local links, images, alt text, headings, references, and required files.
- Check PDF metadata, bookmarks, clipping, page layout, links, and text extraction where feasible.
- Check EPUB package validity, navigation, reading order, and reflow.
- Produce a concise build/QA report and keep human editorial review separate.

### Phase 5 — Automation and integration
- Add GitHub Actions for pull-request validation and preview artifacts.
- Pin system versions in consuming repositories.
- Decide integration method using a small proof of concept.
- Add versioning and release notes.
- Integrate the Financial Markets project only after its own project workflow and owner approvals permit it.

### Phase 6 — First usable release
Acceptance evidence must include:
- A clean checkout builds both PDF and EPUB from one Markdown manuscript.
- The same content source is used by both renderers.
- Validation tests catch missing metadata and broken local asset references.
- Tool versions and setup are documented.
- A human-reviewed PDF and EPUB sample is available.
- A consuming book repository can pin and invoke a released version.
- No automatic publication occurs without explicit owner approval.

## 9. Immediate next actions

1. Review [PR #1](https://github.com/JennyJoshua/universal-ebook-publishing-system/pull/1), which contains the initial architecture documents and this handover.
2. Resolve any requested corrections and the repository licence before inviting wider reuse.
3. After PR #1 is approved and merged, begin Phase 1: content contract and sample project.
4. Do not modify `png-financial-markets-ebook` during this foundational work.

## 10. Instructions for the next ChatGPT/Claude session

At the beginning of a new session, provide this file and ask the assistant to:

1. Read `PROJECT_CONTEXT.md` first, then inspect the current GitHub repository rather than assuming this snapshot is still current.
2. Check `main`, active branches, open PRs, latest commits, and the current project status.
3. Preserve all accepted decisions and owner approval gates.
4. Clearly label facts, accepted decisions, proposals, and unresolved questions.
5. Continue from the next incomplete roadmap phase; do not repeat completed work.
6. Do not merge, publish, delete, purchase, or materially change scope without explicit owner approval.
7. Keep the Financial Markets book repository separate and unchanged unless the owner authorizes integration.

**This file is the project's portable context snapshot, not a substitute for checking the live repository.** Update it whenever a significant decision, implementation milestone, scope change, or repository-state change occurs.
