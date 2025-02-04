---
title: NuGetPublisher@0 - NuGet publisher v0 task
description: NuGetPublisher@0 is deprecated. Use the NuGet task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# NuGetPublisher@0 - NuGet publisher v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
NuGetPublisher@0 is deprecated. Use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# NuGet publisher v0
# Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
- task: NuGetPublisher@0
  inputs:
    searchPattern: '**/*.nupkg;-:**/packages/**/*.nupkg;-:**/*.symbols.nupkg' # string. Required. Path/Pattern to nupkg. Default: '**/*.nupkg;-:**/packages/**/*.nupkg;-:**/*.symbols.nupkg'.
    nuGetFeedType: 'external' # 'external' | 'internal'. Required. Feed type. Default: 'external'.
    connectedServiceName: # string. Required when nuGetFeedType = external. NuGet Service Connection. 
    #feedName: # string. Required when nuGetFeedType = internal. Internal Feed URL. 
  # Advanced
    #nuGetAdditionalArgs: # string. NuGet Arguments. 
    #verbosity: '-' # '-' | 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: '-'.
    nuGetVersion: '3.3.0' # '3.3.0' | '3.5.0.1829' | '4.0.0.2283' | 'custom'. Required. NuGet Version. Default: '3.3.0'.
    #nuGetPath: # string. Path to NuGet.exe. 
    #continueOnEmptyNupkgMatch: false # boolean. Continue if no packages match the "Path/Pattern to nupkg". Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# NuGet Publisher v0
# Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default.
- task: NuGetPublisher@0
  inputs:
    searchPattern: '**/*.nupkg;-:**/packages/**/*.nupkg;-:**/*.symbols.nupkg' # string. Required. Path/Pattern to nupkg. Default: '**/*.nupkg;-:**/packages/**/*.nupkg;-:**/*.symbols.nupkg'.
    nuGetFeedType: 'external' # 'external' | 'internal'. Required. Feed type. Default: 'external'.
    connectedServiceName: # string. Required when nuGetFeedType = external. NuGet Service Connection. 
    #feedName: # string. Required when nuGetFeedType = internal. Internal Feed URL. 
  # Advanced
    #nuGetAdditionalArgs: # string. NuGet Arguments. 
    #verbosity: '-' # '-' | 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: '-'.
    nuGetVersion: '3.3.0' # '3.3.0' | '3.5.0.1829' | '4.0.0.2283' | 'custom'. Required. NuGet Version. Default: '3.3.0'.
    #nuGetPath: # string. Path to NuGet.exe. 
    #continueOnEmptyNupkgMatch: false # boolean. Continue if no packages match the "Path/Pattern to nupkg". Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="searchPattern"::: -->
:::moniker range="<=azure-pipelines"

**`searchPattern`** - **Path/Pattern to nupkg**<br>
Type: string. Required. Default value: '**/*.nupkg;-:**/packages/**/*.nupkg;-:**/*.symbols.nupkg'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The pattern to match or path to nupkg files to be uploaded. Multiple patterns can be separated by a semicolon.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetFeedType"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetFeedType`** - **Feed type**<br>
Type: string. Required. Allowed values: 'external', 'internal'. Default value: 'external'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connectedServiceName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`connectedServiceName`** - **NuGet Service Connection**<br>
Type: string. Required when nuGetFeedType = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The NuGet server generic service connection, set the key 'Password/Token Key' field to your NuGet API key.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`connectedServiceName`** - **NuGet Server Endpoint**<br>
Type: string. Required when nuGetFeedType = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The NuGet server generic service connection, set the key 'Password/Token Key' field to your NuGet API key.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedName"::: -->
:::moniker range="<=azure-pipelines"

**`feedName`** - **Internal Feed URL**<br>
Type: string. Required when nuGetFeedType = internal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The URL of a NuGet feed hosted in this account.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetAdditionalArgs"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetAdditionalArgs`** - **NuGet Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to NuGet.exe push. [More Information](/nuget/tools/cli-ref-push).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosity"::: -->
:::moniker range="<=azure-pipelines"

**`verbosity`** - **Verbosity**<br>
Type: string. Allowed values: '-', 'Quiet', 'Normal', 'Detailed'. Default value: '-'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
NuGet's verbosity level.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetVersion"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetVersion`** - **NuGet Version**<br>
Type: string. Required. Allowed values: '3.3.0', '3.5.0.1829', '4.0.0.2283', 'custom'. Default value: '3.3.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of NuGet to use, or custom version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetPath"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetPath`** - **Path to NuGet.exe**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to NuGet.exe. Will override version selection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="continueOnEmptyNupkgMatch"::: -->
:::moniker range="<=azure-pipelines"

**`continueOnEmptyNupkgMatch`** - **Continue if no packages match the "Path/Pattern to nupkg"**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Continue instead of fail if no packages match the "Path/Pattern to nupkg".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->