# 26/11 — Projeto de solução inteligente

**Unidade:** IV — Projeto Final

**Valor total:** 2,0 pontos

**Projeto:** [HelpDesk AI 2.0](https://github.com/sztsu/helpdesk-ai)

**Aplicação:** <https://sztsu.github.io/helpdesk-ai/>

## Identificação da evolução

| Versão | Resultado |
|---|---|
| v1.x | Forms + Sheets + Make + Gemini + Gmail para triagem assíncrona |
| v2.0 | chatbot web + agente autônomo de 4 camadas + RAG + PII + equidade + 24 testes |

O snapshot v1.x permanece na
[Unidade 3](../../../Unidade_03/10_Outubro/29_10_Limitacoes_e_Mini_Projeto/HelpDeskAI/).
A implementação v2.0 e suas evidências são referenciadas no repositório-fonte do
parceiro para preservar histórico e autoria.

## Entrega 1 — Apresentação da solução inteligente (1,0 ponto)

### Roteiro sugerido — 8 a 10 minutos

1. **Problema:** fila única, urgência subjetiva, sobrecarga N1 e riscos de IA.
2. **Evolução:** da automação linear v1.x para o agente autônomo v2.0.
3. **Demonstração:** abrir o [GitHub Pages](https://sztsu.github.io/helpdesk-ai/).
4. **Quatro camadas:** Percepção, Memória, Planejamento e Ação/Tools.
5. **Caso Financeiro + PII:** comprovar mascaramento, RAG, P1 e protocolo.
6. **Caso adversarial:** mostrar bloqueio de prompt injection ou comando destrutivo.
7. **Equidade:** executar aging e demonstrar contestação humana.
8. **Testes:** executar a suíte completa e apresentar 24/24 resultados.
9. **Limitações:** persistência local, demo sem backend corporativo e dependência
   opcional da API Gemini.
10. **Participação:** explicar autoria, integração e documentação de cada integrante.

### Evidências da apresentação

- [x] [aplicação executável](https://sztsu.github.io/helpdesk-ai/);
- [x] [documentação central](https://github.com/sztsu/helpdesk-ai#índice-completo-da-documentação-padrão-tcc--conteúdo-a1);
- [x] [chatbot e quatro camadas](https://github.com/sztsu/helpdesk-ai/blob/main/docs/images/v2_chatbot_4layers.png);
- [x] [fila, equidade e remediação](https://github.com/sztsu/helpdesk-ai/blob/main/docs/images/v2_queue_equity.png);
- [x] [suíte 24/24](https://github.com/sztsu/helpdesk-ai/blob/main/docs/images/v2_tests_24.png);
- [x] [slides em PDF](https://github.com/sztsu/helpdesk-ai/blob/main/slides/Apresentacao_HelpDesk_AI.pdf);
- [x] [documentação acadêmica adaptada](DOCUMENTACAO_SISTEMA.md).

### Critérios — 1,0 ponto

| Critério | Evidência | Pontos |
|---|---|---:|
| Clareza do problema e da solução | comparação v1.x × v2.0 | 0,20 |
| Demonstração do fluxo e uso de IA | interface, 4 camadas, RAG e tools | 0,25 |
| Evidências e testes | 24 casos e três capturas v2.0 | 0,20 |
| Análise crítica e ética | PII, viés, aging e remediação | 0,20 |
| Organização e participação da dupla | autoria e fontes registradas | 0,15 |

## Entrega 2 — Integração e participação no GitHub (1,0 ponto)

### Evidências no repositório da disciplina

- [x] organização por unidade, mês, data e tema;
- [x] atividade específica de agente de IA;
- [x] atividade de chatbot com comparação de cinco alternativas;
- [x] atividade de viés com reflexão autoral e testes associados;
- [x] documentação do projeto final;
- [x] snapshot histórico do projeto colaborativo na Unidade 3;
- [x] origem e autoria preservadas em `ORIGEM.md` e nesta Unidade 4;
- [x] links para o código, aplicação e commit de referência v2.0;
- [x] histórico Git com commits descritivos do trabalho colaborativo.

### Contribuição declarada

| Integrante | Contribuição documentada |
|---|---|
| Gustavo Negreiros | concepção e implementação do HelpDesk AI, esteira v1.x, aplicação v2.0, agente, interface, testes e documentação técnica no repositório-fonte |
| João Pedro Alves | integração do projeto no repositório da disciplina, análise dos artefatos, organização da Unidade 4, documentação acadêmica, reflexão ética e preparação do roteiro de apresentação |

### Critérios — 1,0 ponto

| Critério | Evidência | Pontos |
|---|---|---:|
| Organização do repositório | estrutura Unidade → mês → atividade | 0,20 |
| Integração dos conteúdos | No/Low/Vibecode, agente, ética e testes | 0,25 |
| Documentação e reprodutibilidade | execução em 10 segundos e links diretos | 0,25 |
| Histórico, autoria e colaboração | origem e contribuições explícitas | 0,15 |
| Participação e evolução | v1.x → v2.0 documentada | 0,15 |

## Checklist antes da apresentação

- [ ] abrir o GitHub Pages e confirmar carregamento;
- [ ] executar a suíte de 24 testes na frente do avaliador;
- [ ] demonstrar um caso com PII sem usar dados reais;
- [ ] demonstrar uma contestação humana;
- [ ] conferir se os slides refletem a versão 2.0;
- [ ] combinar a divisão da fala entre os integrantes;
- [ ] não afirmar produção corporativa: trata-se de protótipo acadêmico.

## Observação

A avaliação A1/reflexão da mesma data permanece separada em
[`Avaliacoes/11_Novembro/26_11_Avaliacao_A1`](../../../Avaliacoes/11_Novembro/26_11_Avaliacao_A1/).
