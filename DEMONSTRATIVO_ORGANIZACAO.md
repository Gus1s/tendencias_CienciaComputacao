# Demonstrativo da organização do repositório

Este documento explica o que foi alterado, por que a organização foi escolhida
e como continuar o trabalho sem perder a autoria ou confundir atividades.

## 1. Objetivo da mudança

O repositório possuía atividades com nomes diferentes e projetos guardados em
unidades que não correspondiam ao cronograma. A reorganização criou um padrão
único:

```text
Unidade → mês → data e tema → arquivos da atividade
```

Assim, uma atividade de 27 de agosto sobre Engenharia de Prompt fica em:

```text
Unidade_01/
└── 08_Agosto/
    └── 27_08_Engenharia_de_Prompt/
        ├── atividade.md
        └── material_complementar.md
```

## 2. Estrutura resultante

```text
tendencias_CienciaComputacao/
├── Unidade_01/     Fundamentos de IA e Engenharia de Prompt
├── Unidade_02/     Programação Assistida por IA
├── Unidade_03/     Low Code, No Code e Vibecode
├── Unidade_04/     Agentes de IA, ética e projeto final
├── Avaliacoes/     A2, A1 e Avaliação Final
├── README.md
├── ORGANIZACAO_ATIVIDADES.md
└── PROMPT_COPILOT_ATIVIDADES_PENDENTES.md
```

Cada unidade tem um `README.md` funcionando como índice. Isso permite começar
pela página principal e navegar até a aula desejada sem procurar nomes soltos.

## 3. Principais movimentações

| Antes | Depois | Motivo |
|---|---|---|
| `Unidade_01/atividadedia20` | `Unidade_01/08_Agosto/20_08_LLMs_e_Logica/atividade.md` | Identificar data e assunto |
| `Unidade_01/atividade_27_08.md` | `Unidade_01/08_Agosto/27_08_Engenharia_de_Prompt/atividade.md` | Aplicar o padrão de pastas |
| `Unidade_01/atividade_03_09.md` | `Unidade_01/09_Setembro/03_09_Refinamento_de_Prompts/atividade.md` | Separar agosto de setembro |
| `Unidade_02/AgendaFacil` | `Unidade_03/10_Outubro/08_10_Introducao_Low_Code_No_Code/AgendaFacil` | Relacionar o projeto ao conteúdo Low Code/No Code |
| `Unidade_03/HelpDeskAI` | `Unidade_03/10_Outubro/29_10_Limitacoes_e_Mini_Projeto/HelpDeskAI` | Relacionar o trabalho ao mini-projeto de 29/10 |

Os arquivos foram movidos com o Git, mantendo o histórico de renomeação. O
HelpDesk AI continua com o arquivo `ORIGEM.md` e os créditos da dupla.

## 4. Como as pendências foram tratadas

Quando não havia uma entrega comprovável, não foi criada uma resposta fictícia.
Foi adicionado um arquivo `PENDENTE.md` contendo:

1. a data e o tema da aula;
2. o estado atual da atividade;
3. quais evidências ainda precisam ser incluídas.

Exemplo:

```text
Unidade_02/09_Setembro/24_09_Automacao_com_IA/PENDENTE.md
```

Ao realizar a atividade, o procedimento recomendado é:

1. ler o enunciado real fornecido em sala;
2. produzir e testar a solução;
3. registrar entradas, saídas e dificuldades reais;
4. substituir `PENDENTE.md` por `atividade.md`, ou manter o marcador junto da
   entrega até que todos os itens estejam comprovados;
5. criar um commit com uma descrição verdadeira da alteração.

## 5. Por que as avaliações estão separadas

A avaliação A2 e o mini-projeto aparecem em 29/10, mas são registros distintos.
O mesmo vale para o projeto final e a avaliação A1 em 26/11. Por isso foi criada
a pasta `Avaliacoes/`, evitando que um projeto seja apresentado como se fosse a
avaliação individual.

## 6. Arquivos de orientação

- `README.md`: página inicial e acesso às unidades;
- `ORGANIZACAO_ATIVIDADES.md`: tabela completa de datas, temas e situação;
- `PROMPT_COPILOT_ATIVIDADES_PENDENTES.md`: prompt para auditar pendências sem
  inventar conteúdo;
- `PENDENTE.md`: marcador de uma evidência que ainda não está no repositório;
- `ORIGEM.md`: procedência e autoria de material trazido de outro repositório.

## 7. Fluxo de trabalho recomendado

```text
Consultar o plano
        ↓
Abrir a pasta da data
        ↓
Ler atividade.md ou PENDENTE.md
        ↓
Produzir e testar a atividade
        ↓
Documentar evidências reais
        ↓
Revisar autoria e links
        ↓
Criar commit descritivo
```

Exemplos de mensagens de commit adequadas:

```text
Conclui exercício de refatoração de 17/09
Adiciona testes do script de automação de 24/09
Documenta análise de privacidade do HelpDesk AI
```

## 8. Como conferir se está organizado

Antes de enviar uma nova atividade, verifique:

- a pasta corresponde à unidade, ao mês e à data;
- o arquivo explica o que foi realmente feito;
- código ou automação tem instruções de execução;
- resultados e testes são verificáveis;
- trabalhos em grupo identificam todos os autores;
- links do Markdown abrem os arquivos corretos;
- a mensagem do commit descreve a mudança sem alterar artificialmente a data.

## 9. Resultado prático

Com esse padrão, a professora pode acompanhar o conteúdo na ordem do plano de
aulas, enquanto o aluno consegue enxergar rapidamente o que está concluído, o
que possui apenas material parcial e o que ainda precisa ser produzido.
