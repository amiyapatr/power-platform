---
title: Microsoft Power Platform CLI solution command group| Microsoft Docs
description: "Describes commands and parameters for the Microsoft Power Platform CLI solution command group."
keywords: "pac cli"
ms.subservice: developer
author: kkanakas
ms.author: kartikka
ms.date: 9/15/2022
ms.reviewer: jdaly
ms.topic: reference
contributors: 
 - JimDaly
---
<!-- 
Do not edit this file. 
This file is generated by a program and any changes will be overwritten when this topic is re-generated.
Use the include files to add additional content to this topic.
-->
# pac solution

Commands for working with Dataverse solution projects

[!INCLUDE [solution-intro](includes/solution-intro.md)]

## Commands

|Command|Description|
|---------|---------|
|[pac solution add-license](#pac-solution-add-license)|Add license and plan info to solution|
|[pac solution add-reference](#pac-solution-add-reference)|Adds a reference from the project in the current directory to the project at 'path'|
|[pac solution add-solution-component](#pac-solution-add-solution-component)|Adds a solution component to the target unmanaged solution in Dataverse.|
|[pac solution check](#pac-solution-check)|Upload a Dataverse Solution project to run against the Power Apps Checker Service|
|[pac solution clone](#pac-solution-clone)|Create a solution project based on an existing solution in your Organization|
|[pac solution create-settings](#pac-solution-create-settings)|Create a settings file from solution zip or solution folder.|
|[pac solution delete](#pac-solution-delete)|Delete solution from Dataverse in the current Environment.|
|[pac solution export](#pac-solution-export)|Export a solution from Dataverse.|
|[pac solution import](#pac-solution-import)|Import the solution into Dataverse.|
|[pac solution init](#pac-solution-init)|Initializes a directory with a new Dataverse solution project|
|[pac solution list](#pac-solution-list)|List all Solutions from the current Dataverse Organization|
|[pac solution online-version](#pac-solution-online-version)|Sets version for solution loaded in Dataverse.|
|[pac solution pack](#pac-solution-pack)|Package solution components on local filesystem into solution.zip (SolutionPackager)|
|[pac solution publish](#pac-solution-publish)|Publishes all customizations|
|[pac solution sync](#pac-solution-sync)|Sync the current Dataverse solution project to the current state of the solution in your Organization.|
|[pac solution unpack](#pac-solution-unpack)|Extract solution components from solution.zip onto local filesystem (SolutionPackager)|
|[pac solution upgrade](#pac-solution-upgrade)|Option to stage the Dataverse solution for upgrade|
|[pac solution version](#pac-solution-version)|Update build or revision version for solution|


## pac solution add-license

Add license and plan info to solution

[!INCLUDE [solution-add-license-intro](includes/solution-add-license-intro.md)]


### Required Parameters

#### `--planDefinitionFile` `-pd`

License plan definition file in CSV format; expected columns: Service ID, Display name, More info URL

#### `--planMappingFile` `-pm`

License plan mapping file in CSV format; expected columns: Service ID, Component name

[!INCLUDE [solution-add-license-remarks](includes/solution-add-license-remarks.md)]

## pac solution add-reference

Adds a reference from the project in the current directory to the project at 'path'

[!INCLUDE [solution-add-reference-intro](includes/solution-add-reference-intro.md)]


### Required Parameters

#### `--path` `-p`

The path to the referenced project

[!INCLUDE [solution-add-reference-remarks](includes/solution-add-reference-remarks.md)]

## pac solution add-solution-component

Adds a solution component to the target unmanaged solution in Dataverse.

[!INCLUDE [solution-add-solution-component-intro](includes/solution-add-solution-component-intro.md)]


### Required Parameters

#### `--component` `-c`

The schema name or ID of the component to add to the target solution

#### `--componentType` `-ct`

The value that represents the solution component that you are adding

#### `--solutionUniqueName` `-sn`

Name of the solution


### Optional Parameters

#### `--AddRequiredComponents` `-arc`

Indicates whether other solution components that are required by the solution component that you are adding should also be added to the unmanaged solution

This parameter requires no value. It is a switch.

#### `--environment` `-env`

Environment URL or ID of the target environment.

[!INCLUDE [solution-add-solution-component-remarks](includes/solution-add-solution-component-remarks.md)]

## pac solution check

Upload a Dataverse Solution project to run against the Power Apps Checker Service

[!INCLUDE [solution-check-intro](includes/solution-check-intro.md)]


### Optional Parameters

#### `--customEndpoint` `-ce`

Specify a custom URL as Power Apps Checker endpoint

#### `--excludedFiles` `-ef`

Exclude Files from the Analysis. Pass as comma-separated values

#### `--geo` `-g`

Which geographical instance of the Power Apps Checker service to use.

Use one of these values:

- `PreviewUnitedStates`
- `UnitedStates`
- `Europe`
- `Asia`
- `Australia`
- `Japan`
- `India`
- `Canada`
- `SouthAmerica`
- `UnitedKingdom`
- `France`
- `Germany`
- `UnitedArabEmirates`
- `Switzerland`
- `USGovernment`
- `USGovernmentL4`
- `USGovernmentL5DoD`
- `China`

#### `--outputDirectory` `-o`

Output directory

#### `--path` `-p`

Path where the to-be-checked solution zip file(s) exist; path can contain glob/wildcard characters

#### `--ruleLevelOverride` `-rl`

Path to a file containing a JSON array rules and levels to override.  Accepted values for OverrideLevel are: Critical, High, Medium, Low, Informational. Example: [{"Id":"meta-remove-dup-reg","OverrideLevel":"Medium"},{"Id":"il-avoid-specialized-update-ops","OverrideLevel":"Medium"}]

#### `--ruleSet` `-rs`

Select a rule set that will be executed as part of this build. Values: A valid Guid, "AppSource Certification", "Solution Checker" (default)

#### `--solutionUrl` `-u`

SAS Uri pointing to solution.zip to be analyzed

[!INCLUDE [solution-check-remarks](includes/solution-check-remarks.md)]

## pac solution clone

Create a solution project based on an existing solution in your Organization

[!INCLUDE [solution-clone-intro](includes/solution-clone-intro.md)]


### Required Parameters

#### `--name` `-n`

The name of the solution to be exported


### Optional Parameters

#### `--async` `-a`

Exports solution asynchronously

This parameter requires no value. It is a switch.

#### `--include` `-i`

Which settings should be included in the solution being exported

Use one or more of these values separated by commas:

- `autonumbering`
- `calendar`
- `customization`
- `emailtracking`
- `externalapplications`
- `general`
- `isvconfig`
- `marketing`
- `outlooksynchronization`
- `relationshiproles`
- `sales`

#### `--max-async-wait-time` `-wt`

Max asynchronous wait time in minutes. Default value is 60 minutes

#### `--outputDirectory` `-o`

Output directory

#### `--packagetype` `-p`

Specifies the extraction type for the solution. Can be: 'Unmanaged', 'Managed' or 'Both'; default: 'Both'

#### `--processCanvasApps` `-pca`

(Preview) Pack/unpack any Canvas apps (.msapp) while processing the solution. default: false

This parameter requires no value. It is a switch.

#### `--targetversion` `-v`

**Deprecated**: This parameter will be ignored.
[!INCLUDE [solution-clone-remarks](includes/solution-clone-remarks.md)]

## pac solution create-settings

Create a settings file from solution zip or solution folder.

[!INCLUDE [solution-create-settings-intro](includes/solution-create-settings-intro.md)]


### Optional Parameters

#### `--settings-file` `-s`

The .json file with the deployment settings for connection references and environment variables.

#### `--solution-folder` `-f`

Path to the local, unpacked solution folder: either the root of the 'Other/Solution.xml' file or a folder with a .cdsproj file.

#### `--solution-zip` `-z`

Path to solution zip file.

[!INCLUDE [solution-create-settings-remarks](includes/solution-create-settings-remarks.md)]

## pac solution delete

Delete solution from Dataverse in the current Environment.

[!INCLUDE [solution-delete-intro](includes/solution-delete-intro.md)]


### Required Parameters

#### `--solution-name` `-sn`

Name of the solution

[!INCLUDE [solution-delete-remarks](includes/solution-delete-remarks.md)]

## pac solution export

Export a solution from Dataverse.

[!INCLUDE [solution-export-intro](includes/solution-export-intro.md)]


### Required Parameters

#### `--name` `-n`

The name of the solution to be exported

#### `--path` `-p`

Path where the exported solution zip file will be written


### Optional Parameters

#### `--async` `-a`

Exports solution asynchronously

This parameter requires no value. It is a switch.

#### `--include` `-i`

Which settings should be included in the solution being exported

Use one or more of these values separated by commas:

- `autonumbering`
- `calendar`
- `customization`
- `emailtracking`
- `externalapplications`
- `general`
- `isvconfig`
- `marketing`
- `outlooksynchronization`
- `relationshiproles`
- `sales`

#### `--managed` `-m`

Whether the solution should be exported as a managed solution

This parameter requires no value. It is a switch.

#### `--max-async-wait-time` `-wt`

Max asynchronous wait time in minutes. Default value is 60 minutes

#### `--overwrite` `-ow`

The exported solution file can overwrite the solution zip file on the local file system.

This parameter requires no value. It is a switch.

#### `--targetversion` `-v`

**Deprecated**: This parameter will be ignored.
[!INCLUDE [solution-export-remarks](includes/solution-export-remarks.md)]

## pac solution import

Import the solution into Dataverse.

[!INCLUDE [solution-import-intro](includes/solution-import-intro.md)]


### Optional Parameters

#### `--activate-flows` `-af`

Turn on workflows specified in the deployment settings file using a specified user

This parameter requires no value. It is a switch.

#### `--activate-plugins` `-ap`

Activate plug-ins and workflows on the solution

This parameter requires no value. It is a switch.

#### `--async` `-a`

Imports solution asynchronously

This parameter requires no value. It is a switch.

#### `--convert-to-managed` `-cm`

Convert as Managed Solution

This parameter requires no value. It is a switch.

#### `--force-overwrite` `-f`

Force an overwrite of unmanaged customizations

This parameter requires no value. It is a switch.

#### `--import-as-holding` `-h`

Import the solution as a holding solution

This parameter requires no value. It is a switch.

#### `--max-async-wait-time` `-wt`

Max asynchronous wait time in minutes. Default value is 60 minutes

#### `--path` `-p`

Path to solution zip file. If not specified, assumes the current folder is a cdsproj project.

#### `--publish-changes` `-pc`

Publish your changes upon a successful import

This parameter requires no value. It is a switch.

#### `--settings-file`

The .json file with the deployment settings for connection references and environment variables.

#### `--skip-dependency-check` `-s`

Skip dependency check against dependencies flagged as product update

This parameter requires no value. It is a switch.

[!INCLUDE [solution-import-remarks](includes/solution-import-remarks.md)]

## pac solution init

Initializes a directory with a new Dataverse solution project

[!INCLUDE [solution-init-intro](includes/solution-init-intro.md)]


### Required Parameters

#### `--publisher-name` `-pn`

Name of the Dataverse solution publisher

**Note**: Only characters within the ranges [A - Z], [a - z], [0 - 9], or _ are allowed. The first character may only be in the ranges [A - Z], [a - z], or _.

#### `--publisher-prefix` `-pp`

Customization prefix value for the Dataverse solution publisher

**Note**: The prefix must be 2 to 8 characters long, can only consist of alpha-numerics, must start with a letter, and cannot start with 'mscrm'.


### Optional Parameters

#### `--outputDirectory` `-o`

Output directory

[!INCLUDE [solution-init-remarks](includes/solution-init-remarks.md)]

## pac solution list

List all Solutions from the current Dataverse Organization

[!INCLUDE [solution-list-intro](includes/solution-list-intro.md)]


### Optional Parameters

#### `--environment` `-env`

The target Environment ID or URL.  Default value is the environment of your currently active Dataverse Auth Profile.

#### `--environment-id`

**Deprecated**: Use `--environment` instead.
[!INCLUDE [solution-list-remarks](includes/solution-list-remarks.md)]

## pac solution online-version

Sets version for solution loaded in Dataverse.

[!INCLUDE [solution-online-version-intro](includes/solution-online-version-intro.md)]


### Required Parameters

#### `--solution-name` `-sn`

Name of the solution

#### `--solution-version` `-sv`

Specify the solution version number.

[!INCLUDE [solution-online-version-remarks](includes/solution-online-version-remarks.md)]

## pac solution pack

Package solution components on local filesystem into solution.zip (SolutionPackager)

[!INCLUDE [solution-pack-intro](includes/solution-pack-intro.md)]


### Required Parameters

#### `--zipfile` `-z`

The full path to the solution ZIP file


### Optional Parameters

#### `--allowDelete` `-ad`

Dictates if delete operations may occur; default: false.

This parameter requires no value. It is a switch.

#### `--allowWrite` `-aw`

Dictates if write operations may occur; default: false.

This parameter requires no value. It is a switch.

#### `--clobber` `-c`

Enables that files marked read-only can be deleted or overwritten; default: false.

This parameter requires no value. It is a switch.

#### `--disablePluginRemap` `-dpm`

Disabled plug-in fully qualified type name remapping. default: false

This parameter requires no value. It is a switch.

#### `--errorlevel` `-e`

Minimum logging level for log output [Verbose|Info|Warning|Error|Off]; default: Info

#### `--folder` `-f`

The path to the root folder on the local filesystem. When unpacking/extractins, this will be written to, when packing this will be read from.

#### `--localize` `-loc`

Extract or merge all string resources into .resx files.

This parameter requires no value. It is a switch.

#### `--log` `-l`

The path to the log file.

#### `--map` `-m`

The full path to a mapping xml file from which to read component folders to pack.

#### `--packagetype` `-p`

When unpacking/extracting, use to specify dual Managed and Unmanaged operation. When packing, use to specify Managed or Unmanaged from a previous unpack 'Both'. Can be: 'Unmanaged', 'Managed' or 'Both'; default: 'Unmanaged'

#### `--processCanvasApps` `-pca`

(Preview) Pack/unpack any Canvas apps (.msapp) while processing the solution. default: false

This parameter requires no value. It is a switch.

#### `--singleComponent` `-sc`

Only perform action on a single component type [WebResource|Plugin|Workflow|None]; default: None.

#### `--sourceLoc` `-src`

Generates a template resource file. Valid only on Extract. Possible Values are auto or an LCID/ISO code of the language you wish to export. When Present, this will extract the string resources from the given locale as a neutral .resx. If auto or just the long or short form of the switch is specified the base locale for the solution will be used.

#### `--useLcid` `-lcid`

Use LCID's (1033) rather than ISO codes (en-US) for language files.

This parameter requires no value. It is a switch.

#### `--useUnmanagedFileForMissingManaged` `-same`

Use the same XML source file when packaging for Managed and only Unmanaged XML file is found; applies to AppModuleSiteMap, AppModuleMap, FormXml files

This parameter requires no value. It is a switch.

[!INCLUDE [solution-pack-remarks](includes/solution-pack-remarks.md)]

## pac solution publish

Publishes all customizations

[!INCLUDE [solution-publish-intro](includes/solution-publish-intro.md)]


### Optional Parameters

#### `--async` `-a`

Imports solution asynchronously

This parameter requires no value. It is a switch.

#### `--max-async-wait-time` `-wt`

Max asynchronous wait time in minutes. Default value is 60 minutes

[!INCLUDE [solution-publish-remarks](includes/solution-publish-remarks.md)]

## pac solution sync

Sync the current Dataverse solution project to the current state of the solution in your Organization.

[!INCLUDE [solution-sync-intro](includes/solution-sync-intro.md)]


### Optional Parameters

#### `--async` `-a`

Exports solution asynchronously

This parameter requires no value. It is a switch.

#### `--include` `-i`

Which settings should be included in the solution being exported

Use one or more of these values separated by commas:

- `autonumbering`
- `calendar`
- `customization`
- `emailtracking`
- `externalapplications`
- `general`
- `isvconfig`
- `marketing`
- `outlooksynchronization`
- `relationshiproles`
- `sales`

#### `--max-async-wait-time` `-wt`

Max asynchronous wait time in minutes. Default value is 60 minutes

#### `--packagetype` `-p`

When unpacking/extracting, use to specify dual Managed and Unmanaged operation. When packing, use to specify Managed or Unmanaged from a previous unpack 'Both'. Can be: 'Unmanaged', 'Managed' or 'Both'; default: 'Unmanaged'

#### `--processCanvasApps` `-pca`

(Preview) Pack/unpack any Canvas apps (.msapp) while processing the solution. default: false

This parameter requires no value. It is a switch.

#### `--solution-folder` `-f`

Path to the local, unpacked solution folder: either the root of the 'Other/Solution.xml' file or a folder with a .cdsproj file.

[!INCLUDE [solution-sync-remarks](includes/solution-sync-remarks.md)]

## pac solution unpack

Extract solution components from solution.zip onto local filesystem (SolutionPackager)

[!INCLUDE [solution-unpack-intro](includes/solution-unpack-intro.md)]


### Required Parameters

#### `--zipfile` `-z`

The full path to the solution ZIP file


### Optional Parameters

#### `--allowDelete` `-ad`

Dictates if delete operations may occur; default: false.

This parameter requires no value. It is a switch.

#### `--allowWrite` `-aw`

Dictates if write operations may occur; default: false.

This parameter requires no value. It is a switch.

#### `--clobber` `-c`

Enables that files marked read-only can be deleted or overwritten; default: false.

This parameter requires no value. It is a switch.

#### `--disablePluginRemap` `-dpm`

Disabled plug-in fully qualified type name remapping. default: false

This parameter requires no value. It is a switch.

#### `--errorlevel` `-e`

Minimum logging level for log output [Verbose|Info|Warning|Error|Off]; default: Info

#### `--folder` `-f`

The path to the root folder on the local filesystem. When unpacking/extractins, this will be written to, when packing this will be read from.

#### `--localize` `-loc`

Extract or merge all string resources into .resx files.

This parameter requires no value. It is a switch.

#### `--log` `-l`

The path to the log file.

#### `--map` `-m`

The full path to a mapping xml file from which to read component folders to pack.

#### `--packagetype` `-p`

When unpacking/extracting, use to specify dual Managed and Unmanaged operation. When packing, use to specify Managed or Unmanaged from a previous unpack 'Both'. Can be: 'Unmanaged', 'Managed' or 'Both'; default: 'Unmanaged'

#### `--processCanvasApps` `-pca`

(Preview) Pack/unpack any Canvas apps (.msapp) while processing the solution. default: false

This parameter requires no value. It is a switch.

#### `--singleComponent` `-sc`

Only perform action on a single component type [WebResource|Plugin|Workflow|None]; default: None.

#### `--sourceLoc` `-src`

Generates a template resource file. Valid only on Extract. Possible Values are auto or an LCID/ISO code of the language you wish to export. When Present, this will extract the string resources from the given locale as a neutral .resx. If auto or just the long or short form of the switch is specified the base locale for the solution will be used.

#### `--useLcid` `-lcid`

Use LCID's (1033) rather than ISO codes (en-US) for language files.

This parameter requires no value. It is a switch.

#### `--useUnmanagedFileForMissingManaged` `-same`

Use the same XML source file when packaging for Managed and only Unmanaged XML file is found; applies to AppModuleSiteMap, AppModuleMap, FormXml files

This parameter requires no value. It is a switch.

[!INCLUDE [solution-unpack-remarks](includes/solution-unpack-remarks.md)]

## pac solution upgrade

Option to stage the Dataverse solution for upgrade

[!INCLUDE [solution-upgrade-intro](includes/solution-upgrade-intro.md)]


### Required Parameters

#### `--solution-name` `-sn`

Name of the solution


### Optional Parameters

#### `--async` `-a`

Upgrades solution asynchronously

This parameter requires no value. It is a switch.

#### `--max-async-wait-time` `-wt`

Max asynchronous wait time in minutes. Default value is 60 minutes

[!INCLUDE [solution-upgrade-remarks](includes/solution-upgrade-remarks.md)]

## pac solution version

Update build or revision version for solution

[!INCLUDE [solution-version-intro](includes/solution-version-intro.md)]


### Optional Parameters

#### `--buildversion` `-bv`

Build version for solution

**Note**: The value must be a positive integer

#### `--filename` `-fn`

Tracker CSV file name to be used when using filetracking as a strategy. Default value is ControlsStateVersionInfo.csv

#### `--patchversion` `-pv`

**Deprecated**: This parameter will be ignored.
#### `--revisionversion` `-rv`

Revision version for solution

**Note**: The value must be a positive integer

#### `--strategy` `-s`

Updates build version for 'Solution.xml' file using specified strategy. If using gittags, set personal access token in the following environment variable "PacCli.PAT"

Use one of these values:

- `gittags`
- `filetracking`
- `solution`

[!INCLUDE [solution-version-remarks](includes/solution-version-remarks.md)]

[!INCLUDE [solution-remarks](includes/solution-remarks.md)]

### See also

[Microsoft Power Platform CLI Command Groups](index.md)<br />
[Microsoft Power Platform CLI overview](../introduction.md)