---
title: require-vscomponent
description: devinit tool require-vscomponent.
ms.date: 11/20/2020
ms.topic: reference
author: andysterland
ms.author: andster
manager: jmartens
ms.workload:
- multiple
monikerRange: ">= vs-2019"
ms.prod: visual-studio-windows
ms.technology: devinit
---
# require-vscomponent

The `require-vscomponent` tool is used to import Visual Studio configurations to existing Visual Studio. Read more about `.vsconfig` [here](../install/import-export-installation-configurations.md).

## Usage

If both the `input` and `additionalOptions` properties are omitted or empty, then the tool will follow the [default](#default-behavior) behavior detailed below.

| Name                                     | Type   | Required | Value                                                                |
|------------------------------------------|--------|----------|----------------------------------------------------------------------|
| **comments**                             | string | No       | Optional comments property. Not used.                                |
| [**input**](#input)                      | string | No       | The full path of `.vsconfig`. See [input](#input) below for details. |
| [additionalOptions](#additional-options) | string | No       | See [Additional options](#additional-options) below for details.     |

### Input

The `input` property is used to specify the full path of `.vsconfig` file. If not mentioned, the tool will search for a `.vsconfig` in current directory and pass the value to the Visual Studio Installer.

### Additional options

Not used.

### Default behavior

The default behavior of the `require-vscomponent` tool is to look for a `.vsconfig` file in current directory and run the Visual Studio Installer with these details in quiet mode. `require-vscomponent` only supports modifying an existing Visual Studio installation.

## Example usage
Below is an example of how to run `require-vscomponent` using a `.devinit.json`.

#### .devinit.json that will import the configurations of a given .vsconfig file path:
```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "comments": "A sample dot-devinit file.",
    "run": [
        {
            "tool": "require-vscomponent",
            "input": "C:\\.vsconfig"
        }
    ]
}
```