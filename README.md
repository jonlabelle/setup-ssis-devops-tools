# Setup SSIS DevOps Tools

[![test](https://github.com/jonlabelle/setup-ssis-devops-tools/actions/workflows/test.yml/badge.svg)](https://github.com/jonlabelle/setup-ssis-devops-tools/actions/workflows/test.yml)

> A GitHub action that installs the latest standalone SQL Server Integration
> Service (SSIS) [devops tools](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone).

Standalone SSIS DevOps Tools provide a set of executables to do SSIS CICD tasks
without the dependency on the installation of Visual Studio or SSIS runtime. The
executables provided are:

- [SSISBuild.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisbuildexe): build SSIS projects in project deployment model or package deployment model.
- [SSISDeploy.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisdeployexe): deploy ISPAC files to SSIS catalog, or DTSX files and their dependencies to file system.

## Usage

> [!IMPORTANT]  
> This action supports **Windows** runners only.

```yaml
- name: Setup SSIS devops tools
  uses: jonlabelle/setup-ssis-devops-tools@v1.4.1
```

After running this step, **SSISBuild.exe** and **SSISDeploy.exe** are available for use from your path.

See the [tests](https://github.com/jonlabelle/setup-ssis-devops-tools/blob/main/.github/workflows/test.yml) for example usage.

## License

[MIT](LICENSE)
