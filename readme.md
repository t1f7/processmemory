

# ProcessMemory
Little shitty library i ~~made~~ took from (https://github.com/CSharpProgramming/ProcessMemory and updated for my needs) that can do the following: Read, Write, Query memory regions and AOB Scan Processes 64Bit and 32Bit.

Example for those who need it i guess

```csharp
ProcessStream stream = new ProcessStream(Process.GetProcessesByName("NAME_OF_PROCESS").First());
//Each byte is separated by a space, and each ?? indicates an wildcard
HexPattern p = new HexPattern("?? ?? 0x32 ?? 0x43");
long address = stream.PatternScan(p);
```

or

```csharp
HexPattern matrixPat = new HexPattern("00 0A FC 01 00 00 00 00 00 0A FB 01 00 00 00 00");
pointerMatrix = Global.stream.PatternScan(matrixPat, 0x00000000, 4096 * 3, 0x600000000);
if (pointerMatrix != -1)
{
    pointerMatrix += 0x60;
}
```