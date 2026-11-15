# AgendaFácil

Protótipo de um sistema de solicitação de agendamentos com confirmação automática por e-mail. O projeto demonstra o uso combinado de No Code, Low Code e IA generativa integrada por API.

## Objetivo

Permitir que uma pessoa solicite um atendimento informando nome, e-mail, data, horário, tipo de atendimento e observações. A solicitação é registrada em uma planilha, processada por uma automação e respondida com uma mensagem personalizada.

> O protótipo registra uma solicitação, mas não consulta disponibilidade em tempo real. Por isso, a mensagem informa que o horário ainda depende de validação.

## Tecnologias

- Google Forms: coleta dos dados;
- Google Sheets: armazenamento e acompanhamento;
- Make: automação visual do processo;
- Gemini API: geração da mensagem personalizada;
- Gmail: envio da confirmação de recebimento.

## Fluxo

```text
Google Forms
    ↓
Google Sheets — nova linha
    ↓
Make — Watch New Rows
    ↓
Gemini API — gera a mensagem
    ↓
Gmail — envia o e-mail
    ↓
Google Sheets — registra o resultado
```

## Formulário

[Abrir o formulário do AgendaFácil](https://docs.google.com/forms/d/e/1FAIpQLSeUrNakukU2iuzlajc-QqJs3A2VwQwbnmd4A7x9Wko2DKn7bA/viewform)

Antes da integração, deve-se garantir que exista apenas um campo de e-mail obrigatório ou que o cabeçalho correto esteja claramente identificado na planilha.

## Divisão das atividades

| Parte | Responsabilidade |
|---|---|
| 1 | Criar o formulário e organizar a planilha |
| 2 | Configurar o cenário e a automação no Make |
| 3 | Integrar a Gemini API e preparar o prompt |
| 4 | Documentar, testar e preparar a apresentação |

## Integração entre as partes 2 e 3

O módulo da Gemini API recebe os seguintes campos da planilha:

- `nome`
- `data`
- `horario`
- `tipo`
- `observacoes`

Ele retorna um único texto, chamado neste projeto de `mensagem_ia`. Esse texto deve ser mapeado para o corpo da mensagem no módulo `Gmail > Send an email`.

Consulte [docs/integracao-gemini-api.md](docs/integracao-gemini-api.md) para configurar e testar a integração antes de a automação completa ficar pronta.

## Testes mínimos

1. Solicitação com todos os campos preenchidos;
2. Solicitação sem observações;
3. Nome com acentos e mais de um sobrenome;
4. E-mail ausente ou inválido, que deve impedir o envio;
5. Duas novas linhas, verificando se cada uma produz apenas um e-mail.

## Segurança e privacidade

- Nunca salvar a chave da API neste repositório;
- Não exibir a chave em capturas de tela ou slides;
- Utilizar dados fictícios durante a apresentação;
- Não enviar o endereço de e-mail ao Gemini, pois ele é necessário apenas no módulo do Gmail;
- Revogar e substituir imediatamente qualquer chave exposta.

## Estado atual

- [x] Formulário inicial criado;
- [x] Arquitetura e contrato de dados definidos;
- [x] Prompt para a mensagem documentado;
- [ ] Cenário configurado no Make;
- [ ] Gemini API conectada e testada;
- [ ] Envio pelo Gmail testado;
- [ ] Evidências e apresentação concluídas.
