# Cyber Attack Defend (CAD) Intelligence

## REAgentC.exe

**INDICATOR**: ```reagentc.exe /disable```

<details>
<summary>CAD Details</summary>

| TITLE| DETAILS |
| :-----------: | :-----------: |
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
## vssadmin.exe

**INDICATOR**: ```vssadmin.exe delete shadows /all /quiet```

<details>
<summary>CAD Details</summary>

| TITLE| DETAILS |
| :-----------: | :-----------: |
| _PLATFORMS_ | Windows |
| _ARTIFACT_ | d3f:Process |
| _COUNTERMEASURE_ | d3f:ProcessAnalysis |
| _DETECTION STRATEGIES_ | [DET0329](https://attack.mitre.org/detectionstrategies/DET0329/) |
| _DETECTION_ | [Shadow Copies Deletion Using Operating Systems Utilities](https://sigma.nasbench.dev/rules/c947b146-0abc-4c87-9c64-b17e9d7274a2) |
| _HUNT_ | ```(Image:"*\\vssadmin.exe") AND (CommndLine:*delete* AND *shadows*)``` |
| _ACTOR SEEN_ | Medusa |
| _REFERENCE_ | [CISA](https://www.cisa.gov/) |

</details>

---
