# Cyber Attack Defend Intelligence

## REAgentC.exe
<details>
<summary>Click Here for CAD Details</summary>

| PLATFORMS | INDICATOR | ARTIFACT | COUNTERMEASURE | DETECTION STRATEGIES | DETECTION | HUNT | ACTOR | REFERENCE |
| :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: |
| Windows | ```reagentc.exe /disable``` | d3f:Process | d3f:ProcessAnalysis | DET0329 | [Windows Recovery Environment Disabled Via Reagentc](https://sigma.nasbench.dev/rules/db1c21e4-cd66-4b4e-85ca-590f0780529c) | ```(Image:"*\\reagentc.exe") AND (CommndLine:*disable*)``` | Settra |  [Huntress](https://www.huntress.com/) |

</details>
