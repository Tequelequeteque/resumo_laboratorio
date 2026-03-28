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

Combina o **erro instrumental** ($\delta_{inst}$, dado pelo equipamento) com o **desvio padrão** ($s$, das repetições), que são fontes independentes:

$$\Delta x = \sqrt{\delta_{inst}^2 + s^2}$$

> Se há só 1 medição: $\Delta x = \delta_{inst}$ apenas.

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

| Etapa | Cálculo | Resultado |
|---|---|---|
| Média do volume | $(1{,}20 + 1{,}10 + 1{,}15)/3$ | $1{,}15$ mL |
| Desvio padrão | $\sqrt{(0{,}05^2+0{,}05^2+0)/2}$ | $0{,}05$ mL |
| Erro total (proveta) | $\sqrt{0{,}05^2 + 0{,}05^2}$ | $\approx 0{,}07$ mL |
| **Volume final** | | $(1{,}15 \pm 0{,}07)$ mL |
| Densidade $\rho = m/V$ | erro relativo dominado pela proveta | $\approx 6{,}1\%$ de incerteza |

> **Conclusão prática:** nos seus experimentos, o erro da **proveta domina** sobre o da balança — investir em volumetria mais precisa reduz muito mais a incerteza final do que usar uma balança melhor.