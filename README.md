# Personal Cloud Storage

A shared public storage repository for personal applications. Each project owns an isolated namespace; this repository is not tied to any single application or data format.

## Layout

```text
storage.json
projects/
  <project-id>/
    README.md
    manifest.json
    config/                  # User preferences and application settings
    data/                    # Project-specific datasets
```

Current project: [Crypto Contract Workstation](projects/crypto-contract-workstation/README.md).

## Common rules

- Add projects to `storage.json`; use a stable lowercase project ID.
- Each project has its own manifest and schema. Paths in a project manifest are relative to that project's root.
- A project must only update files inside its own namespace and its own registry entry. Preserve other projects and their metadata.
- Keep configuration separate from datasets. A dataset may be split by type, entity and date, as required by that project.
- Validate structure, size and checksums before restoring data. Use GitHub file SHA or branch commit checks to detect concurrent writes.
- Store only data intended to be public. Credentials, tokens and device-local runtime protection state do not belong in this repository.
- Consumers can read public files without authentication. Writes require GitHub authorization.