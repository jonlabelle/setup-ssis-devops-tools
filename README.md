# Setup SSIS DevOps Tools

Installs [Standalone SQL Server Integration Service (SSIS) DevOps Tools](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone).

## Usage

> [!IMPORTANT]
> The step only supports Windows runners.

```yaml
- name: Setup SSIS devops tools
  uses: jonlabelle/setup-ssis-devops-tools@v1
```

After running this step, [SSISBuild.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisbuildexe) and [SSISDeploy.exe](https://learn.microsoft.com/en-us/sql/integration-services/devops/ssis-devops-standalone#ssisdeployexe) are available for use in your path.
