# Aula 08 — PINNs com DeepXDE

Esta aula apresenta a aplicação de redes neurais informadas pela física (PINNs) a problemas de condução de calor utilizando a biblioteca **DeepXDE**.

## Notebooks

- **Aula08_01 — Problema 2D direto:** solução da equação de Laplace com e sem dados internos sintéticos. São comparadas a solução analítica, a resposta da PINN e o erro absoluto.

- **Aula08_02 — Problema 1D direto com geração:** solução de uma parede com geração uniforme de calor. O notebook compara uma implementação inicial, uma formulação corrigida e uma formulação normalizada, considerando casos com e sem dados.

- **Aula08_03 — Problema 1D inverso:** identificação do parâmetro $C=\dot q/k$ a partir de dados internos de temperatura. O notebook acompanha a evolução do parâmetro durante o treinamento.

## O que se espera compreender

Ao final da aula, o aluno deve compreender:

- como transformar uma equação diferencial e suas condições de contorno em um problema para uma PINN;
- a diferença entre um problema direto e um problema inverso;
- como dados internos podem ser incorporados ao treinamento;
- por que a normalização das variáveis pode melhorar a estabilidade numérica;
- como interpretar a função de perda, as curvas de convergência, os erros e os campos de temperatura;
- que a solução analítica pode ser usada para validar a PINN e gerar dados sintéticos, mas não é necessária para treinar um problema direto sem dados.

Os notebooks são exemplos didáticos. O objetivo principal é compreender o fluxo de construção, treinamento e avaliação de uma PINN, e não apenas reproduzir os valores finais.
