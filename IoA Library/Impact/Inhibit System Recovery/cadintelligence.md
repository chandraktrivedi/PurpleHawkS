# Cyber Attack Defend Intelligence

| ACTOR | INDICATOR | ARTIFACT | COUNTERMEASURE | DETECTION STRATEGIES | DETECTION | HUNT | REFERENCE |
| :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: |
| Settra | ```reagentc.exe /disable``` | d3f:Process | d3f:ProcessAnalysis | DET0329 | [Windows Recovery Environment Disabled Via Reagentc](https://sigma.nasbench.dev/rules/db1c21e4-cd66-4b4e-85ca-590f0780529c) | ```(Image:"*\\reagentc.exe") AND (CommndLine:*disable*)  ``` |  [Huntress](https://www.huntress.com/) |
