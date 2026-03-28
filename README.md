# Setup SSIS DevOps Tools

[![CI](https://github.com/jonlabelle/setup-ssis-devops-tools/actions/workflows/ci.yml/badge.svg)](https://github.com/jonlabelle/setup-ssis-devops-tools/actions/workflows/ci.yml)
[![latest release](https://img.shields.io/github/v/tag/jonlabelle/setup-ssis-devops-tools.svg?label=version&sort=semver)](https://github.com/jonlabelle/setup-ssis-devops-tools/releases)

> A GitHub action that installs the latest standalone SQL Server Integration
> Service (SSIS) [devops tools](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone).

Standalone SSIS DevOps Tools provide a set of executables to do SSIS CI/CD tasks
without the dependency on the installation of Visual Studio or SSIS runtime. The
executables provided are:

- [SSISBuild.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisbuildexe): build SSIS projects in project deployment model or package deployment model.
- [SSISDeploy.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisdeployexe): deploy ISPAC files to SSIS catalog, or DTSX files and their dependencies to file system.

## Usage

> [!IMPORTANT]  
> This action supports **Windows** runners only.

```yaml
- name: Setup SSIS devops tools
  id: setup-ssis-tools
  uses: jonlabelle/setup-ssis-devops-tools@v1

- name: Show installed location
  shell: pwsh
  run: |
    Write-Host "SSIS tools path: ${{ steps.setup-ssis-tools.outputs.ssis_tools_path }}"
```

After running this step, **SSISBuild.exe** and **SSISDeploy.exe** are available from your job `PATH`.
The tools are installed in the runner temp directory, and the resolved install location is also available through the `ssis_tools_path` output.

See the [CI workflow](https://github.com/jonlabelle/setup-ssis-devops-tools/blob/main/.github/workflows/ci.yml) for example usage.

## License

[MIT](LICENSE)
