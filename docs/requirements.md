## Perfis de Usuário

O sistema contempla os seguintes perfis:

- Usuário autenticado da clínica  
- Profissional responsável por atendimento veterinário  
- Administrador ou atendente com acesso a cadastros e processos financeiros  

---

## Requisitos Funcionais

### 1.1 Autenticação
- O sistema deve permitir login com e-mail e senha  
- O sistema deve permitir exibir ou ocultar a senha digitada  
- O sistema deve disponibilizar recuperação de senha  
- O sistema deve permitir logout  

### 1.2 Página Inicial / Dashboard e Visualização Gerencial
- O sistema deve exibir os últimos atendimentos realizados  
- O sistema deve exibir a agenda do dia  
- O sistema deve apresentar um Dashboard Restrito de Administração com evolução de atendimentos por gráfico  
- O sistema deve apresentar navegação lateral com os módulos principais  

### 1.3 Gestão de Pacientes
- O sistema deve listar pacientes cadastrados  
- O sistema deve permitir pesquisar e filtrar cadastro do animal  
- O sistema deve permitir edições dos dados  

### 1.4 Cadastro de Paciente
O sistema deve permitir cadastrar:
- Foto, nome e data de nascimento 
- Idade, peso atual, microchip e restrições alérgicas  
- Espécie e Raça  

### 1.5 Cadastro do Tutor
O sistema deve vincular em conjunto ao paciente:
- Nome completo  
- CPF  
- Telefone e método do seguro convenio
- E-mail e Endereço  

### 1.6 Segurança de Edição
- O sistema deve alertar ao tentar sair com alterações não salvas   
- O sistema deve permitir salvar alterações  

### 1.7 Agenda
- O sistema deve exibir horários em formato de grade do dia atuante  
- O sistema deve permitir criar e interagir com horários ociosos   

### 1.8 Novo Agendamento
O sistema deve permitir gerenciar:
- Associação a Tutor / Paciente / Profissional Veterinário  
- Data e Hora  
- Categoria de procedimento (Vacinação, Observação, Exame ou Cirúrgico)  

### 1.9 Histórico Clínico Unificado
- O sistema deve consolidar o prontuário em visual de histórico contínuo
- O sistema deve abrigar as listas de Imunização/Vacinação (Com aviso de pendência)
- O sistema deve listar de modo cronológico a evolução de peso das vindas à clínica
- O sistema deve manter registro perpétuo de médico veterinário que operou consulta predecessora  

### 1.10 Prontuário Clínico (Veterinário)
- O sistema deve permitir o preenchimento diário de notas de avanço de prontuário  
- O sistema deve suportar campo semântico de respiração, diagnósticos pendentes, orientações de rotina

### 1.11 Emissão de Receituário
- O sistema deve compilar uma receita formato PDF extraindo os dados do Prontuário gerado
- O documento deve ser livre para manuseio, formatação A4 e encaminhamento Web
- A geração da receita exigirá assinatura ou carimbo validador  

### 1.12 Gerenciamento Anexo
- O sistema deve viabilizar alocamento e upload de imagem e arquivos PDF estáticos nos cadastros clínicos de cada paciente 

### 1.13 Relatório Facilitador via IA
- O software deve prover ferramenta baseada em motor Inteligência Artificial visível na guia de Histórico Global interpretando os dados do campo Veterinário traduzidos em relatório não complexo

### 1.14 Portal do Tutor Independente 
- A aplicação disponibilizará ambiente individual ao usuário atrelando a senha inicial de tutor para a vitrine Iougurt Care acompanhando imunizações tardias pendentes e histórico restrito

---

## Requisitos Não Funcionais

- Interface web responsiva e organizada  
- Feedback visual claro para ações  
- Consistência visual entre módulos  
- Proteção por autenticação e perfil RBAC  
- Persistência segura e backup regular  

---

## Histórico de Versões

| Versão | Data       | Descrição                                      | Autor               | Revisor            |
|--------|------------|------------------------------------------------|---------------------|--------------------|
| 1.0    | 26/03/2026 | Criação do documento e requisitos              | [Kaio Macedo Santana](https://github.com/bigkaio)  | [Maria Clara](https://github.com/alvezclari) | 
| 1.1    | 29/03/2026 | Refino unificador Histórico e Receitas Dashboard  | Equipe  |                    | 
