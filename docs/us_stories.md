# Histórias de Usuário


## Épico 1: Autenticação e Segurança
**Objetivo:** Garantir que o acesso às áreas internas seja protegido por autenticação.

### US01: Acesso ao Sistema (Login e Logout)
**Como** usuário autenticado da clínica,
**Quero** fazer login com meu e-mail e senha
**Para que** eu possa acessar minhas ferramentas de trabalho com segurança.

**Critérios de Aceite:**
* O sistema deve permitir login com e-mail e senha.
* O sistema deve permitir exibir ou ocultar a senha digitada.
* O sistema deve disponibilizar recuperação de senha.
* O sistema deve permitir realizar logout da conta.

---

## Épico 2: Dashboard e Navegação
**Objetivo:** Centralizar a visão diária da clínica e permitir navegação simples por menu lateral.

### US02: Painel Inicial (Home)
**Como** profissional responsável por atendimento veterinário,
**Quero** visualizar um resumo do meu dia no dashboard
**Para que** eu possa me organizar para os próximos atendimentos.

**Critérios de Aceite:**
* O sistema deve exibir os últimos atendimentos realizados.
* O sistema deve exibir a agenda do dia.
* O sistema deve permitir acessar mais detalhes de cada seção da home.
* O sistema deve apresentar uma navegação lateral com os módulos principais (Home, Pacientes, Agenda, Histórico).

---

## Épico 3: Gestão de Pacientes e Tutores
**Objetivo:** Manter o controle dos pacientes cadastrados, garantindo que todo paciente esteja vinculado a um tutor.

### US03: Listagem e Busca de Pacientes
**Como** administrador ou atendente,
**Quero** listar, pesquisar e filtrar os pacientes
**Para que** eu possa encontrar rapidamente o cadastro de um animal.

**Critérios de Aceite:**
* O sistema deve permitir a paginação da lista de pacientes.
* O sistema deve permitir pesquisar e filtrar pacientes cadastrados.
* O sistema deve permitir acessar a ficha individual do paciente a partir da listagem.

### US04: Cadastro e Edição de Paciente e Tutor
**Como** administrador ou atendente,
**Quero** cadastrar ou editar os dados completos do paciente e do seu tutor
**Para que** a clínica possua as informações vitais e de contato corretas.

**Critérios de Aceite:**
* O sistema deve permitir cadastrar os seguintes dados do paciente: foto, nome, data de nascimento, idade, espécie, raça, peso atual, sexo, informações/número de microchip e observações gerais.
* O sistema deve exigir e permitir cadastrar os dados do tutor junto ao paciente: nome completo, CPF, contato/telefone, e-mail, convênio e endereço.
* O sistema deve permitir salvar as alterações feitas no cadastro.
* O sistema deve alertar o usuário ao tentar sair da tela com alterações não salvas.
* O sistema deve permitir cancelar a saída ou confirmar a saída sem salvar após o alerta.

### US05: Histórico de Vacinação do Paciente
**Como** profissional responsável por atendimento,
**Quero** registrar e visualizar as vacinas aplicadas no animal
**Para que** o controle de imunização esteja sempre atualizado.

**Critérios de Aceite:**
* O sistema deve permitir o registro de: nome da vacina, data de aplicação, lote e data de reforço.
* O sistema deve exibir o status da vacina (Em dia / Pendente).

---

## Épico 4: Agenda
**Objetivo:** Controlar o fluxo de consultas e procedimentos da clínica através de uma agenda diária.

### US06: Visualização da Agenda Diária
**Como** profissional responsável por atendimento,
**Quero** visualizar a agenda por dia
**Para que** eu saiba os horários de pico e as janelas livres.

**Critérios de Aceite:**
* O sistema deve exibir horários de atendimento em formato de grade.
* O sistema deve mostrar os atendimentos agendados organizados por faixa de horário.
* O sistema deve permitir navegar entre datas diferentes.

### US07: Criação de Novo Agendamento
**Como** administrador ou atendente,
**Quero** criar um novo agendamento
**Para que** o paciente tenha seu horário de atendimento garantido.

**Critérios de Aceite:**
* O sistema deve exigir o vínculo do agendamento com: tutor, paciente, data, horário e veterinário responsável.
* A seleção do tutor, paciente, horário, veterinário e tipo de atendimento deve ser realizada através de listas suspensas (dropdowns).
* O sistema deve permitir selecionar o tipo de atendimento, incluindo: consulta, exame, vacinação ou cirurgia.
* O sistema deve permitir registrar uma observação no agendamento.

### US08: Cancelamento e Reagendamento
**Como** administrador ou atendente,
**Quero** cancelar ou alterar o horário de um agendamento
**Para que** a grade de horários da clínica seja liberada para outros pacientes.

**Critérios de Aceite:**
* O sistema deve permitir a alteração de data/hora via drag-and-drop ou formulário.
* O sistema deve exigir a justificativa para cancelamentos.

---

## Épico 5: Prontuário e Atendimento Clínico
**Objetivo:** Registrar informações clínicas e manter o histórico consultável por paciente.

### US09: Registro de Atendimento Clínico
**Como** profissional responsável por atendimento veterinário,
**Quero** preencher as informações do atendimento clínico
**Para que** eu possa diagnosticar e prescrever o tratamento adequado.

**Critérios de Aceite:**
* O atendimento deve estar vinculado obrigatoriamente a um paciente e a um profissional responsável.
* O formulário deve disponibilizar campos para: frequência respiratória, observações, pedidos de exame, diagnóstico provisório/definitivo e medicação/prescrição.
* O sistema deve exibir um resumo clínico lateral com o histórico do paciente durante o atendimento, contendo espécie, idade, peso, vacinação e consultas anteriores.
* O sistema deve permitir finalizar o atendimento.
* O sistema deve permitir imprimir os dados do atendimento ou do prontuário.

### US10: Consulta ao Histórico Global e Prontuário
**Como** profissional responsável por atendimento,
**Quero** visualizar os dados cadastrais e o prontuário do paciente
**Para que** eu possa avaliar a evolução clínica do animal.

**Critérios de Aceite:**
* A tela do paciente deve exibir abas separadas para: "Atendimento", "Dados" e "Prontuário".
* O módulo "Histórico" global deve listar o histórico de atendimentos e permitir paginação.
* O sistema deve exibir paciente, tutor, data, espécie e profissional responsável na lista de histórico.
* O sistema deve permitir pesquisar e filtrar registros do histórico.
* O sistema deve permitir abrir os detalhes de um registro específico a partir da listagem do histórico.

---

## Épico 6: Portal do Tutor
**Objetivo:** Fornecer acesso próprio ao sistema para o tutor acompanhar a saúde do seu animal.

### US11: Dashboard do Tutor (Visão Geral do Pet)
**Como** tutor de um paciente,
**Quero** visualizar os dados cadastrais do meu pet e o histórico recente
**Para que** eu possa acompanhar o resumo da saúde do meu animal de forma rápida.

**Critérios de Aceite:**
* O sistema deve direcionar o tutor para uma Home específica ao realizar o login.
* A tela inicial deve exibir um card "Meu Pet" com as informações cadastrais do animal (foto, nome, data de nascimento, espécie, etc.).
* A tela inicial deve exibir uma lista de "Últimos atendimentos" contendo apenas os registros dos animais vinculados a este tutor.

### US12: Alertas e Recomendações (iougurt Care)
**Como** tutor de um paciente,
**Quero** visualizar lembretes importantes sobre a saúde do meu pet
**Para que** eu não perca datas de consultas e reforços de vacinas.

**Critérios de Aceite:**
* O dashboard do tutor deve conter um painel de alertas denominado "iougurt Care".
* O painel deve exibir informações sobre a próxima consulta agendada (data, horário e profissional).
* O painel deve alertar sobre vacinas próximas do vencimento.
* O painel deve exibir recomendações de saúde cadastradas pelo veterinário.

### US13: Histórico Completo Visão Tutor
**Como** tutor de um paciente,
**Quero** acessar o histórico clínico
**Para que** eu possa consultar todos os procedimentos que meu pet já realizou na clínica.

**Critérios de Aceite:**
* O menu lateral para o tutor deve restringir o acesso apenas aos módulos permitidos (como Home e Histórico).
* O histórico visualizado pelo tutor deve exibir apenas os atendimentos referentes aos seus pets.
* O tutor deve ter permissão apenas de leitura sobre o histórico, sem poder editar ou excluir registros.

---

## Histórico de Versões

| Versão | Data       | Descrição                                      | Autor               | Revisor            |
|--------|------------|------------------------------------------------|---------------------|--------------------|
| 1.0    | 27/03/2026 | Criação do documento                           | Equipe  | [Taynara Vitorino](https://github.com/taybalau) | 