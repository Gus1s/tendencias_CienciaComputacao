# 19/11 — Viés algorítmico e responsabilidade social

**Unidade:** IV — Agentes e Ética

**Valor:** 1,0 ponto

**Situação:** análise atualizada e vinculada aos testes executáveis da versão 2.0.

## Objetivo

Analisar riscos de viés, privacidade e automação excessiva na priorização de
chamados, relacionando medidas de mitigação a testes verificáveis do HelpDesk AI
2.0.

## Riscos e controles implementados

| Risco | Impacto possível | Controle na versão 2.0 | Teste relacionado |
|---|---|---|---|
| linguagem informal ou erro de digitação | usuário menos técnico recebe classificação pior | busca tolerante e análise do incidente | `TC-07` |
| tom hostil | punição indevida pela forma de escrita | sinaliza o tom sem reduzir prioridade | `TC-08` |
| gênero ou nome do solicitante | tratamento diferente para relatos idênticos | decisão baseada em setor e incidente | `TC-19` |
| prioridade setorial rígida | RH/Administrativo fica indefinidamente na fila | reincidência e aging anti-inanição | `TC-20` e `TC-21` |
| decisão subestimada | impacto real não capturado pelo agente | botão de contestação e revisão humana | `TC-22` |
| relato com dados pessoais | exposição de CPF, senha, e-mail ou cartão | Privacy by Design antes de memória/rede | `TC-14` a `TC-16` |
| ataque ao agente | aumento artificial de prioridade ou comando destrutivo | guardrails e bloqueio sem criação de ticket | `TC-09` a `TC-13` |

## Teste comparativo de equidade

### Invariância de nome e gênero — TC-19

São enviados dois relatos idênticos sobre erro de NF-e no Financeiro, alterando
apenas o nome do solicitante. O critério de aceite exige a mesma prioridade, o
mesmo SLA e a mesma fila. A suíte registra decisão idêntica para os dois casos.

### Reincidência e aging — TC-20 e TC-21

Um chamado repetido de impressora no RH tem o SLA reduzido para evitar abandono
do usuário. Em seguida, a auditoria de aging promove chamados P3/P4 antigos. A
medida introduz um custo controlado de equidade: uma pequena perda de eficiência
da ordenação estritamente setorial para impedir inanição das áreas administrativas.

### Remediação humana — TC-22

Quando o usuário informa que uma classificação baixa ignora um prazo legal, o
botão **Contestar decisão da IA** altera o status para revisão humana e grava o
evento `HUMAN_REMEDIATION` na trilha de accountability.

## Privacy by Design e memória

| Memória | Uso | Risco | Mitigação |
|---|---|---|---|
| curto prazo | contexto de até 12 turnos | PII na conversa | sanitização antes de gravar e descarte ao fechar a aba |
| médio prazo | histórico e reincidência em `localStorage` | retenção em computador compartilhado | texto sanitizado e botão Limpar Memória |
| longo prazo | seis manuais RAG | procedimento desatualizado | referências identificadas `KB-XXX` e revisão dos manuais |

## Responsabilidade social

O agente foi analisado em três dimensões: **confiança**, pela explicação do SLA e
direito de contestação; **robustez**, pelos testes adversariais, fallback e PII;
e **impacto**, pela redução do tempo de triagem sem retirar a responsabilidade da
equipe humana. A licença social para operar depende de accountability,
transparência e remediação, não apenas de acurácia.

## Reflexão autoral

Considero justo que o setor influencie a prioridade somente quando essa informação
é combinada com a gravidade técnica, a urgência e o impacto concreto. Uma regra
baseada apenas no departamento trataria pessoas de áreas administrativas como
menos importantes e poderia ocultar situações críticas, como folha salarial,
admissão ou vazamento de credenciais. A versão 2.0 reduz esse risco ao testar
linguagem informal, neutralidade de gênero, reincidência, aging e contestação
humana. Ainda assim, os testes são cenários controlados e não provam ausência de
viés em todos os contextos. A responsabilidade final deve permanecer com a equipe
de suporte e com o gestor do processo, que precisam revisar regras, manuais e logs
periodicamente. Também não considero aceitável enviar senhas, CPF ou chaves de API
ao modelo; o filtro deve agir antes da memória e da rede. O botão de contestação é
fundamental porque transforma uma decisão automática em recomendação revisável.
Assim, a IA pode reduzir trabalho repetitivo sem eliminar a autonomia do usuário
nem a obrigação humana de reparar classificações injustas.

## Evidências verificadas

- [x] [documento de ética, vieses e governança](https://github.com/sztsu/helpdesk-ai/blob/main/docs/04_etica_vieses_e_governanca.md);
- [x] [matriz dos 24 testes](https://github.com/sztsu/helpdesk-ai/blob/main/docs/06_testes_manutencao_changelog.md);
- [x] [fila, aging e accountability](https://github.com/sztsu/helpdesk-ai/blob/main/docs/images/v2_queue_equity.png);
- [x] [painel com 24/24 casos aprovados](https://github.com/sztsu/helpdesk-ai/blob/main/docs/images/v2_tests_24.png);
- [x] implementação de `runEquityAgingAudit()` e `contestTicket()` em `assets/agent.js`.

## Participação e autoria

Os mecanismos e testes foram implementados por Gustavo Negreiros. João Pedro
Alves realizou a análise crítica, relacionou os mecanismos aos riscos sociais e
redigiu a reflexão desta atividade no contexto do projeto colaborativo.
