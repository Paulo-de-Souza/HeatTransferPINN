### O que é estudado no notebook base

#### 1. Problema direto: equação do calor

É resolvida a equação

$$
\frac{\partial u}{\partial t}=\alpha\frac{\partial^2u}{\partial x^2},
\qquad x\in[0,1],\quad t\in[0,1],
$$

com condição inicial senoidal e condições de contorno de Dirichlet nulas. A solução exata é utilizada para comparar:

- a solução de referência;
- a solução prevista pela PINN;
- o erro absoluto espaço-temporal.

O exemplo utiliza comprimento da barra `L = 1`, modo inicial `n = 1` e difusividade térmica `alpha = 0.4`.

#### 2. Problema direto: equação de difusão com termo-fonte

Em seguida, é considerada uma equação de difusão em `x ∈ [-1, 1]`, com termo-fonte construído a partir de uma solução conhecida. Esse exemplo ajuda a distinguir a equação de calor, como um caso particular de difusão, de uma equação de difusão com fonte explícita.

#### 3. Problema inverso: identificação de `k`

O parâmetro `k` da equação

$$
\frac{\partial T}{\partial t}=k\frac{\partial^2T}{\partial x^2}
$$

é tratado como uma variável treinável. A rede recebe observações de temperatura e utiliza simultaneamente:

- o resíduo da equação diferencial;
- a condição inicial;
- as condições de contorno;
- observações pontuais da solução.

O valor de referência é `k = 0.4`. O notebook apresenta dois cenários de inicialização, começando com `k = 5.0` e com `k = 1.0`, para observar como a estimativa evolui durante o treinamento.

| Cenário | Observações utilizadas | Estimativa inicial | Valor de referência |
|---|---|---:|---:|
| Identificação de `k` | 10 pontos ao longo da barra em `t = 0.5` | `k = 5.0` ou `k = 1.0` | `k = 0.4` |

#### 4. Problema inverso: identificação de `C`

Também é estudada a equação de difusão com termo-fonte, agora com um coeficiente desconhecido `C`. Nesse caso, o valor de referência é `C = 1.0`, enquanto o treinamento começa com uma estimativa inicial diferente.

Neste experimento, são utilizadas 10 observações ao longo do domínio em `t = 1.0`, com estimativa inicial `C = 2.0`.

Esse exemplo mostra como uma PINN pode ser utilizada não apenas para aproximar uma solução, mas também para inferir parâmetros físicos a partir de dados e das leis de conservação representadas pela equação diferencial.

## Conceitos de PINNs explorados

Ao longo dos notebooks, a rede neural aproxima o campo físico, por exemplo `u(x,t)` ou `T(x,t)`. A função de perda combina diferentes informações do problema:

$$
\mathcal{L}=\mathcal{L}_{\mathrm{PDE}}
 +\mathcal{L}_{\mathrm{CC}}
 +\mathcal{L}_{\mathrm{CI}}
 +\mathcal{L}_{\mathrm{dados}}.
$$

Em termos gerais:

- `L_PDE` penaliza a violação da equação diferencial nos pontos internos do domínio;
- `L_CC` penaliza a violação das condições de contorno;
- `L_CI` penaliza a violação da condição inicial;
- `L_dados` aproxima as observações disponíveis.

Nos problemas inversos, o parâmetro físico desconhecido também participa do treinamento. Assim, a rede procura uma solução que seja simultaneamente compatível com a física, com as condições impostas e com os dados observados.

O notebook também permite observar o uso de diferenciação automática, dos otimizadores **Adam** e **L-BFGS**, do erro relativo `L2` e de métricas de erro absoluto.
