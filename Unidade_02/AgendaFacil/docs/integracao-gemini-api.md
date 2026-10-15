# Integração com a Gemini API

Este guia permite testar a parte de IA sem depender da planilha ou do cenário definitivo no Make.

## 1. Criar a chave

1. Acessar o Google AI Studio;
2. Abrir **Chaves de API**;
3. Criar ou copiar uma chave associada ao projeto;
4. Guardar a chave em local privado.

A chave não deve ser adicionada ao GitHub. Na tela do AI Studio, o botão com dois retângulos copia a chave existente.

## 2. Criar o cenário provisório

No Make, criar o seguinte fluxo:

```text
Tools > Basic trigger
    ↓
Google Gemini AI > Generate a response
```

No `Basic trigger`, utilizar dados fictícios:

| Campo | Exemplo |
|---|---|
| nome | Ana Souza |
| data | 20/10/2026 |
| horario | 14:30 |
| tipo | Orientação |
| observacoes | Primeiro atendimento |

## 3. Configurar o módulo Gemini

1. Criar uma conexão usando a chave da API;
2. Escolher um modelo Flash disponível no projeto;
3. Definir uma saída curta, de aproximadamente 250 tokens;
4. Utilizar temperatura baixa, como `0.3`, quando essa configuração estiver disponível;
5. Inserir o conteúdo de [prompts/mensagem-confirmacao.txt](../prompts/mensagem-confirmacao.txt);
6. Mapear os campos do `Basic trigger` nas posições correspondentes do prompt;
7. Executar o cenário com **Run once** e conferir o texto retornado.

## 4. Conectar ao cenário definitivo

Quando a automação da planilha estiver pronta:

1. Substituir `Tools > Basic trigger` por `Google Sheets > Watch New Rows`;
2. Mapear nome, data, horário, tipo e observações da nova linha;
3. Adicionar `Gmail > Send an email` após o Gemini;
4. Usar o e-mail da planilha somente no campo de destinatário do Gmail;
5. Mapear o texto retornado pelo Gemini para o corpo do e-mail;
6. Opcionalmente, atualizar a linha com status, mensagem gerada e data de envio.

## Saída esperada

```text
Olá, Ana!

Recebemos sua solicitação de atendimento do tipo Orientação para o dia
20/10/2026, às 14:30. Seu pedido foi registrado com sucesso.

O horário solicitado ainda depende de validação. Caso seja necessário
algum ajuste, entraremos em contato pelo e-mail informado.

Atenciosamente,
Equipe AgendaFácil
```

## Evidências para a apresentação

- Captura do fluxo completo no Make, ocultando a chave;
- Entrada de teste do `Basic trigger`;
- Saída produzida pelo Gemini;
- E-mail recebido;
- Linha da planilha com o status final;
- Explicação de que o prompt impede a IA de inventar disponibilidade.
