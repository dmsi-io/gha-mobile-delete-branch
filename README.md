# gha-mobile-delete-branch

Clean up Expo branch on PR close

## Inputs

| NAME     | DESCRIPTION                               | TYPE      | REQUIRED | DEFAULT                     |
|:---------|:------------------------------------------|:----------|:---------|:----------------------------|
| `branch` | What Expo branch to delete if non-default | `string`  | `false`  | The current git branch name |
| `token`  | Token for logging in to Expo              | `string`  | `true`   |                             |

```yaml
name: Publish

on:
  push:
    branches:
      - develop

jobs:
  publish:
    name: Delete Branch
    runs-on: ubuntu-latest
    steps:
      - name: Delete Branch
        uses: dmsi-io/gha-mobile-delete-branch@main
        with:
          token: ${{ secrets.EXPO_TOKENS }}
```
