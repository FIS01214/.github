# FIS01214 · análise de dados no LHC

Bem-vindo à organização da disciplina **Física Nuclear e de Partículas B** do
IF-UFRGS. Aqui transformamos eventos simulados pelo MadGraph em uma análise
curta, reproduzível e inspirada no fluxo de trabalho do LHC: ler, selecionar,
visualizar e interpretar.

## Projetos em destaque

Comece por um dos exemplos públicos prontos:

- [analise-colab](https://github.com/FIS01214/analise-colab) — roteiro completo
  para Google Colab;
- [analise-swan](https://github.com/FIS01214/analise-swan) — o mesmo fluxo no
  CERN SWAN;

## A ideia da atividade

Cada grupo recebe arquivos LHE de sinal e fundo e constrói uma seleção em
Python. A sequência é simples:

`LHE → objetos físicos → cortes → cutflow e histogramas → interpretação`

Na Parte 1, o foco é ler e validar os eventos. Na Parte 2, a seleção é usada
para comparar sinal e fundo e estimar, de forma didática,
`σ = N / (A · ε · L)`. Os eventos estão no nível de gerador; efeitos de
detector, trigger e pileup ficam como limitações explícitas da análise.

## Como usar

Abra o README do exemplo escolhido antes de iniciar. Ele explica o fluxo de
upload no Colab ou SWAN, a descompactação do ZIP e a inflação dos arquivos
`.lhe.gz`. Os notebooks públicos mostram uma solução completa e reproduzível
para consulta.
