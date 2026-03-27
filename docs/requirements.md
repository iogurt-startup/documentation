
## Perfis de Usuário

O sistema contempla os seguintes perfis:

- Usuário autenticado da clínica  
- Profissional responsável por atendimento veterinário  
- Possível administrador ou atendente com acesso a cadastros e agenda  

---

## Requisitos Funcionais

### 1.1 Autenticação

- O sistema deve permitir login com e-mail e senha  
- O sistema deve permitir exibir ou ocultar a senha digitada  
- O sistema deve disponibilizar recuperação de senha  
- O sistema deve permitir logout  

### 1.2 Página Inicial / Dashboard

- O sistema deve exibir os últimos atendimentos realizados  
- O sistema deve exibir a agenda do dia  
- O sistema deve permitir acessar mais detalhes de cada seção  
- O sistema deve apresentar navegação lateral com os módulos principais  

### 1.3 Gestão de Pacientes

- O sistema deve listar pacientes cadastrados  
- O sistema deve permitir pesquisar pacientes  
- O sistema deve permitir filtrar pacientes  
- O sistema deve permitir cadastrar um novo paciente  
- O sistema deve permitir visualizar os dados de um paciente  
- O sistema deve permitir editar os dados de um paciente  
- O sistema deve permitir paginação da lista de pacientes  
- O sistema deve permitir acessar a ficha individual do paciente  

### 1.4 Cadastro de Paciente

O sistema deve permitir cadastrar:

- Foto do paciente  
- Nome do pet  
- Data de nascimento  
- Idade  
- Espécie  
- Raça  
- Peso atual  
- Sexo  
- Informação sobre microchip  
- Número do microchip  
- Observações clínicas gerais  

### 1.5 Cadastro do Tutor

O sistema deve permitir cadastrar junto ao paciente:

- Nome completo do tutor  
- CPF  
- Contato/telefone  
- E-mail  
- Convênio  
- Endereço  

### 1.6 Segurança de Edição

- O sistema deve alertar ao tentar sair com alterações não salvas  
- O sistema deve permitir cancelar a saída  
- O sistema deve permitir confirmar a saída sem salvar  
- O sistema deve permitir salvar alterações  

### 1.7 Agenda

- O sistema deve exibir agenda por dia  
- O sistema deve exibir horários em formato de grade  
- O sistema deve mostrar atendimentos por faixa de horário  
- O sistema deve permitir navegar entre datas  
- O sistema deve permitir criar um novo agendamento  

### 1.8 Agendamento

O sistema deve permitir registrar:

- Tutor  
- Paciente  
- Data  
- Horário  
- Veterinário responsável  
- Tipo de atendimento  
- Observação  

Tipos de atendimento:

- Consulta  
- Exame  
- Vacinação  
- Cirurgia  

### 1.9 Histórico

- O sistema deve listar o histórico de atendimentos  
- O sistema deve permitir pesquisar no histórico  
- O sistema deve permitir filtrar registros  
- O sistema deve exibir paciente, tutor, data, espécie e profissional  
- O sistema deve permitir visualizar detalhes  
- O sistema deve permitir paginação  

### 1.10 Prontuário / Atendimento

- O sistema deve permitir visualizar dados cadastrais do paciente  
- O sistema deve permitir visualizar o prontuário  
- O sistema deve permitir registrar atendimento clínico  

Campos do atendimento:

- Frequência respiratória  
- Observações  
- Pedidos de exame  
- Diagnóstico provisório/definitivo  
- Medicação/prescrição  

### 1.11 Resumo Clínico Lateral

- O sistema deve exibir resumo do histórico do paciente  
- O sistema deve apresentar espécie, idade, peso, vacinação e consultas  
- O sistema deve apoiar o profissional durante o atendimento  

### 1.12 Encerramento do Atendimento

- O sistema deve permitir finalizar atendimento  
- O sistema deve permitir imprimir dados do atendimento ou prontuário  

---

## Requisitos Não Funcionais

- Interface web responsiva e organizada  
- Navegação simples por menu lateral  
- Feedback visual claro para ações  
- Consistência visual entre módulos  
- Proteção por autenticação  
- Persistência segura dos dados  

---

