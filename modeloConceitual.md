# Modelo Conceitual

#### Entidades

- Paciente
    ID_paciente  (PK)
    Nome
    CPF
    NumeroTelefone
    Sexo
    DataNascimento
    Endereco
    Sintomas
    Status
    DataHoraChegada

- Triagem
    ID_paciente (FK) 
    ID_enfermeira (FK)
    Temperatura
    Peso
    Glicose
    Pressao
    Saturacao
    ClassificacaoDeRisco
    DataHoraTriagem

- FilaAtendimento
    ID_paciente (FK)
    Prioridade

- Enfermeira
    ID_enfermeira (PK)
    Nome
    Corem
    CPF

- Atendimento
    ID_atendimento (PK)
    ID_paciente (FK)
    ID_medico (FK)
    DataHoraInicioFim
    Diagnostico

- Medico
    ID_medico (PK)
    Nome
    CRM
    CPF


### Relacionamentos

Entidade A  | Relacionamento | Entidade B      | Cardinalidade | Tipo

Paciente    | realiza        | Triagem         | 1:1           | Obrigatório
Paciente    | entra_na       | FilaAtendimento | 1:1           | Temporário
Paciente    | recebe         | Atendimento     | 1:N           | Obrigatório
Atendimento | é_feito_por    | Médico          | N:1           | Obrigatório
Triagem     | é_feita_por    | Enfermeira      | N:1           | Opcional