# FIS01214 · análise de dados no LHC

Bem-vindo à organização da disciplina **Física Nuclear e de Partículas B** do
IF-UFRGS. Aqui transformamos eventos simulados pelo MadGraph em uma análise
curta, reproduzível e inspirada no fluxo de trabalho do LHC: ler, selecionar,
visualizar e interpretar.

## Projetos em destaque

Comece por um dos exemplos prontos ou escolha uma tarefa:

- [analise-colab](https://github.com/FIS01214/analise-colab) — roteiro completo
  para Google Colab;
- [analise-swan](https://github.com/FIS01214/analise-swan) — o mesmo fluxo no
  CERN SWAN;
- [tarefa1–tarefa10](https://github.com/FIS01214/tarefa1) — conjuntos de
  atividades para estudantes.

Os repositórios de manutenção ficam separados: [`template`](https://github.com/FIS01214/template)
guarda os notebooks e instruções de referência, e
[`geracao-amostras`](https://github.com/FIS01214/geracao-amostras) documenta a
produção das amostras LHE.

## A ideia da atividade

Cada grupo recebe arquivos LHE de sinal e fundo e constrói uma seleção em
Python. A sequência é simples:

`LHE → objetos físicos → cortes → cutflow e histogramas → interpretação`

Na Parte 1, o foco é ler e validar os eventos. Na Parte 2, a seleção é usada
para comparar sinal e fundo e estimar, de forma didática,
`σ = N / (A · ε · L)`. Os eventos estão no nível de gerador; efeitos de
detector, trigger e pileup ficam como limitações explícitas da análise.

## Como usar

Abra o README do repositório escolhido antes de iniciar. Ele explica o fluxo de
upload no Colab ou SWAN, a descompactação do ZIP e a inflação dos arquivos
`.lhe.gz`. Os notebooks de tarefa deixam as células de código para o estudante
preencher com auxílio de um agente; os exemplos públicos mostram uma solução
completa para consulta.

Para docentes e monitores, o material privado contém também os notebooks de
referência, os dados de entrada e a documentação para recriar a distribuição
em novos semestres.
