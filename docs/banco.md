# Modelo Físico do Banco de Dados

## Introdução

O banco de dados do sistema IOUGURT foi desenvolvido utilizando o SGBD PostgreSQL e modelado por meio do ORM Prisma. O sistema é voltado para a gestão de clínicas veterinárias, permitindo o gerenciamento de usuários, tutores, pacientes, consultas, prontuários clínicos, vacinação e exames.

O modelo segue uma arquitetura multi-tenant, onde cada clínica possui seus próprios usuários, tutores e pacientes.

Este documento apresenta o modelo físico do banco de dados utilizado pela plataforma **IOUGURT**, implementado em **PostgreSQL**.

## Metodologia

A construção do modelo físico foi realizada a partir da análise do script SQL gerado pelo Prisma (`prisma/physical_model.sql`), contemplando:

- Identificação das tabelas, suas colunas e tipos de dados;
- Mapeamento das restrições de integridade (`PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `NOT NULL`);
- Definição dos relacionamentos entre as entidades;
- Documentação dos tipos enumerados criados no banco.


## Visão Geral

O banco de dados é composto por entidades relacionadas à gestão de clínicas veterinárias, usuários, tutores, pacientes, agendamentos, prontuários clínicos, vacinação e exames.

# Estrutura das Tabelas

## clinics

Tabela responsável pelo cadastro das clínicas veterinárias.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| name | TEXT | NOT NULL |
| cnpj | TEXT | |
| address | TEXT | |
| phone | TEXT | |
| created_at | TIMESTAMP | NOT NULL |
| updated_at | TIMESTAMP | NOT NULL |

---

## users

Tabela responsável pelos usuários do sistema.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| email | TEXT | NOT NULL, UNIQUE |
| password_hash | TEXT | NOT NULL |
| name | TEXT | NOT NULL |
| avatar_url | TEXT | |
| crmv | TEXT | |
| role | Role | NOT NULL |
| clinic_id | TEXT | FK → clinics(id) |
| created_at | TIMESTAMP | NOT NULL |
| updated_at | TIMESTAMP | NOT NULL |

---

## refresh_tokens

Armazena tokens de renovação de autenticação.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| token | TEXT | NOT NULL, UNIQUE |
| user_id | TEXT | FK → users(id) |
| expires_at | TIMESTAMP | NOT NULL |
| created_at | TIMESTAMP | NOT NULL |

---

## password_tokens

Tokens utilizados para recuperação de senha.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| token | TEXT | NOT NULL, UNIQUE |
| user_id | TEXT | FK → users(id) |
| expires_at | TIMESTAMP | NOT NULL |
| used_at | TIMESTAMP | |

---

## tutors

Cadastro dos responsáveis pelos pacientes.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| user_id | TEXT | UNIQUE, FK → users(id) |
| clinic_id | TEXT | NOT NULL, FK → clinics(id) |
| full_name | TEXT | NOT NULL |
| cpf | TEXT | NOT NULL |
| phone | TEXT | NOT NULL |
| email | TEXT | |
| address | TEXT | |
| insurance | TEXT | |
| created_at | TIMESTAMP | NOT NULL |
| updated_at | TIMESTAMP | NOT NULL |

---

## patients

Cadastro dos animais atendidos.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| name | TEXT | NOT NULL |
| photo_url | TEXT | |
| birth_date | TIMESTAMP | |
| sex | TEXT | |
| weight_kg | DECIMAL(5,2) | |
| observations | TEXT | |
| microchip | TEXT | |
| allergies | TEXT | |
| species | TEXT | NOT NULL |
| breed | TEXT | |
| tutor_id | TEXT | NOT NULL, FK → tutors(id) |
| clinic_id | TEXT | NOT NULL, FK → clinics(id) |
| created_at | TIMESTAMP | NOT NULL |
| updated_at | TIMESTAMP | NOT NULL |

---

## appointments

Agendamentos veterinários.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| patient_id | TEXT | NOT NULL, FK → patients(id) |
| vet_id | TEXT | NOT NULL, FK → users(id) |
| date_time | TIMESTAMP | NOT NULL |
| end_date_time | TIMESTAMP | |
| category | AppointmentCategory | NOT NULL |
| status | AppointmentStatus | NOT NULL |
| observation | TEXT | |
| cancel_reason | TEXT | |
| created_at | TIMESTAMP | NOT NULL |
| updated_at | TIMESTAMP | NOT NULL |

---

## clinical_records

Prontuários clínicos.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| patient_id | TEXT | NOT NULL, FK → patients(id) |
| vet_id | TEXT | NOT NULL, FK → users(id) |
| appointment_id | TEXT | UNIQUE, FK → appointments(id) |
| weight_kg | DECIMAL(5,2) | |
| clinical_notes | TEXT | |
| diagnosis | TEXT | |
| pending_diagnosis | TEXT | |
| prescriptions | TEXT | |
| breathing_notes | TEXT | |
| routine_guidance | TEXT | |
| ai_summary | TEXT | |
| finalized | BOOLEAN | NOT NULL |
| created_at | TIMESTAMP | NOT NULL |
| updated_at | TIMESTAMP | NOT NULL |

---

## vaccinations

Controle de vacinação.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| patient_id | TEXT | NOT NULL, FK → patients(id) |
| vaccine_name | TEXT | NOT NULL |
| applied_at | TIMESTAMP | |
| next_dose_at | TIMESTAMP | |
| status | VaccinationStatus | NOT NULL |
| created_at | TIMESTAMP | NOT NULL |

---

## exam_files

Arquivos de exames.

| Coluna | Tipo | Restrições |
|---------|---------|---------|
| id | TEXT | PK, NOT NULL |
| patient_id | TEXT | NOT NULL, FK → patients(id) |
| clinical_record_id | TEXT | FK → clinical_records(id) |
| file_name | TEXT | NOT NULL |
| file_url | TEXT | NOT NULL |
| file_type | TEXT | NOT NULL |
| uploaded_at | TIMESTAMP | NOT NULL |

---

# Tipos Enumerados (ENUMs)

## Role

```text
OWNER
VET
TUTOR
```

## AppointmentCategory

```text
VACCINATION
OBSERVATION
EXAM
SURGICAL
```

## AppointmentStatus

```text
SCHEDULED
IN_PROGRESS
COMPLETED
CANCELLED
```

## VaccinationStatus

```text
UP_TO_DATE
PENDING
OVERDUE
```

---

# Restrições de Integridade

## Chaves Primárias

| Tabela | Chave Primária |
|---------|---------|
| clinics | id |
| users | id |
| refresh_tokens | id |
| password_tokens | id |
| tutors | id |
| patients | id |
| appointments | id |
| clinical_records | id |
| vaccinations | id |
| exam_files | id |

---

## Restrições UNIQUE

| Tabela | Coluna(s) |
|---------|---------|
| users | email |
| refresh_tokens | token |
| password_tokens | token |
| tutors | user_id |
| tutors | cpf, clinic_id |
| tutors | email, clinic_id |
| clinical_records | appointment_id |

---

## Chaves Estrangeiras

| Origem | Destino | ON DELETE | ON UPDATE |
|---------|---------|---------|---------|
| users.clinic_id | clinics(id) | RESTRICT | CASCADE |
| refresh_tokens.user_id | users(id) | CASCADE | CASCADE |
| password_tokens.user_id | users(id) | CASCADE | CASCADE |
| tutors.clinic_id | clinics(id) | RESTRICT | CASCADE |
| tutors.user_id | users(id) | SET NULL | CASCADE |
| patients.clinic_id | clinics(id) | RESTRICT | CASCADE |
| patients.tutor_id | tutors(id) | RESTRICT | CASCADE |
| appointments.patient_id | patients(id) | RESTRICT | CASCADE |
| appointments.vet_id | users(id) | RESTRICT | CASCADE |
| clinical_records.patient_id | patients(id) | RESTRICT | CASCADE |
| clinical_records.vet_id | users(id) | RESTRICT | CASCADE |
| clinical_records.appointment_id | appointments(id) | SET NULL | CASCADE |
| vaccinations.patient_id | patients(id) | RESTRICT | CASCADE |
| exam_files.patient_id | patients(id) | RESTRICT | CASCADE |
| exam_files.clinical_record_id | clinical_records(id) | SET NULL | CASCADE |

---

# Considerações Finais

O modelo da plataforma **IOUGURT** foi projetado para suportar um ambiente multi-tenant de clínicas veterinárias, garantindo:

- Integridade referencial;
- Segurança dos dados;
- Escalabilidade da aplicação;
- Consistência das informações clínicas;
- Controle de autenticação e autorização;
- Rastreabilidade dos registros médicos e exames.

A implementação utiliza recursos nativos do PostgreSQL aliados ao Prisma ORM para garantir manutenção simplificada e evolução contínua da estrutura de dados.
