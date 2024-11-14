# Update Sphinx Translations Action

This GitHub Action helps you automatically fetch and update Sphinx translations from a source repository to your own repository.

## Inputs

- `source_repo`: (Required) The URL of the source repository containing the original translations.
- `target_branch`: (Optional) The branch to push updated translations to (default: `main`).
- `languages`: (Required) A comma-separated list of language codes to update (e.g., `en,fr,de`).

## Example Workflow

```yaml
name: 'Update Sphinx Translations'

on:
  push:
    branches:
      - main

jobs:
  update-translations:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    - name: Update translations
      uses: your-org/update-sphinx-translations-action@v1
      with:
        source_repo: 'https://github.com/your-org/source-repo.git'
        languages: 'en,fr,de'
