# Cyber Attack Defend Intelligence

## REAgentC.exe
---
INDICATOR

```reagentc.exe /disable```

<details>
<summary>CAD Details</summary>
  
| TITLE| DETAILS |
| :-----------: | :-----------: |
| _INDICATOR_ | ```reagentc.exe /disable``` |
| _PLATFORMS_ | Windows |
| _ARTIFACT_ | d3f:Process |
| _COUNTERMEASURE_ | d3f:ProcessAnalysis |
| _DETECTION STRATEGIES_ | [DET0329](https://attack.mitre.org/detectionstrategies/DET0329/) |
| _DETECTION_ | [Windows Recovery Environment Disabled Via Reagentc](https://sigma.nasbench.dev/rules/db1c21e4-cd66-4b4e-85ca-590f0780529c) |
| _HUNT_ | ```(Image:"*\\reagentc.exe") AND (CommndLine:*disable*)``` |
| _ACTOR SEEN_ | Settra |
| _REFERENCE_ | [Huntress](https://www.huntress.com/) |

</details>

---
INDICATOR

```reagentc.exe /disable```

<details>
<summary>CAD Details</summary>
  
| TITLE| DETAILS |
| :-----------: | :-----------: |
| _INDICATOR_ | ```reagentc.exe /disable``` |
| _PLATFORMS_ | Windows |
| _ARTIFACT_ | d3f:Process |
| _COUNTERMEASURE_ | d3f:ProcessAnalysis |
| _DETECTION STRATEGIES_ | [DET0329](https://attack.mitre.org/detectionstrategies/DET0329/) |
| _DETECTION_ | [Windows Recovery Environment Disabled Via Reagentc](https://sigma.nasbench.dev/rules/db1c21e4-cd66-4b4e-85ca-590f0780529c) |
| _HUNT_ | ```(Image:"*\\reagentc.exe") AND (CommndLine:*disable*)``` |
| _ACTOR SEEN_ | Settra |
| _REFERENCE_ | [Huntress](https://www.huntress.com/) |

</details>

