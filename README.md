# Setup SSIS DevOps Tools

Installs the standalone SQL Server Integration Service (SSIS) [devops tools](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone).

## Usage

> [!IMPORTANT]
> The step only supports Windows runners.

```yaml
- name: Setup SSIS devops tools
  uses: jonlabelle/setup-ssis-devops-tools@v1
```

After running this step, [SSISBuild.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisbuildexe) and [SSISDeploy.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisdeployexe) are available for use in your path.

## Related

- [Test Setup SSIS DevOps Tools](https://github.com/jonlabelle/setup-ssis-devops-tools-test) - The testing repo for this project.
