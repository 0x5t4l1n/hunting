# Contributing to OWASP Hunting

This is the canonical contribution guide for the project.

## Rules

- Content must be legal, ethical, and support authorized security testing only.
- No credentials, API keys, tokens, or private/customer data — real or realistic-looking.
- No exploits for undisclosed (0-day) vulnerabilities.
- No plagiarism — attribute sources where a payload comes from a specific writeup, CVE, or tool.
- Don't submit a payload that is character-for-character or whitespace-only different from one that already exists. If it's a meaningful variant (different encoding, bypass, or context), say so in the PR.

## Workflow

1. Fork the repo and create a focused branch (`add-xss-dom-payloads`, `new-category-graphql-injection`, etc.).
2. Add/edit payloads in the right category directory, matching its existing format.
3. Before opening the PR, grep the target (and related) categories for near-duplicates yourself — the CI duplicate check only catches exact and whitespace-only matches, not meaningful near-duplicates.
4. Review your own diff, then open a PR against `main` using the PR template.

### New category

Only if the vulnerability class doesn't fit an existing one:

```
New-Category/
├── README.md       # Description, Common Attack Vectors, Testing Approach, Payloads
└── new-category-payloads.txt
```

Add it to the category list in the top-level [README.md](./README.md).

## Duplicate checking

`scripts/check_duplicates.py` runs automatically in CI (`.github/workflows/duplicate-check.yml`) on every PR. It compares added/changed lines in `.txt` payload files against every other `.txt` payload file in the repo, and flags **exact** and **whitespace-only** duplicates — both against `main` and within the PR itself. It's a line-based text comparison scoped to payload files, not a semantic check and not a check of Markdown/documentation content. It is not meant to be run standalone locally (it reads the PR diff via the GitHub API).

The bot always comments directly on the PR with the result: if a duplicate is found, it lists each entry, its location in your PR, and where it already exists; if not, it confirms no duplicates were found. It updates that same comment on every push instead of piling up new ones.

The bot also applies or removes the `duplicate` label based on this same result — it's the only thing that touches that label; it's never applied from file paths alone.

## Automatic labels

`.github/workflows/labeler.yml` applies labels based on which files a PR changes, using `.github/labeler.yml`:

| Label | Applied when |
|---|---|
| `new-payload` | A `.txt` payload file is added or changed |
| `documentation` | Any `.md` file changes (root docs or a category README) |
| `maintenance` | Changes under `.github/workflows/`, `.github/labeler.yml`, `scripts/`, or `.gitignore` |
| `new-category` | Every changed file sits inside a top-level directory that isn't already a known category — i.e. the PR introduces a new one |
| `duplicate` | Applied/removed only by the Duplicate Payload Check workflow above — never by the labeler |
| `needs-review` | Not automated — no file path reliably implies a PR needs review (every PR does), so this is left to maintainers |

`new-payload`, `documentation`, `new-category`, and `duplicate` already exist as repository labels and are reused as-is. **`maintenance` does not exist yet and must be created manually** in the repo's Labels settings before the labeler workflow can apply it.

## Pull requests

Every PR should state: what changed, why it's useful, which category it affects, whether you checked for duplicates, what validation you did, and any sources/references. Payloads are never executed in CI or by any project tooling.

## AI-assisted contributions

AI-assisted contributions are allowed if disclosed and personally validated by the contributor — disclosure alone is never grounds for rejection; undisclosed or unvalidated AI output is.

Every PR must include:

```
AI assistance: Yes / No
Tool or model: <name + version, or "unknown">
Provider: <if known>
Contribution: <what it helped create or modify>
Human validation: <what you personally reviewed or tested>
```

- Say "unknown" rather than guessing a model/version.
- No need to disclose prompts, conversations, or account details — only the fields above.
- No tool or provider is required, recommended, or disallowed.
- You are responsible for the technical accuracy, legality, and relevance of anything you submit, regardless of what tool helped produce it. This covers *contributor* AI use only — the project itself does not integrate any AI provider.

## Resources

- [Official project page](https://owasp.org/projects/hunting)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [DISCLAIMER.md](./DISCLAIMER.md) — legal terms you agree to by contributing
- [SECURITY.md](./SECURITY.md) — reporting a security issue in this repo itself
