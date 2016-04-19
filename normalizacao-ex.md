---
layout: page
title: "Normalização: exercícios"
date:   2016-04-14 13:00:00 -0300
categories: aula
---

## Exercício 1

Resolver os exercícios disponíveis em <http://www.pedrofcarvalho.com.br/PDF/EXERCICIOS_FORMAS_NORMAIS.pdf> (não precisa montar diagrama entidade-relacionamento e nem dicionário de dados)

<!-- Outro: http://docente.ifrn.edu.br/nickersonferreira/disciplinas/programacao-com-acesso-a-banco-de-dados-3o-ano/lista-de-exercicios-01-normalizacao/view -->

### Resposta da questão 2

Historico (CodCurso, NomeCurso, Matricula, NomeAluno, Status, CodDisciplina, NomeDisciplina, CodProfessor, NomeProfessor, Notas, Faltas, Situacao)

#### 1 FN

Para passar para a primeira forma normal, deve-se identificar os atributos não-atômicos (i.e., compostos ou multivalorados) e realizar transformações para que o modelo só tenha atributos atômicos.

Aproveitaremos para identificar as chaves primárias e estrangeiras.

O único atributo multivalorado é `Notas`. Vamos movê-lo para um tabela própria, que se relacionará com a tabela histórico (1:N):


- Historico (_CodCurso_, NomeCurso, _Matricula_, NomeAluno, Status, _CodDisciplina_, NomeDisciplina, CodProfessor, NomeProfessor, Faltas, Situacao)
- Nota (_CodDisciplina_, _Matricula_, NumAvaliacao, Nota)
    - Matricula referencia Historico(Matricula)

#### 2 FN

Para passar para a segunda formal, deve-se identificar os atributos que dependem apenas de uma parte da chave e então movê-los para novas tabelas, incluindo as chaves das quais elas dependem.

- Curso (_CodCurso_, NomeCurso)
- MatriculaAluno (_Matricula_, NomeAluno)
- StatusAlunoCurso (_CodCurso_, _Matricula_, Status)
    + CodCurso referencia Curso(CodCurso)
    + Matricula referencia MatriculaAluno(Matricula)
- Disciplina (_CodDisciplina_, NomeDisciplina)
- Nota (_CodDisciplina_, _Matricula_, NumAvaliacao, Nota)
    - Matricula referencia Disciplina(CodDisciplina)
    - Matricula referencia MatriculaAluno(Matricula)
- AlocacaoProfessor(_CodCurso_, _CodDisciplina_, CodProfessor, NomeProfessor)
    + CodCurso referencia Curso(CodCurso)
    + CodDisciplina referencia Disciplina(CodDisciplina)
- Historico (_CodCurso_, _CodDisciplina_, _Matricula_, Faltas, Situacao)
    + CodCurso referencia Curso(CodCurso)
    + Matricula referencia MatriculaAluno(Matricula)
    + CodDisciplina referencia Disciplina(CodDisciplina)

Note que não existe uma única resposta certa; tudo depende dos pressupostos que assumimos ao fazer a transformação (uma vez que o enunciado da questão não é bem-definido). Nesta modelagem, assumimos os seguintes pressupostos:

- O status se refere à situação de um aluno em um determinado curso. Ex.: um aluno pode estar ativo em um curso e inativo em outro.
- Cada disciplina tem exatamente uma turma, com exatamente um professor.
- Cada aluno só pode cursar uma determinada disciplina uma vez para cada curso que fizer.

#### 3 FN

Para passar para a terceira formal, deve-se identificar os atributos que dependem indiretamente da chave e então movê-los para novas tabelas, incluindo as chaves das quais elas dependem.

Na tabela AlocacaoProfessor, NomeProfessor depende de CodProfessor, que depende da chave primária. Para resolver esse problema, vamos criar uma tabela Professor. Fica assim:

- Curso (_CodCurso_, NomeCurso)
- MatriculaAluno (_Matricula_, NomeAluno)
- StatusAlunoCurso (_CodCurso_, _Matricula_, Status)
    + CodCurso referencia Curso(CodCurso)
    + Matricula referencia MatriculaAluno(Matricula)
- Disciplina (_CodDisciplina_, NomeDisciplina)
- Nota (_CodDisciplina_, _Matricula_, NumAvaliacao, Nota)
    - Matricula referencia Disciplina(CodDisciplina)
    - Matricula referencia MatriculaAluno(Matricula)
- Professor(_CodProfessor_, NomeProfessor)
- AlocacaoProfessor(_CodCurso_, _CodDisciplina_, CodProfessor)
    + CodProfessor referencia Professor(CodProfessor)
    + CodCurso referencia Curso(CodCurso)
    + CodDisciplina referencia Disciplina(CodDisciplina)
- Historico (_CodCurso_, _CodDisciplina_, _Matricula_, Faltas, Situacao)
    + CodCurso referencia Curso(CodCurso)
    + Matricula referencia MatriculaAluno(Matricula)
    + CodDisciplina referencia Disciplina(CodDisciplina)

Note que adicionamos a restrição de chave estrangeira a AlocacaoProfessor(CodProfessor).

## Exercício 2

Considere o seguinte esquema, baseado em <http://www.cgp.ufba.br/docentes.asp>:

Professor (CodUnidade, NomeUnidade, CpfProfessor, NomeProfessor, CodDepartamento, Departamento, Classe, Nível, Regime de Trabalho, Data de Ingresso na UFBA)

Transforme-o para a 3FN.

