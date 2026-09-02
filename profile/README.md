# FIS01214 — Análise de Dados em Física de Partículas

Bem-vindo à organização GitHub da disciplina **Física Nuclear e de Partículas B
(FIS01214)** do IF-UFRGS.

Aqui os estudantes trabalham com eventos simulados em formato **LHE — Les
Houches Event**, produzidos com **MadGraph5_aMC@NLO**, para construir uma
análise inspirada no fluxo de uma busca ou medida no LHC: ler eventos,
selecionar objetos, comparar sinal e fundo, construir histogramas, estimar
yields e discutir limitações físicas da análise.

O objetivo não é apenas “rodar um notebook”. A proposta é praticar uma análise
de dados de ponta a ponta: entender o arquivo de entrada, formular critérios de
seleção, validar hipóteses, documentar decisões e interpretar resultados com
cuidado.

## Como começar

Cada estudante ou grupo recebe um repositório público de tarefa:

- [tarefa1](https://github.com/FIS01214/tarefa1)
- [tarefa2](https://github.com/FIS01214/tarefa2)
- [tarefa3](https://github.com/FIS01214/tarefa3)
- [tarefa4](https://github.com/FIS01214/tarefa4)
- [tarefa5](https://github.com/FIS01214/tarefa5)
- [tarefa6](https://github.com/FIS01214/tarefa6)
- [tarefa7](https://github.com/FIS01214/tarefa7)
- [tarefa8](https://github.com/FIS01214/tarefa8)
- [tarefa9](https://github.com/FIS01214/tarefa9)
- [tarefa10](https://github.com/FIS01214/tarefa10)

Dentro de cada repositório há:

- amostras `data/sinal.lhe.gz` e `data/fundo.lhe.gz`;
- notebooks de análise para as Partes 1 e 2;
- instruções gerais da atividade;
- pasta para resultados e gráficos produzidos durante o trabalho.

Os repositórios de tarefa não incluem notebooks de referência. Eles foram
preparados para que o estudante escreva a análise com apoio de um agente de IA,
copiando para as células vazias o código que for gerado, revisado e executado.

## Uso no Google Colab

Um fluxo simples para trabalhar sem instalar nada localmente:

1. Abra o repositório da sua tarefa no GitHub e use **Code → Download ZIP**.
2. Baixe também o notebook indicado pelo professor.
3. Abra o notebook no Google Colab e, no painel **Arquivos**, faça upload do
   `.ipynb` e do `.zip` no mesmo ambiente de execução; o ZIP será o arquivo de
   dados usado pelo notebook.
4. Antes de começar a análise, peça ao agente que gere e execute código para:
   - localizar e descompactar o arquivo `.zip`;
   - entrar na pasta extraída;
   - inflar com `gzip` `data/sinal.lhe.gz` e `data/fundo.lhe.gz`, criando
     `data/sinal.lhe` e `data/fundo.lhe` sem apagar os originais;
   - confirmar a presença das quatro versões na pasta `data/`.
5. Execute as etapas do notebook a partir da pasta extraída.

Os notebooks têm uma seção inicial `0. Preparação no Google Colab` para lembrar
esse passo.

## O que você vai analisar

Os arquivos LHE contêm eventos em nível de gerador. Isso significa que eles
representam partículas e partons antes de uma simulação completa de detector.
Essa distinção é essencial:

- léptons e fótons podem ser usados diretamente como objetos de gerador;
- neutrinos carregam energia invisível;
- quarks e glúons no LHE são partons, não jatos reconstruídos;
- efeitos de detector, trigger, pileup e reconstrução não estão incluídos.

Essa limitação faz parte da atividade. Uma boa análise deve deixar claro o que
foi medido em nível de gerador e o que ainda seria necessário para aproximar uma
análise experimental real.

## Partes da atividade

### Parte 1 — ler, validar e selecionar eventos

Na primeira parte, o foco é construir a base técnica da análise:

- abrir os arquivos LHE;
- extrair partículas finais e metadados do evento;
- calcular grandezas cinemáticas como `pT`, `eta`, `phi` e massas invariantes;
- comparar sinal e fundo;
- definir cortes de seleção;
- construir um cutflow simples.

Há três estilos de notebook, para distribuir abordagens diferentes entre os
grupos:

- leitura direta do arquivo texto LHE;
- leitura usando uma biblioteca como `pylhe`;
- leitura convertendo eventos para uma estrutura tabular com `pandas.DataFrame`.

### Parte 2 — interpretar fisicamente a seleção

Na segunda parte, a análise avança para perguntas mais próximas de uma medida:

- conservação de quadrimomento;
- reconstrução de massas invariantes;
- normalização por seção de choque e luminosidade;
- comparação quantitativa entre sinal e fundo;
- interpretação estatística básica;
- estimativa simplificada de seção de choque por
  `sigma = N / (aceitação × eficiência × luminosidade)`.

O ponto importante é conectar o código à física. Um gráfico bonito sem
interpretação física não é suficiente; uma seleção bem justificada vale mais do
que uma sequência longa de comandos sem controle.

## Para agentes de IA

Os notebooks foram escritos para colaboração com agentes. O agente deve gerar
código, explicar hipóteses e apontar verificações, mas o estudante continua
responsável por:

- ler o que foi gerado;
- executar as células;
- conferir se os resultados fazem sentido;
- explicar as escolhas no relatório;
- identificar limitações do método.

Evite aceitar respostas automáticas sem validação. Em análise de dados, o erro
mais comum não é o código quebrar; é o código rodar e produzir um número que
parece plausível, mas responde à pergunta errada.

## Para docentes e monitores

O repositório privado `template` mantém a versão completa do material:

- notebooks de estudante;
- notebooks de referência;
- banco de arquivos LHE;
- instruções para recriar repositórios de tarefa em novos semestres;
- arquivos internos de apoio ao fluxo de manutenção.

Os repositórios públicos `tarefa*` são versões reduzidas e independentes,
contendo apenas o necessário para os estudantes.

## Ciclo de manutenção e planejamento

O trabalho de manutenção é organizado por milestones nos repositórios de apoio:

- `template`: **Template 2026 — Notebooks e análise** e **Template 2026 —
  Governança e manutenção**;
- `geracao-amostras`: **Geração 2026 — Validação física**;
- `.github`: **Organização 2026 — Exemplo e distribuição** e **Organização
  2026 — Automação de tarefas**.

As issues abertas são associadas à milestone correspondente e permanecem
auditáveis. Os repositórios `tarefa*` não recebem milestones próprias enquanto
forem apenas entregas distribuídas aos estudantes e não tiverem backlog de
manutenção; essa decisão será revisada a cada semestre. Uma milestone só deve
ser encerrada quando não houver issues ou pull requests abertos associados.
