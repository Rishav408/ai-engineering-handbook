# Contributing to AI Engineering Handbook

Thanks for considering a contribution. This repo works because it stays original, accurate, and well-organized — please read this before opening a PR.

---

## Ground rules

1. **Write in your own words.** Notes in `docs/` are original synthesis, not copy-pasted material from courses, books, or papers. If you're adding or editing a note, explain the concept the way you'd explain it to someone else — don't lift phrasing from a source.
2. **Cite, don't reproduce.** If a resource (course, paper, book, blog post) informed a note, link it in that file's "Further Reading" section instead of quoting it at length. Short (under ~15-word) attributed quotes are fine when exact wording matters; long excerpts are not.
3. **No paywalled or pirated content.** Don't link to scraped course dumps, pirated books, or paywall-bypass mirrors. Only link to legitimate sources (official course pages, publisher sites, arXiv, official docs).
4. **Keep the folder numbering intact.** Files and folders are numbered (`00-`, `01-`, `02-`...) to preserve reading order. If you're adding a new topic, number it to fit logically within its section rather than appending it at the end.
5. **One topic per file.** Each `.md` file in `docs/` covers a single concept or sub-topic, matching the structure in the main `README.md`. Don't merge multiple unrelated topics into one file.

---

## Types of contributions welcome

| Type | Example |
|---|---|
| **Typo / grammar fixes** | Fixing a broken sentence or misspelling in an existing note |
| **Clarifications** | Rewriting a confusing explanation, adding a missing definition |
| **New resources** | Adding a free, high-quality course/paper/tool to `resources/` |
| **New notes** | Writing a note for a topic listed in the roadmap but not yet covered |
| **Diagrams/tables** | Adding a comparison table or Mermaid diagram that clarifies a concept |
| **Dead link fixes** | Reporting or fixing broken links in `resources/` |

---

## File format conventions

### Notes (`docs/`)

Each note should follow this rough shape:

```markdown
# Topic Title

## Definition
Plain-language definition of the concept.

## Details
Deeper explanation — how it works, why it matters, common pitfalls.

## Comparison / Reference table (if applicable)
| ... | ... |

## Further Reading
- [Resource name](url) — one-line description of what it covers
```

### Resources (`resources/`)

Keep the existing per-category format:

```markdown
## Category Name
- [Resource Title](url)
```

Only add resources that are:
- Free (or clearly marked if partially paid, e.g. "free tier available")
- Currently live (check the link before submitting)
- Genuinely useful — not filler to pad the list

---

## Submitting a change

1. Fork the repo and create a branch: `git checkout -b add-notes-on-topic-x`
2. Make your changes following the conventions above.
3. Check that any links you added actually resolve.
4. Open a pull request with a short description of what changed and why.
5. Be responsive to review comments — small, focused PRs merge faster than large ones.

---

## Reporting issues

Found a dead link, factual error, or outdated resource? Open an issue with:
- The file/section affected
- What's wrong
- (Optional) A suggested fix

---

## Code of conduct

Be respectful, be constructive, and assume good faith. This is a learning resource — the goal is to help people, not to gatekeep.
