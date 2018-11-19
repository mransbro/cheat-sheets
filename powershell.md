# PowerShell

```powershell
# Single line comments are simple
```

```powershell
<#
Multi line comments are
also simple to
create
#>
```

```powershell
@"
Multi line strings are possible.
Just make sure,
the opening @" token must be at the end of the line
and the ending token at the beginning of the line
"@
```

```powershell
# All variables in PowerShell start with $ and they dont care how you capitalise them
$ImAVarIablE = 'Store data in me'
$AMIVALID = 'totally'
$iamalsovalid = $True

# Although it doesnt affect the variable, the accpted PowerShell formatting is to use PascalCase
$LooksLikeThis = 'Much easier to read'
```

## Help

```powershell
# Powershell has brilliant built in help
Help or Get-Help
```

```powershell
# Get-Command 
Get-command -verb 'add' -module 'ActiveDirectory'
```

```powershell
# Get member or its alias gm returns the object type and all of its Methods and properties.
$someData | Get-Member
# If we pass an array with different datypes get member will show use the details of the objects inside the array.

```

```powershell
# GetType() doesnt look inside the object. If 
$info.GetType()
```

## Data types

```powershell
# Array
$a = @()
```

```powershell
# Array List
$Time = New-Object System.Collections.ArrayList
$Time.add([DateTime]'12:38')
```

```powershell
# Hashtables
$b = @{'':}
```

```powershell
# Tuple
$c = [tuple]::Create(12,'Monday',$True)
```

```powershell



## Functions

# Function names, in your own code you can give functions any name but if you're making them publically available they should use the verb-noun format.

```powershell
function Hello-World ($name) {
    Write-Output "Hello $name"
}
```

