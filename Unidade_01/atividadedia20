Alunos: Maria Cecília Araujo, Gustavo Negreiros, João Pedro Alves, Gabriella Oliveira de Souza Dias

**Etapa 1 — Defina o Problema **

Durante o desenvolvimento de um sistema, os requisitos escritos por um cliente podem ser vagos, incompletos ou ambíguos. Isso pode gerar retrabalho. Objetivo ser3ia implementar a IA generativa pode ajudar a, analisar a descrição inicial identificar requisitos funcionais e não funcionais; encontrar ambiguidades ou informações que faltam; sugerir regras de negócio; criar critérios de acessibilidade; gerar possíveis casos de teste; levantar perguntas que devem ser feitas ao cliente antes da implementação.
**- Etapa 2 - Prompt inicial **

Atue como um analista de requisitos de software .

Analise o requisito apresentado abaixo e identifique possíveis problemas, ambiguidades ou informações que estejam faltando.

Sua análise deve:

Requisitos específicos identificados.
Requisitos não funcionais , caso existam ou possam ser sugeridos.
Regras de negócio envolvido.
Ambiguidades ou pontos que precisam ser esclarecidos .
Perguntas que devem ser feitas ao cliente ou usuário antes do desenvolvimento.
Critérios de acessibilidade para validar se a funcionalidade foi rompida corretamente.
Possíveis casos de teste para verificar o funcionamento da funcionalidade.
Ao final, apresenta também uma melhorada e mais completa do requisito original , mantendo a intenção inicial do usuário.

Requisito a ser analisado
- Etapa 3 - Resposta do prompt

Requisitos específicos identificados
A partir do requisito original:

“O sistema deve permitir cadastrar pacientes e controlar os medicamentos utilizados por eles.”

Podemos identificar inicialmente os seguintes requisitos funcionais:

RF01 — Cadastrar pacientes O sistema deve permitir o cadastro de pacientes.

RF02 — Consultar pacientes O sistema deve permitir visualizar os pacientes cadastrados.

RF03 — Editar pacientes O sistema deve permitir alterar os dados de um paciente cadastrado.

RF04 — Associar medicamentos a pacientes O sistema deve permitir registrar quais medicamentos são usados ​​por determinado paciente.

RF05 — Consultar medicamentos do paciente O sistema deve permitir visualizar os medicamentos associados a cada paciente.

Outras funcionalidades podem ser solicitadas, dependendo do que o cliente entende por “controlar medicamentos”, como:

dose registradora; frequência de registradores; informar horários; dados do registrador de início e fim do tratamento; suspensor de medicamentos; registradoradministração do medicamento; manter o histórico de medicamentos utilizados. 2. Requisitos não funcionais

O requisito original não apresenta requisitos não funcionalmente explícitos. Entretanto, alguns podem ser sugeridos.

RNF01 — Segurança O sistema deve permitir acesso aos dados dos pacientes apenas para usuários autorizados.

RNF02 — Privacidade Os dados pessoais e de saúde dos pacientes devem ser protegidos de acordo com a LGPD.

RNF03 — Desempenho As operações de cadastro e consulta deverão apresentar resposta em tempo adequado, por exemplo, em até 3 segundos em condições normais de uso.

RNF04 — Integridade dos dados O sistema deve evitar inconsistências, como associar medicamentos a pacientes inexistentes.

RNF05 — Usabilidade Os formulários devem apresentar mensagens claras quando dados obrigatórios não forem informados ou forem inválidos.

Regras de negócio
Algumas possíveis regras de negócio seriam:

RN01. Todo paciente deve possuir um identificador exclusivo no sistema.

RN02. Os dados determinados do paciente devem ser obrigatórios, como nome e dados de nascimento, conforme definição do cliente.

RN03. Um paciente pode usar nenhum, um ou vários medicamentos.

RN04. Um medicamento pode ser utilizado por vários pacientes.

RN05. Um medicamento não deve ser associado a um paciente sem que ambos estejam previamente cadastrados.

RN06. Caso exista controle de tratamento, cada medicamento associado ao paciente deverá possuir informações como dose, frequência e período de utilização.

RN07. Medicamentos suspensos ou encerrados devem permanecer no histórico do paciente, caso seja necessário manter a rastreabilidade.

Ambiguidades e pontos que precisam ser esclarecidos
O principal problema do requisito é a falta de detalhes.

“Cadastro de pacientes”

Não está definido quais informações devem fazer parte do cadastro.

Por:

nome; CPF; dados de nascimento; telefone; endereço; sexo; responsável; alergias; condições clínicas.

Também não sabemos quais campos são obrigatórios.

“Controlar os medicamentos”

Esse é o trecho mais ambíguo.

“Controlar” pode significar apenas:

Registrador de quais medicamentos o paciente utiliza.

Mas também pode significar:

Registrador de medicamento, dose, horários, frequência, duração do tratamento e administração.

Ou até mesmo incluir:

estoque de medicamentos; histórico; medicamentos atrasados; responsável pela administração; observações; prescrições médicas.

Portanto, essa expressão precisa ser detalhada antes da implementação.

Perguntas que deveriam ser feitas ao cliente
Antes do desenvolvimento, algumas perguntas importantes seriam:

Quais informações devem ser armazenadas no cadastro do paciente? Quais campos são obrigatórios? O CPF do paciente será obrigatório e único? O sistema deve permitir editar e excluir pacientes? O que exatamente significa “controlar os medicamentos”? O sistema precisa apenas registrar quais medicamentos o paciente utiliza ou também controlar doses e horários? Devem ser registrados os dados de início e os dados de término do medicamento? Existe diferença entre medicamento ativo, suspenso e finalizado? O sistema precisa manter o histórico dos medicamentos usados ​​anteriormente? É necessário registrar cada administração de medicamento? Quem poderá cadastrar ou alterar medicamentos? O sistema precisa informar medicamentos atrasados ​​ou próximos do horário? Deve existir cadastro próprio de medicamentos? Um paciente pode usar vários medicamentos simultaneamente? É necessário registrar quem prescreveu o medicamento? É necessário registrar alergias ou contraindicações? Quem terá acesso às informações dos pacientes? Existe necessidade de relatórios ou filtros? 6. Critérios de acesso CA01 — Cadastro de paciente

Dado que o usuário está autorizado a cadastrar pacientes, ao preencher corretamente os campos obrigatórios e confirmar o cadastro, então o paciente deverá ser registrado no sistema.

CA02 — Campos obrigatórios

Dado que o usuário está cadastrando um paciente, ao tentar salvar sem preencher um campo obrigatório, então o sistema deverá impedir o cadastro e informar quais dados precisam ser preenchidos.

CA03 — Associação de Medicamentos

Dado que existe um paciente cadastrado, quando o usuário associa um medicamento a esse paciente, então o medicamento deverá aparecer na lista de medicamentos utilizados pelo paciente.

CA04 — Vários medicamentos

Dado que um paciente já utiliza um medicamento, quando outro medicamento for associado, então ambos deverão permanecer vinculados ao paciente.

CA05 — Consulta

Dado que existem medicamentos associados ao paciente, quando o usuário acessa os detalhes desse paciente, então deverá conseguir visualizar seus medicamentos.

CA06 — Histórico

Caso seja definido que o sistema mantém histórico:

Dado que um medicamento é suspenso, quando o usuário consulta o histórico do paciente, então o medicamento deve continuar disponível como tratamento anterior, mas não como medicamento ativo.

Possíveis casos de teste Caso Cenário Resultado esperado CT01 Cadastrar paciente com dados válidos Paciente cadastrado com sucesso CT02 Cadastrar paciente sem nome obrigatório Sistema impedir cadastro e informações de erro CT03 Cadastrar paciente com CPF duplicado Sistema descartado cadastro, caso CPF seja único CT04 Editar dados de paciente Dados atualizados corretamente CT05 Associar medicamento a paciente Medicamento fica vinculado ao paciente CT06 Associar vários medicamentos Todos aparecem no cadastro do paciente CT07 Consultar medicamentos de um paciente Sistema apresenta corretamente os medicamentos CT08 Associar medicamento a paciente inexistente Operação deve ser rejeitada CT09 Suspender medicamento Medicamento deixa a lista de ativos CT10 Consultar histórico Medicamentos anteriormente usados ​​são apresentados CT11 Informar dose inválida Sistema deve rejeitar o valor CT12 Usuário sem permissão tenta alterar informações Sistema deve negar a operação
Versão melhorada do requisito
Uma versão mais completa poderia ser:

O sistema deverá permitir o cadastro e gerenciamento de pacientes, armazenando informações como nome, dados de nascimento, documento, telefone e demais dados definidos como obrigatórios. Cada paciente deverá possuir um identificador exclusivo no sistema.

O sistema deverá permitir associar um ou mais medicamentos a cada paciente, registrando, quando aplicável, nome do medicamento, dosagem, frequência de utilização, horários, dados de início, dados de termo e observações.

O usuário autorizado deverá poder consultar os medicamentos atualmente utilizados pelo paciente, bem como suspender ou finalizar um tratamento sem desligar seu histórico.

O sistema deverá manter a integridade das informações, impedindo a associação de medicamentos a pacientes inexistentes e restringindo o acesso e alteração dos dados para usuários autorizados. As informações pessoais e de saúde armazenadas deverão ser protegidas de acordo com os requisitos de segurança e privacidade aplicáveis, incluindo a LGPD.

Principal

O requisito original apresenta a intenção da funcionalidade, mas ainda não é suficientemente detalhado para iniciar o desenvolvimento com segurança. A maior lacuna está na expressão “controlar os medicamentos”, porque ela pode representar desde uma associação simples paciente–medicamento até um módulo completo de administração, horários, doses e histórico.

O sistema deve permitir cadastrar pacientes e controlar os medicamentos utilizados por eles.

Organize uma resposta de forma clara, objetiva e separada por tópicos.

**etapa - 4 - promt orgânico **

Atue como Analista de Requisitos de Software Sênior , com experiência em levantamento de requisitos, modelagem de regras de negócio, critérios de acessibilidade e testes de software.

Sua tarefa é analisar criticamente o requisito abaixo, considerando que ele será utilizado como base para o desenvolvimento de um sistema real.

Requisito inicial
O sistema deve permitir cadastrar pacientes e controlar os medicamentos utilizados por eles.

Objetivo da análise
Identifique tudo o que é claro, incompleto, ambíguo ou ausente no requisito e proponha uma especificação mais específica, sem inventar regras de negócio como se fossem fatos. Sempre que alguma informação não estiver definida, sinalize como “A confirmar com o cliente” .

Organize uma resposta nas seguintes declarações:

Interpretação do requisito

Explique brevemente o que você entende que o sistema deve fazer.
Requisitos

Liste as funcionalidades possíveis.
Números como RF01, RF02, RF03 etc.
Diferenças de funcionalidades explicitamente informadas apenas sugeridas pela análise.
Requisitos não

Sugira requisitos relacionados a segurança, desempenho, usabilidade, disponibilidade, privacidade e proteção de dados.
Quando aplicável, considerar boas práticas relacionadas à LGPD.
Regras de negócio

Identificar possíveis regras relacionadas ao cadastro de pacientes e ao controle de medicamentos.
Não assuma como definitiva nenhuma regra que não esteja presente no requisito original.
Dados necessários

Sugira quais informações provavelmente precisarão ser armazenadas para:

pacientes;
medicamentos;
vínculo entre paciente e medicamento.
Informe quais campos precisam ser confirmados com o cliente.

Ambigüidades e lacunas

Aponte termos vagos ou informações ausentes.
Explique que cada ponto pode gerar problemas durante o desenvolvimento.
Perguntas para o cliente

Crie perguntas objetivas que devem ser respondidas antes da implementação.
Priorize perguntas que possam alterar banco de dados, regras de negócio, telas ou comportamento do sistema.
Critérios de proteção

Escreva critérios verificáveis.
Sempre que possível, utilize o formato: Dado que / Quando / Então .
Casos de teste

Crie casos positivos, negativos e de validação.

Para cada caso de teste, informe:

cenário;
dados de entrada;
resultado esperado.
Riscos de

Identifique problemas que poderiam ocorrer caso o desenvolvimento comece somente com o requisito original.
Requisito refinado

Reescreva o requisito original de maneira mais completa, clara e testável.
Separadamente o que já pode ser definido do que ainda depende de validação com o cliente.
: para sua resposta
Não invente informações sobre o negócio.
Diferença claramente fato , sugestão e informação a confirmar .
Evite termos genéricos como “adequado”, “rápido”, “fácil” ou “seguro” sem explicar como poderiam ser medidos.
Priorize requisitos que possam ser implementados e testados.
Caso encontre dependências entre requisitos, indique-as.
Ao final, apresenta uma seção chamada “Principais decisões que o cliente precisa tomar” , contendo no máximo 10 decisões prioritárias.
Utilizar linguagem técnica, mas clara e objetiva. **

etapa 5 - comparação** A principal diferença é que o prompt inicial pede uma análise mais geral e direta, enquanto o prompt orgânico define melhor o papel da IA, a estrutura da resposta, os limites do que podem ser reforçados e a forma como os resultados devem ser apresentados.
- etapa 6 - Teste de Robustez " Explique o sistema para um aluno" Claro. Pensando como se eu estivesse explicando para um aluno que está começando no desenvolvimento de sistemas:

Esse sistema seria um sistema de cadastro e acompanhamento de pacientes e medicamentos.

A ideia principal é permitir que uma instituição, clínica ou profissional de saúde consiga registrar os pacientes e controlar quais medicamentos cada um utilizado.

Por exemplo, imagine o paciente João da Silva. No sistema, poderiam ser cadastradas informações como nome, data de nascimento, telefone e outros dados necessários. Depois disso, seria possível associar ao João os medicamentos que ele utiliza.

Um corpo seria:

Paciente: João da Silva Medicamento: Losartana Dosagem: 50 mg Frequência: 1 vez ao dia Horário: 08:00

Assim, o sistema não serve apenas para salvar o nome do medicamento. Ele pode ajudar a organizar quem usa determinado medicamento, quanto deve tomar, quando deve tomar e por quanto tempo.

Como o sistema poderia funcionar

Primeiro, o usuário cadastraria o paciente.

Depois, cadastraria os medicamentos disponíveis no sistema.

Em seguida, faria a associação entre o paciente e o medicamento.

Por:

Paciente

Maria

Medicamentos cadastrados

Dipirona Losartana Omeprazol

O sistema poderia registrar que Maria utiliza:

Losartana — 50 mg — todos os dias às 8h.

Esse relacionamento é importante porque um paciente pode utilizar vários medicamentos e, ao mesmo tempo, um mesmo medicamento pode ser utilizado por vários pacientes.

No banco de dados, de forma simplificada, pensamos em três partes:

PACIENTE

eu ia
nome
data_nascimento
MEDICAMENTO

eu ia
nome
PACIENTE_MEDICAMENTO

paciente_id
medicamento_id
dosagem
horário
frequência
A tabela PACIENTE_MEDICAMENTO é responsável por dizer qual medicamento pertence a qual paciente e como ele deve ser utilizado.

＀＀

Imagine que existam dois pacientes:

João Maria

E dois medicamentos:

Losartana Omeprazol

As relações poderiam ser:

João → Losartana João → Omeprazol

Maria → Losartana

Isso significa que o mesmo medicamento, Losartana, pode aparecer para pacientes diferentes.

O problema do requisito original

O requisito inicial dizia apenas:

"O sistema deve permitir cadastrar pacientes e controlar os medicamentos utilizados por eles."

Para uma pessoa, essa frase parece simples. Para um desenvolvedor, porém, ela gerou várias dúvidas.

Por:

O que significa "controlar medicamentos"?

Pode significar apenas listar os medicamentos que o paciente usa.

Mas também pode significar:

dosagem registradora; horários de registradores; controleadministração; informar se o medicamento foi tomado; registrador de medicamentos atrasado; manter histórico; emitir alertas.

É justamente aí que entra a análise de requisitos.

Antes de começar a programar, precisamos entender exatamente o que o cliente quer.

Onde entra a IA generativa nesse trabalho?

A IA pode receber aquele requisito simples e ajudar o analista a encontrar essas dúvidas.

Por exemplo, ao receber:

"O sistema deve permitir cadastrar pacientes e controlar os medicamentos utilizados por eles."

A IA pode perguntar:

Quais informações devem ser armazenadas sobre o paciente?

É necessário registrar dose e horário dos medicamentos?

Um medicamento pode ser suspenso?

Deve existir um histórico de medicamentos usados?

Quem poderá cadastrar ou alterar medicamentos?

Ou seja, um IA funciona como uma espécie de assistente do analista de requisitos.

Ela não decide sozinha como o sistema deve funcionar. Ela ajuda a perceber o que ainda precisa ser questionado ao cliente antes de começar o desenvolvimento.

Essa é justamente a ideia central do exercício: mostrar que um prompt simples produz uma análise mais genérica, enquanto um prompt orgânico orienta melhor a IA e gera uma análise muito mais completa e útil para desenvolver o sistema.
