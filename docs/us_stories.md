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
* O sistema deve apresentar uma navegação lateral.

### US03: Dashboard Gerencial (Gráficos)
**Como** administrador da clínica,
**Quero** visualizar gráficos gerenciais na tela inicial do sistema
**Para que** eu possa acompanhar o volume de atendimentos e avaliar o desempenho geral do negócio.

**Critérios de Aceite:**
* O sistema deve exibir um gráfico simples mostrando a quantidade de atendimentos realizados nos últimos meses ou dias.
* O painel gerencial deve ser restrito ao perfil de Administrador, não poluindo a tela de outros usuários.

---

## Épico 3: Gestão de Pacientes e Tutores
**Objetivo:** Manter o controle dos pacientes cadastrados, garantindo que todo paciente esteja vinculado a um tutor.

### US04: Listagem e Busca de Pacientes
**Como** administrador ou atendente,
**Quero** listar, pesquisar e filtrar os pacientes
**Para que** eu possa encontrar rapidamente o cadastro de um animal.

**Critérios de Aceite:**
* O sistema deve permitir a paginação da lista de pacientes.
* O sistema deve permitir pesquisar e filtrar pacientes cadastrados.
* O sistema deve permitir acessar a ficha individual do paciente a partir da listagem.

### US05: Cadastro e Edição de Paciente e Tutor
**Como** administrador ou atendente,
**Quero** cadastrar ou editar os dados completos do paciente e do seu tutor
**Para que** a clínica possua as informações vitais e de contato corretas.

**Critérios de Aceite:**
* O sistema deve permitir cadastrar dados do paciente (foto, nome, idade, espécie, raça, microchip, etc.).
* O sistema deve exigir os dados do tutor junto ao paciente (nome, CPF, contato, endereço, convênio).
* O sistema deve alertar ao tentar sair da tela com alterações não salvas.
* O sistema deve permitir salvar as alterações feitas no cadastro.

---

## Épico 4: Agenda
**Objetivo:** Controlar o fluxo de consultas e procedimentos da clínica através de uma agenda diária.

### US06: Visualização da Agenda Diária
**Como** profissional responsável por atendimento,
**Quero** visualizar a agenda por dia
**Para que** eu saiba os horários de pico e as janelas livres.

**Critérios de Aceite:**
* O sistema deve exibir horários em formato de grade.
* O sistema deve mostrar os atendimentos organizados por faixa de horário.
* O sistema deve permitir navegar entre datas diferentes.

### US07: Criação de Novo Agendamento
**Como** administrador ou atendente,
**Quero** criar um novo agendamento
**Para que** o paciente tenha seu horário de atendimento garantido.

**Critérios de Aceite:**
* O sistema deve exigir tutor, paciente, data, horário e veterinário responsável.
* A seleção deve ser realizada através de listas suspensas (dropdowns).
* O sistema deve permitir selecionar o tipo (consulta, exame, vacinação, cirurgia).
* O sistema deve permitir registrar uma observação.

### US08: Cancelamento e Reagendamento
**Como** administrador ou atendente,
**Quero** cancelar ou alterar o horário de um agendamento
**Para que** a grade da clínica seja liberada.

**Critérios de Aceite:**
* O sistema deve permitir a alteração de data/hora (drag-and-drop ou form).
* O sistema deve exigir justificativa para cancelamentos.

---

## Épico 5: Prontuário e Atendimento Clínico
**Objetivo:** Registrar informações clínicas e manter o histórico consultável por paciente.

### US09: Registro de Atendimento Clínico
**Como** profissional responsável por atendimento veterinário,
**Quero** preencher as informações do atendimento clínico
**Para que** eu possa diagnosticar e prescrever tratamentos específicos.

**Critérios de Aceite:**
* O formulário deve disponibilizar notas clínicas, diagnóstico, pedidos de exames e medicamentos aplicados.
* O sistema deve permitir finalizar o atendimento.

### US10: Emissão de Receituário Clínico
**Como** profissional responsável por atendimento,
**Quero** preencher e gerar uma receita médica (prescrição) em formato PDF
**Para que** eu possa imprimir e entregar orientações ao tutor sem precisar redigí-las à mão.

**Critérios de Aceite:**
* O sistema deve oferecer o botão "Gerar Receita" com os recursos preenchidos do atendimento.
* O formato de documento gerado deve contemplar as medicações, dados do paciente, da clínica e do profissional.
* A solução deve permitir impressão direta e download.

### US11: Histórico Clínico Unificado
**Como** profissional responsável por atendimento,
**Quero** visualizar todo o histórico do paciente consolidado em uma estrutura de abas e listas
**Para que** eu possa acompanhar evolução de peso, imunizações e avaliações completas em um só lugar.

**Critérios de Aceite:**
* O sistema deve consolidar registros antigos em abas de "Atendimentos Anteriores", "Controle Imunológico (Vacinas)" e "Curva de Peso".
* A seção de vacinação deve evidenciar status Em Dia / Pendente.
* A evolução de peso deve detalhar cronologia das aferições por kg.
* A lista de Consultas passadas deve informar diagnósticos provisórios e os médicos predecessores.

### US12: Gerenciamento de Exames Anexados
**Como** profissional responsável por atendimento veterinário,
**Quero** anexar arquivos de resultados de exames (PDFs, imagens) ao prontuário do paciente
**Para que** eu possua o laudo completo e o histórico visual integrados.

**Critérios de Aceite:**
* O sistema deve permitir o upload de arquivos na área do Prontuário daquele paciente.
* A listagem dos exames anexados constará da data e do nome do arquivo (permitindo download).

### US13: Resumo de Atendimento por IA
**Como** atendente da clínica,
**Quero** visualizar um resumo simplificado do atendimento gerado por IA
**Para que** eu compreenda a instrução e libere o paciente com as orientações do médico abstraindo jargão técnico.

**Critérios de Aceite:**
* O sistema gerará texto com Inteligência Artificial interpretando prescrição finalizada e notas clínicas do veterinário.
* Este mini-relatório deve figurar no histórico macro visível pela recepção da administração.

---

## Épico 6: Portal do Tutor
**Objetivo:** Fornecer acesso próprio ao sistema para o tutor acompanhar a saúde do seu animal.

### US14: Dashboard do Tutor (Visão Geral do Pet)
**Como** tutor de um paciente,
**Quero** visualizar os dados cadastrais do meu pet e o histórico recente
**Para que** eu possa acompanhar o resumo da saúde de forma rápida.

**Critérios de Aceite:**
* O sistema deve direcionar o logista para Home específica do tutor.
* Exibições em formato Card devem enumerar os últimos eventos daquele pet.

### US15: Alertas e Recomendações (iougurt Care)
**Como** tutor de um paciente,
**Quero** visualizar lembretes importantes sobre a saúde do meu pet
**Para que** eu não perca datas de consultas e reforços de vacinas.

**Critérios de Aceite:**
* Painel de acompanhamento nomeado iougurt Care sinalizando proximidade de exames ou vacinas.
* Exibição de recomendações registradas previamente pelo médico.

### US16: Histórico Completo Visão Tutor
**Como** tutor de um paciente,
**Quero** acessar o histórico clínico
**Para que** eu possa consultar todos os procedimentos de maneira independente.

**Critérios de Aceite:**
* Restrição de acesso e visibilidade aos pets unicamente atrelados aquele tutor na arquitetura de Permissões.
* Permissão de leitura exclusiva sem funcionalidade de formatação de Prontuário.

---

## Histórico de Versões

| Versão | Data       | Descrição                                      | Autor               | Revisor            |
|--------|------------|------------------------------------------------|---------------------|--------------------|
| 1.0    | 27/03/2026 | Criação do documento                           | Equipe  | [Taynara Vitorino](https://github.com/taybalau) | 
| 1.1    | 29/03/2026 | Refino Inicial com Exames, Resumo IA e numeração sequencial | Equipe  |                    |
| 1.2    | 29/03/2026 | Unificação de Históricos e adição da US de Dashboard/Receita | Equipe  |                    |