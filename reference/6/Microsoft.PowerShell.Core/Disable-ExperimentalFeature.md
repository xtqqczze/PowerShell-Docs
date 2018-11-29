---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
online version:
schema: 2.0.0
---

# Disable-ExperimentalFeature

## SYNOPSIS
Disable an experimental feature on startup of new instance of PowerShell.

## SYNTAX
```
Disable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The `Disable-ExperimentalFeature` cmdlet disables experimental features by removing the named
experimental features from the `powershell.config.json` settings file read on PowerShell startup.

> [!NOTE]
> Any changes to experimental feature state only takes effect on restart of PowerShell

## EXAMPLES

### Example 1
```powershell
PS C:\> Disable-ExperimentalFeature PSImplicitRemotingBatching
```

```output
Name                                Enabled Source                              Description
----                                ------- ------                              -----------
PSImplicitRemotingBatching             True PSEngine                            Batch implicit remoting proxy commands to improve performance
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

In this example, if this experimental feature was previously enabled, then the `powershell.config.json`
file is updated for the user to not enable that feature once PowerShell is restarted.
The `Enabled` value represents the current state, not the new desired state.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name or names of the experimental features to disable.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope
Determines which `powershell.config.json` to update whether it affects all users or
just the current user.

```yaml
Type: ConfigScope
Parameter Sets: (All)
Aliases:
Accepted values: AllUsers, CurrentUser

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### ExperimentalFeature

Pipe instances of ExperimentalFeature from `Get-ExperimentalFeature` cmdlet to disable.

## OUTPUTS

### ExperimentalFeature

Affected instances of ExperimentalFeature that will be disabled upon restart of PowerShell.

## NOTES

Changes to state of an experimental feature only take effect on restart of PowerShell.

## RELATED LINKS

[Enable-ExperimentalFeature](Enable-ExperimentalFeature.md)
[Get-ExperimentalFeature](Get-ExperimentalFeature.md)