## Resumo — Tratamento de Dados Experimentais

---

### 1. Média $(\bar{x})$

Valor central das repetições:

$$\bar{x} = \frac{\sum x_i}{n}$$

---

### 2. Desvio Padrão $(s)$ e Erro Padrão da Média $(s_{\bar{x}})$

**Desvio padrão** — mede o espalhamento de cada medição individual:

$$s = \sqrt{\frac{\sum(x_i - \bar{x})^2}{n-1}}$$

**Erro padrão da média** — mede a incerteza sobre o valor da própria média:

$$s_{\bar{x}} = \sqrt{\frac{\sum(x_i - \bar{x})^2}{n(n-1)}} = \frac{s}{\sqrt{n}}$$

| | Desvio Padrão $s$ | Erro Padrão $s_{\bar{x}}$ |
|---|---|---|
| Responde | "quanto cada dado varia?" | "quanto a média varia?" |
| Diminui com mais medições? | Não (converge p/ valor fixo) | Sim ($\propto 1/\sqrt{n}$) |
| Usar quando | Descrever dispersão dos dados | Reportar incerteza do resultado final |
| Contexto típico | Laboratório de ensino (mais conservador) | Publicações científicas |

> Sempre deixe explícito qual foi utilizado no relatório.

---

### 3. Erro Absoluto Total

Em medidas com repetições, há **duas fontes independentes de erro** que se combinam em quadratura:

$$\Delta x = \sqrt{\delta_{inst}^2 + s^2}$$

| Fonte | Origem | Exemplo |
|---|---|---|
| $\delta_{inst}$ | Precisão do equipamento (ou propagação de erros) | $\pm 0{,}07$ mL para $V_f - V_i$ |
| $s$ | Espalhamento estatístico das repetições | desvio padrão das triplicatas |

> Se há só **1 medição**: $\Delta x = \delta_{inst}$ apenas — não existe $s$ para combinar.

---

### 4. Propagação de Erros

Depende da operação matemática envolvida:

| Operação | Propaga | Fórmula |
|---|---|---|
| $Q = x \pm y$ | Erro **absoluto** | $\Delta Q = \sqrt{\Delta x^2 + \Delta y^2}$ |
| $Q = x \cdot y$ ou $x/y$ | Erro **relativo** | $\dfrac{\Delta Q}{Q} = \sqrt{\left(\dfrac{\Delta x}{x}\right)^2 + \left(\dfrac{\Delta y}{y}\right)^2}$ |

**Por quê?**
- Na soma, os erros têm a mesma unidade e se acumulam diretamente.
- Na multiplicação, o que importa é o peso proporcional de cada erro ($\Delta x / x$).

---

### 5. Regras de Arredondamento

| Regra | Exemplo |
|---|---|
| Erro com **1 algarismo significativo** | $\Delta V = 0{,}07$ mL |
| Se o erro começar com **1**, usa 2 algarismos | $\Delta V = 0{,}14$ mL |
| O resultado se arredonda na **mesma casa do erro** | $(1{,}15 \pm 0{,}07)$ mL |

---

### 6. Aplicação nos seus dados

**Exemplo — Amostra Prateada 1:**

**Dados brutos coletados:**

| Grandeza | Medição 1 | Medição 2 | Medição 3 |
|---|---|---|---|
| Massa | $(3{,}211 \pm 0{,}001)$ g | $(3{,}210 \pm 0{,}001)$ g | $(3{,}211 \pm 0{,}001)$ g |
| Proveta (vazia) | $(6{,}00 \pm 0{,}05)$ mL | $(6{,}00 \pm 0{,}05)$ mL | $(6{,}00 \pm 0{,}05)$ mL |
| Proveta + amostra | $(7{,}20 \pm 0{,}05)$ mL | $(7{,}10 \pm 0{,}05)$ mL | $(7{,}15 \pm 0{,}05)$ mL |
| Volume deslocado | $(1{,}20 \pm 0{,}07)$ mL | $(1{,}10 \pm 0{,}07)$ mL | $(1{,}15 \pm 0{,}07)$ mL |

**Passo 1 — Propagação do erro na subtração de volumes:**

O volume deslocado é calculado por:

$$V_{deslocado} = V_{proveta+amostra} - V_{proveta}$$

Como é uma subtração, propaga-se o erro absoluto:

$$\Delta V_{deslocado} = \sqrt{(\Delta V_{proveta+amostra})^2 + (\Delta V_{proveta})^2} = \sqrt{(0{,}05)^2 + (0{,}05)^2} = \sqrt{0{,}005} \approx 0{,}07 \text{ mL}$$

Por isso os três volumes deslocados já ficam com $\pm 0{,}07$ mL.

**Passo 2 — Média e desvio padrão dos volumes deslocados:**

| Etapa | Cálculo | Resultado |
|---|---|---|
| Média do volume | $(1{,}20 + 1{,}10 + 1{,}15)/3$ | $1{,}15$ mL |
| Desvio padrão ($s$) | $\sqrt{(0{,}05^2+0{,}05^2+0)/2}$ | $0{,}05$ mL |
| Erro propagado ($\delta_{inst}$) | do Passo 1: $\sqrt{0{,}05^2+0{,}05^2}$ | $0{,}07$ mL |
| **Erro total** | $\sqrt{\delta_{inst}^2 + s^2} = \sqrt{0{,}07^2 + 0{,}05^2}$ | $\approx 0{,}09$ mL |
| **Volume final** | | $(1{,}15 \pm 0{,}09)$ mL |

> Aqui combinam-se **duas fontes independentes**: o erro propagado da subtração $V_f - V_i$ (0,07 mL, fixo para cada medição) e o espalhamento estatístico das 3 repetições (0,05 mL). Para Amostras 2–5, como há apenas 1 medição, usa-se somente $\delta_{inst} = \pm 0{,}07$ mL.

**Passo 3 — Calculando a densidade e sua incerteza:**

$$\rho = \frac{m}{V} = \frac{3{,}211}{1{,}15} \approx 2{,}79 \text{ g/mL}$$

Aplicando a propagação para divisão (erro relativo):

$$\frac{\Delta\rho}{\rho} = \sqrt{\left(\frac{\Delta m}{m}\right)^2 + \left(\frac{\Delta V}{V}\right)^2} = \sqrt{\left(\frac{0{,}001}{3{,}211}\right)^2 + \left(\frac{0{,}09}{1{,}15}\right)^2}$$

$$\frac{\Delta\rho}{\rho} = \sqrt{(0{,}03\%)^2 + (7{,}8\%)^2} \approx 7{,}8\%$$

Convertendo para erro absoluto:

$$\Delta\rho = \rho \times 7{,}8\% = 2{,}79 \times 0{,}078 \approx 0{,}2 \text{ g/mL}$$

| Grandeza | Erro relativo | Contribuição |
|---|---|---|
| Massa $\Delta m / m$ | $0{,}001/3{,}211 \approx 0{,}03\%$ | desprezível |
| Volume $\Delta V / V$ | $0{,}09/1{,}15 \approx 7{,}8\%$ | dominante |

$$\boxed{\rho = (2{,}8 \pm 0{,}2) \text{ g/mL}}$$

> **Conclusão prática:** nos seus experimentos, o erro da **proveta domina** sobre o da balança — investir em volumetria mais precisa reduz muito mais a incerteza final do que usar uma balança melhor.