# Setup CUE

This GitHub Action downloads and installs [`cue`](https://cuelang.org/) so that
it can be used as part of your workflow.

## Inputs

### `version`

Exact version of `cue` to install (cannot be a range or pattern).
Must be a [released version](https://github.com/cuelang/cue/releases).

### `github-token`

GitHub Token to use when downloading the release from GitHub.

## Outputs

### `bin`

Path to the `cue` binary, but will also be made available in `$GITHUB_PATH`.

## Example usage

```yaml
permissions:
  contents: read
steps:
- uses: sajari/setup-cue@v1
  with:
    version: 0.4.0
    github-token: ${{ secrets.GITHUB_TOKEN }}
- run: cue version
```
