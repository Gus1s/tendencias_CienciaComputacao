# 19/11 — Viés algorítmico e responsabilidade social

**Unidade:** IV — Agentes e Ética

**Valor:** 1,0 ponto

**Situação:** análise orientada criada; exemplos e conclusões pessoais devem ser validados pelo aluno.

## Objetivo

Analisar impactos éticos do uso de IA na priorização de chamados do HelpDesk AI,
identificando riscos de viés, pessoas afetadas e medidas de governança.

## Partes interessadas

- colaboradores que abrem chamados;
- analistas de suporte e gestores de TI;
- setores com diferentes níveis de criticidade;
- clientes afetados por indisponibilidades;
- responsáveis por segurança, privacidade e conformidade.

## Riscos a analisar

| Risco | Possível impacto | Mitigação proposta |
|---|---|---|
| Setor usado como atalho para importância | chamados legítimos de áreas menos críticas podem esperar demais | combinar setor, impacto, urgência e tipo de incidente |
| Linguagem técnica favorecida | usuários com menor conhecimento podem receber prioridade inadequada | formulário guiado e exemplos em linguagem simples |
| Relatos curtos ou ambíguos | classificação incorreta ou orientação genérica | solicitar complemento e encaminhar para humano |
| Alucinação do modelo | diagnóstico ou passo inseguro | lista de ações proibidas e validação humana |
| Dados pessoais no relato | exposição a provedores externos | minimização, anonimização e controle de acesso |
| Falta de explicabilidade | usuário não entende prioridade ou fila | registrar justificativa curta e permitir contestação |
| Automação excessiva | perda de autonomia e responsabilidade | humano responsável pela decisão de alto impacto |

## Questões para reflexão

1. É justo que o setor influencie a prioridade? Em quais condições?
2. Como evitar que um usuário com pouca habilidade de escrita seja prejudicado?
3. Quem responde por uma orientação incorreta produzida pela IA?
4. Quais dados não deveriam ser enviados ao modelo?
5. Como o usuário pode contestar uma classificação automática?

## Atividade prática

1. Criar dois chamados equivalentes para setores diferentes.
2. Comparar categoria, prioridade, SLA e justificativa.
3. Criar um relato ambíguo e observar se o sistema pede mais dados.
4. Identificar um resultado potencialmente injusto.
5. Propor uma alteração de regra, prompt ou fluxo para reduzir o risco.

## Evidências a preencher

- [ ] entradas anonimizadas dos testes;
- [ ] resultados comparados;
- [ ] viés ou risco identificado;
- [ ] proposta de mitigação;
- [ ] reflexão autoral de 150 a 300 palavras.

## Critério de aceite — 1,0 ponto

| Critério | Pontos |
|---|---:|
| Identificação de partes interessadas e riscos | 0,20 |
| Teste comparativo verificável | 0,25 |
| Discussão de privacidade e responsabilidade | 0,20 |
| Mitigação tecnicamente aplicável | 0,20 |
| Reflexão crítica autoral | 0,15 |
