# Setup SSIS DevOps Tools

[![CI](https://github.com/jonlabelle/setup-ssis-devops-tools/actions/workflows/ci.yml/badge.svg)](https://github.com/jonlabelle/setup-ssis-devops-tools/actions/workflows/ci.yml)
[![latest release](https://img.shields.io/github/v/tag/jonlabelle/setup-ssis-devops-tools.svg?label=version&sort=semver)](https://github.com/jonlabelle/setup-ssis-devops-tools/releases)

> A GitHub Action that installs the latest standalone SQL Server Integration
> Services (SSIS) [DevOps Tools](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone).

Standalone SSIS DevOps Tools provide executables for SSIS CI/CD tasks without
requiring Visual Studio or the SSIS runtime. This action makes the following
tools available:

- [SSISBuild.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisbuildexe): build SSIS projects in project deployment model or package deployment model.
- [SSISDeploy.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisdeployexe): deploy ISPAC files to SSIS catalog, or DTSX files and their dependencies to file system.

## Usage

> [!IMPORTANT]  
> This action supports **Windows** runners only.

```yaml
name: Use SSIS DevOps Tools

on:
  workflow_dispatch:

jobs:
  test:
    runs-on: windows-latest
    steps:
      - name: Setup SSIS DevOps Tools
        id: setup-ssis-tools
        uses: jonlabelle/setup-ssis-devops-tools@v1

      - name: Show installed location
        shell: pwsh
        run: |
          Write-Host "SSIS tools path: ${{ steps.setup-ssis-tools.outputs.ssis_tools_path }}"

      - name: Show SSISBuild.exe help
        shell: pwsh
        run: SSISBuild.exe -h
```

After the setup step runs, **SSISBuild.exe** and **SSISDeploy.exe** are
available from your job `PATH`.

## Outputs

| Name              | Description                                                          |
| ----------------- | -------------------------------------------------------------------- |
| `ssis_tools_path` | Directory where `SSISBuild.exe` and `SSISDeploy.exe` were installed. |

## Behavior

- Installs the tools under `${{ runner.temp }}/setup-ssis-devops-tools`.
- Recreates the install directory on each run before extraction.
- Adds the tools directory to the current job `PATH`.
- Fails fast on non-Windows runners.

See the [Windows test workflow](https://github.com/jonlabelle/setup-ssis-devops-tools/blob/main/.github/workflows/_test.yml) for a focused example and the [CI workflow](https://github.com/jonlabelle/setup-ssis-devops-tools/blob/main/.github/workflows/ci.yml) for full repository automation.

## License

[MIT](LICENSE)
