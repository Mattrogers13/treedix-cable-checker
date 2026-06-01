# outputs/ — Claude-generated deliverables

Everything Claude produces lands here, versioned so progression is visible at a glance.

## Versioning scheme
- **One folder per deliverable**, named for the artifact: `outputs/<artifact-name>/`
- Files named **`vNN-<artifact-name>.<ext>`**, zero-padded: `v01`, `v02` … `v10`, `v11`
- **Never overwrite a prior version.** Each iteration is a new file with the next number.
- **Highest number = current.**
- Record *what changed* between versions in that day's `docs/ai/journal/` entry.

## Example
```
outputs/
├── landing-copy/
│   ├── v01-landing-copy.md
│   ├── v02-landing-copy.md
│   └── v03-landing-copy.md
└── data-model/
    ├── v01-data-model.md
    └── v02-data-model.md
```

(If under git, git still tracks all of this — the version numbers are for easy
human-readable progression and side-by-side draft comparison.)
