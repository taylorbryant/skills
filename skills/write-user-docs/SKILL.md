---
name: write-user-docs
description: Write, revise, and review user-facing documentation for software libraries, frameworks, APIs, CLIs, CMS products, and developer tools. Use for READMEs, guides, tutorials, reference documentation, troubleshooting pages, public changelogs, release notes, and documentation copy.
---

# Write User Docs

Write for the person using the software. Explain observable behavior, decisions, and tasks without narrating the implementation or documentation work.

## Establish context

Before writing or reviewing:

1. Read applicable repository instructions, including `AGENTS.md` and `CONTRIBUTING.md`.
2. Read nearby documentation to learn its terminology, structure, and voice.
3. Establish the version the documentation targets. Do not present unreleased behavior as available in a released version.
4. Inspect the implementation, tests, schemas, or generated API surface for that version as needed to verify technical claims.
5. Follow repository-specific conventions over this skill.

Do not infer public behavior from names alone. When implementation, tests, and declared public contracts disagree, investigate the discrepancy instead of silently choosing one. Do not turn a possible bug into a documented guarantee. If the conflict remains unresolved, flag it in the handoff and avoid asserting the disputed claim as fact.

## Classify the audience

Treat these artifacts as user-facing unless repository instructions say otherwise:

- READMEs and documentation-site content
- Tutorials, how-to guides, examples, and quickstarts
- API and configuration reference
- Troubleshooting pages and migration guides
- Public changelogs and release notes

Treat contribution guides, architecture documents, architecture decision records, implementation plans, design proposals, pull request descriptions, and internal notes as maintainer-facing.

For an ambiguous artifact, infer the audience from its location, surrounding content, and stated purpose. Ask only when the distinction would materially change the result.

## Center the reader's task

Define the intended reader and the outcome they need. For substantial new pages, identify the content type and a one-sentence, verb-driven goal before drafting. Do not force a planning ceremony onto a small edit.

Use these content types as guides:

- **Tutorial**: teach through a complete, predictable learning path
- **How-to**: help a reader complete a specific task
- **Reference**: document a public surface precisely and completely
- **Concept**: explain a model the reader needs to reason about the product
- **Troubleshooting**: connect symptoms to causes, checks, and fixes
- **Migration**: explain user-visible changes and the actions required to adopt them

Make each sentence help the reader understand, decide, configure, use, debug, migrate, or verify something. Remove it or move it to a maintainer-facing artifact otherwise.

## Prevent maintainer-language leakage

Do not put the following in user-facing prose unless it changes how users interact with the product:

- Refactoring history or reasons a change was convenient to implement
- Internal architecture, abstraction boundaries, or source-tree organization
- Test coverage, fixture design, or build-system details
- Commentary about the current editing task, review process, or generated output
- Team coordination, roadmap reasoning, or repository consistency for its own sake
- Claims framed around what "we added," "we changed," or "the implementation now does"

Keep internal details when they explain public semantics, performance, security, compatibility, extension points, operational behavior, or necessary debugging steps. State the user-visible consequence first.

Translate internal framing into user-facing framing:

| Internal framing | User-facing framing |
| --- | --- |
| "We added a helper that wraps the adapter." | "Use the helper to configure the adapter." |
| "This abstraction lets us share validation." | Describe when validation runs and what errors users receive. |
| "The implementation now caches schemas." | Describe the observable caching behavior, if any. |
| "Tests cover malformed configuration." | Describe the validation guarantee and resulting error. |
| "The refactor makes future providers easier to add." | Omit it until users can select another provider. |

Put implementation notes and editing rationale in the final handoff, pull request description, or an appropriate maintainer document.

## Write clear product documentation

- Lead with the outcome or concept the reader came to learn.
- Use reader-shaped titles and descriptive headings. Prefer the reader's task over an internal feature or component name when the page is task-oriented.
- Address the reader directly when they act. Use imperative verbs for procedures and present tense for current behavior.
- Prefer concrete subjects and actions. Name the actor when passive construction obscures responsibility.
- Replace `easy`, `simple`, `quick`, and `just` with concrete information such as the number of steps, defaults involved, or prerequisites.
- Replace unsupported generalizations with verified specifics, or remove the claim. Preserve meaningful uncertainty, including qualifiers such as `typically` or `most` when supported, and explain the conditions when known. Never invent precision.
- Keep one main idea per paragraph. Use lists for genuinely list-shaped information, not merely to shorten prose.
- Define unfamiliar terms and acronyms when the intended reader is likely to need them. Avoid unnecessary link density.
- Use descriptive link text that names the destination.
- Preserve the project's established voice unless the user requests a broader rewrite.

## Make instructions easy to parse

- Put applicable conditions and context before the action they govern.
- Put the common path before exceptions and optional branches.
- Give the reader one decision or meaningful action per procedural step. Combine tightly coupled actions only when separating them would make the procedure harder to follow.
- Keep modifiers such as `only` and `not` next to the words they modify.
- Make every pronoun point to one unmistakable noun. Repeat the noun when needed.
- Use one public name for each concept, action, option, and component. Prefer the real public identifier over a synonym.

## Write useful code examples

- Use the repository's preferred language, package manager, formatting, and documentation components.
- Make examples minimal enough to understand and complete enough to use.
- Add a language identifier to every fenced code block.
- Explain what each example demonstrates and what result to expect.
- Keep required setup close to the example. Do not hide a necessary step in a distant sample project.
- Use conspicuously fake, descriptive placeholders that readers can replace safely.
- Run examples or the repository's documentation checks when practical. Otherwise state what was not verified in the handoff, not in the documentation.

## Revise with restraint

Preserve accurate content, intentional terminology, and the author's voice. Do not churn prose merely to enforce a personal preference.

Prioritize revisions in this order:

1. Technical accuracy and safe instructions
2. Reader goal, prerequisites, and completeness
3. Separation of user-facing and maintainer-facing information
4. Clarity, structure, and navigation
5. Repository style and typography

Apply sentence-length, paragraph-length, punctuation, and similar style preferences with judgment. Do not create choppy prose to satisfy a mechanical limit.

## Finish the task

For writing or revision requests, make the requested edits and summarize material documentation decisions in the handoff.

For review-only requests, do not edit files. Group actionable findings by file and use `path:line` locations. Explain a rule only when the fix is not obvious. Prioritize correctness and audience problems over low-value stylistic preferences.

### Read without project history

For READMEs, guides, and current architecture docs, reread changed prose as someone who has not seen previous versions, related PRs, or the conversation. Apply this pass to maintainer-facing guides too; new contributors may lack that history.

Review words such as `now`, `still`, `remains`, `continues`, and `no longer`. When they imply an unexplained previous state, describe the current behavior directly:

- "BlockNote remains the editor." → "The page editor uses BlockNote."
- "Database saves still write full snapshots." → "Each database save writes a full snapshot."

Treat these words as review cues, not banned words. Preserve meaningful runtime behavior such as "Edits remain available while offline." Keep comparisons when readers need them for migration, compatibility, or release notes, and make the relevant versions or conditions explicit.

### Final checks

Before finishing, check:

- Does the page tell the intended reader what they can do and how to do it?
- Are internal details included only when they explain a user-visible consequence?
- Are commands, identifiers, defaults, and behavioral claims verified for the target version, with unresolved conflicts reported in the handoff?
- Does each procedure put applicable context before the action and keep one reader decision per step?
- Can every pronoun and modifier be read only one way? Does each thing keep the same public name?
- Do examples include the setup and expected result needed to use them?
