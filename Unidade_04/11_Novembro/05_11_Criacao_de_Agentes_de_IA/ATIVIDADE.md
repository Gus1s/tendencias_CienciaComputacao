# 05/11 — Criação de agentes de IA

**Unidade:** IV — Agentes e Ética

**Valor:** 1,0 ponto

**Situação:** atividade atualizada com agente executável e evidências da versão 2.0.

## Objetivo

Analisar e documentar um agente de IA capaz de receber chamados de suporte,
proteger dados pessoais, manter contexto, aplicar regras de prioridade, consultar
uma base de conhecimento e executar ferramentas auditáveis. O estudo de caso é o
[HelpDesk AI 2.0](https://github.com/sztsu/helpdesk-ai), desenvolvido no projeto
colaborativo da NexusTech S.A.

## Evolução observada

Na versão 1.x, o fluxo era linear: Forms → Sheets → Make → Gemini → Gmail. A
versão 2.0 acrescentou uma interface conversacional e um agente autônomo no
navegador, mantendo a automação Low Code como integração paralela.

| Camada | Responsabilidade | Evidência no projeto |
|---|---|---|
| 1. Percepção | recebe a mensagem e mascara CPF, senha, cartão, API key e e-mail pessoal | `perceiveAndSanitize()` |
| 2. Memória | mantém diálogo de curto prazo, reincidência em médio prazo e manuais RAG em longo prazo | arrays da sessão, `localStorage` e `KNOWLEDGE_BASE` |
| 3. Planejamento | identifica intenção, aplica guardrails e regras de equidade | bloqueio de prompt injection, tom hostil e pedidos destrutivos |
| 4. Ação | chama ferramentas e registra o resultado | tools JSON e trilha de auditoria |

## Papel e limites do agente

O agente atua como **Agente de Triagem ITSM da NexusTech S.A.**. Ele pode:

1. solicitar esclarecimento quando o relato é vago;
2. classificar categoria, prioridade, SLA e fila;
3. recuperar um manual interno por RAG;
4. criar e consultar protocolos;
5. oferecer até três passos seguros;
6. acionar fallback local quando a API Gemini falha;
7. encaminhar contestação para revisão humana.

Ele não pode executar comandos administrativos, solicitar credenciais, apagar
dados corporativos, ocultar a justificativa da decisão nem substituir o analista
humano em incidentes críticos.

## Ferramentas estruturadas

| Tool | Finalidade |
|---|---|
| `sanitize_pii` | remover dados pessoais antes de memória ou rede |
| `search_knowledge_base` | recuperar manual interno relacionado ao incidente |
| `evaluate_business_sla` | calcular prioridade, SLA e fila |
| `create_ticket` | gerar protocolo e registrar o chamado |
| `query_ticket_status` | consultar um protocolo existente |
| `request_clarification` | pedir informações adicionais sem alucinar |
| `activate_fallback_contingency` | manter atendimento em erro HTTP 503/429 |

## Contrato resumido da decisão

```json
{
  "protocolo": "HD-2026-XXX",
  "categoria": "Software",
  "prioridade": "P1",
  "sla_estimado": "30 minutos",
  "fila_responsavel": "Nível 2 Sistemas",
  "referencia_rag": "KB-FIN-02",
  "orientacoes": ["passo 1", "passo 2", "passo 3"],
  "requer_humano": true,
  "justificativa": "impacto no fechamento fiscal"
}
```

## Testes relacionados

- `TC-01` a `TC-06`: classificação funcional e consulta de protocolo;
- `TC-09` a `TC-13`: ataques adversariais e comandos destrutivos;
- `TC-14` a `TC-16`: mascaramento de PII;
- `TC-17`: fallback em HTTP 503;
- `TC-18` e `TC-23`: esclarecimento e diálogo multi-turno;
- `TC-24`: rajada de 30 chamados em menos de 500 ms.

## Evidências verificadas

- [x] [código do agente e tools](https://github.com/sztsu/helpdesk-ai/blob/main/assets/agent.js);
- [x] [arquitetura de 4 camadas](https://github.com/sztsu/helpdesk-ai/blob/main/docs/03_arquitetura_agente_e_dados.md);
- [x] [aplicação executável](https://sztsu.github.io/helpdesk-ai/);
- [x] [matriz com 24 testes](https://github.com/sztsu/helpdesk-ai/blob/main/docs/06_testes_manutencao_changelog.md);
- [x] [captura do painel 24/24](https://github.com/sztsu/helpdesk-ai/blob/main/docs/images/v2_tests_24.png).

## Reflexão

A principal diferença entre um modelo generativo isolado e o agente analisado é
que o agente mantém estado, consulta conhecimento, escolhe ferramentas e altera
uma fila de atendimento. Essa autonomia aumenta o valor do sistema, mas também o
risco. Por isso, privacidade, guardrails, auditoria, fallback e revisão humana
fazem parte da arquitetura, e não apenas do texto do prompt.

## Participação e autoria

Gustavo Negreiros implementou o agente no repositório-fonte. João Pedro Alves
analisou a arquitetura, organizou as evidências e adaptou a atividade ao plano da
disciplina. A implementação não é apresentada como autoria individual de João.
