# Cyber Attack Defend (CAD) Intelligence

## Python Script Execution via Installer Binary (Python LOLBin)

  **INDICATOR**: ```python.exe / pythonw.exe "C:\Users\<username>\AppData\<path>\<script_name>.py"```
  
<details>

<summary>CAD Details</summary>

| TITLE | DETAILS |
| :-----------: | :-----------: |
| _PLATFORM(S)_ | Windows |
| _ARTIFACT(S)_ | d3f:ExecutableScript; d3f:ProcessTree |
| _COUNTERMEASURE(S)_ | d3f:FileAnalysis; d3f:ProcessSpawnAnalysis |
| _EVIDENCE(S)_ | edr:```Parent Process (powershell.exe / cmd.exe) > Child Process ("python.exe" / "pythonw.exe" <script_path>.py)```; <br> siem:```Event ID: 4688```; ```Sysmon Event ID: 1``` |
| _DETECTION_ | [Execute Python Scripts via Python Installer Binary](https://detection.fyi/tsale/sigma_rules/lol_bins/proc_creation_windows_setup_pythonw/) |
| _HUNT_ | ```(Image:("*\\python.exe" OR "*\\pythonw.exe")) AND (CommandLine:"*\\AppData\\*") AND (CommandLine:"*.py*")``` |
| _ACTOR(S) SEEN_ | N/A |
| _MALWARE(S) SEEN_ | CLickFix, modeloRAT  |
| _REFERENCE(S)_ | [Trend Mirco](https://www.trendmicro.com/) |

</details>

---
