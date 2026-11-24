# 05/11 — Criação de agentes de IA

**Unidade:** IV — Agentes e Ética

**Valor:** 1,0 ponto

**Situação:** especificação documentada; evidências de execução devem ser anexadas pelo aluno.

## Objetivo

Projetar um agente de IA capaz de receber um chamado de suporte, interpretar o
contexto do setor solicitante, aplicar regras de prioridade e encaminhar uma
resposta estruturada. O agente usa como estudo de caso o
[HelpDesk AI](../../../Unidade_03/10_Outubro/29_10_Limitacoes_e_Mini_Projeto/HelpDeskAI/).

## Papel do agente

O agente atua como **Agente de Triagem de Service Desk da NexusTech S.A.** Ele
não executa comandos na máquina do usuário nem encerra chamados. Sua função é:

1. validar se o relato contém informações mínimas;
2. identificar a categoria técnica;
3. calcular prioridade e SLA conforme o setor;
4. selecionar a fila responsável;
5. gerar até três orientações seguras de autoatendimento;
6. pedir intervenção humana quando houver risco ou informação insuficiente.

## Entradas e saída esperada

Entradas: nome, e-mail, setor, título e descrição do incidente.

Saída obrigatória em JSON:

```json
{
  "categoria": "Hardware | Software | Rede/Infraestrutura | Acesso/Segurança",
  "prioridade": "P1 | P2 | P3 | P4",
  "sla_estimado": "texto curto",
  "fila_responsavel": "Nível 1 | Nível 2 Infraestrutura | Nível 2 Sistemas",
  "orientacoes": ["passo 1", "passo 2", "passo 3"],
  "requer_humano": true,
  "justificativa": "explicação objetiva"
}
```

## Regras e limites éticos

- não solicitar senhas, tokens, documentos pessoais ou segredos empresariais;
- não sugerir desativação de antivírus, firewall ou controles de acesso;
- não inventar diagnóstico quando o relato for insuficiente;
- chamados de segurança, indisponibilidade crítica ou risco financeiro devem
  ser encaminhados a um humano;
- a prioridade deve considerar impacto e urgência, não o cargo do solicitante;
- toda decisão automatizada deve permanecer registrada para auditoria.

## Roteiro da atividade

1. Executar pelo menos três casos: crítico, comum e ambíguo.
2. Comparar as saídas com as regras de negócio do HelpDesk AI.
3. Registrar uma decisão correta e uma limitação encontrada.
4. Anexar as evidências abaixo sem inserir dados pessoais reais.

## Evidências a preencher

- [ ] prompt ou instrução de sistema utilizada;
- [ ] três entradas de teste anonimizadas;
- [ ] saídas JSON obtidas;
- [ ] captura ou log da execução;
- [ ] reflexão breve sobre limites e supervisão humana.

## Critério de aceite — 1,0 ponto

| Critério | Pontos |
|---|---:|
| Papel, objetivo e limites do agente | 0,20 |
| Entradas e saída estruturada | 0,20 |
| Aplicação das regras de prioridade | 0,20 |
| Testes e evidências verificáveis | 0,20 |
| Análise ética e supervisão humana | 0,20 |
