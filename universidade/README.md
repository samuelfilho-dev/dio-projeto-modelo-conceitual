# Diagrama De Modelagem de Universidade

### Entidades
 - Disciplina
 - Professor
 - Pré-requisitos Das Disciplinas
 - Pré-Requisitos
 - Matriculado
 - Aluno
 - Departamento
 - Curso
 - Disciplina & Curso

### Diagrma Da Universidade v1 (Versão 1)
```mermaid
classDiagram
    class Disciplina {
        - Interger idDisciplina
        - Interger idProfessor
    }

    class Professor {
        - Interger idProfessor
        - Interger idDepartamento
    }

    class Aluno {
        - Interger idAluno
        - Interger idProfessor
    }

    class Matriculado {
        - Interger idAluno
        - Interger idDisciplina
    }

    class Departamento {
        - Interger IdDepartamento
        - String Nome
        - String Campus
        - Interger IdCoordenador
    }

    class Curso {
        - Interger idCurso
        - Interger idDepartamento
    }

    class Disciplina_Curso {
        - Interger idDisciplina
        - Interger idCurso
    }

    class Pre-requisitos {
        - Interger idPrérequisitos
    }

    class Pre-requisitos das Disciplinas {
        - Interger idDisciplina
        - Interger idPrérequisitos
    }

    Disciplina "1" --* "N" Matriculado
    Aluno "1" --* "N" Matriculado
    Professor "1" --* "N" Aluno
    Professor "1" -- "1" Departamento
    Departamento "1" --* "N" Professor
    Departamento "1" --* "N" Curso
    Curso "1" --* "N" Disciplina_Curso
    Disciplina "1" --* "N" Disciplina_Curso
    Pre-requisitos "1" --* "N" Pre-requisitos das Disciplinas
    Disciplina "1" --* "N" Pre-requisitos das Disciplinas
```

---

### Diagrma Da Universidade Refinado
```mermaid
classDiagram
    class Pessoa {
        - Interger idPessoa
        - String Nome
        - String CPF
        - String Endereço
    }

    class Disciplina {
        - Interger idDisciplina
        - Interger idProfessor
    }

    class Professor {
        - Interger idProfessor
        - Interger idDepartamento
        - Interger idPessoa
    }

    class Aluno {
        - Interger idAluno
        - Interger idProfessor
        - Interger idPessoa
    }

    class Matriculado {
        - Interger idAluno
        - Interger idDisciplina
    }

    class Departamento {
        - Interger IdDepartamento
        - String Nome
        - String Campus
        - Interger IdCoordenador
    }

    class Curso {
        - Interger idCurso
        - Interger idDepartamento
    }

    class Disciplina_Curso {
        - Interger idDisciplina
        - Interger idCurso
    }

    class Pre-requisitos {
        - Interger idPrérequisitos
    }

    class Pre-requisitos das Disciplinas {
        - Interger idDisciplina
        - Interger idPrérequisitos
    }

    class Periodo {
        - Interger idPeriodo
        - String Ano
        - String Semestre
    }

    class Oferta de Disciplina {
        - Interger idPeriodo
        - Interger idDisciplina
        - Interger idProfessor
    }

    class Extensao {
        - Interger idExtensão
        - String Nome
        - String Área
        - String Instituição
    }

    class Extensao_has_aluno {
        - Interger idExtensão
        - Interger idAluno
    }


    Disciplina "1" --* "N" Matriculado
    Aluno "1" --* "N" Matriculado
    Professor "1" --* "N" Aluno
    Professor "1" -- "1" Departamento
    Departamento "1" --* "N" Professor
    Departamento "1" --* "N" Curso
    Curso "1" --* "N" Disciplina_Curso
    Disciplina "1" --* "N" Disciplina_Curso
    Pre-requisitos "1" --* "N" Pre-requisitos das Disciplinas
    Disciplina "1" --* "N" Pre-requisitos das Disciplinas
    Pessoa "1" .. "1" Aluno
    Pessoa "1" .. "1" Professor
    Disciplina "1" --* "N" Oferta de Disciplina
    Periodo "1" --* "N" Oferta de Disciplina
    Extensao "1" --* "N" Extensao_has_aluno
    Aluno "1" --* "N" Extensao_has_aluno
```