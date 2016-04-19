---
layout: page
title: "Normalização: exercícios"
date:   2016-04-14 13:00:00 -0300
categories: aula
---

## Exercício 1

Resolver os exercícios disponíveis em <http://www.pedrofcarvalho.com.br/PDF/EXERCICIOS_FORMAS_NORMAIS.pdf> (não precisa montar diagrama entidade-relacionamento e nem dicionário de dados)

<!-- Outro: http://docente.ifrn.edu.br/nickersonferreira/disciplinas/programacao-com-acesso-a-banco-de-dados-3o-ano/lista-de-exercicios-01-normalizacao/view -->

Resp 2:

Historico (CodCurso, NomeCurso, Matricula, NomeAluno, Status, CodDisciplina, NomeDisciplina, CodProfessor, NomeProfessor, Notas, Faltas, Situacao)

=== 1 FN ==>

Historico (_CodCurso_, NomeCurso, _Matricula_, NomeAluno, Status, _CodDisciplina_, NomeDisciplina, _CodProfessor_, NomeProfessor, Faltas, Situacao)

Nota (_CodDisciplina_, _Matricula_, Nota)

== 2 FN ==>

Historico (_CodCurso_, _Matricula_, _CodDisciplina_, _CodProfessor_, Faltas, Situacao)

StatusAlunoCurso (_CodCurso_, _Matricula_, Status)
Curso (_CodCurso_, NomeCurso,)
Aluno (_Matricula_, NomeAluno)
Disciplina (_CodDisciplina_, NomeDisciplina)
Professor (_CodProfessor_, NomeProfessor)

## Exercício 2

Considere o seguinte esquema, baseado em <http://www.cgp.ufba.br/docentes.asp>:

Professor (CodUnidade, NomeUnidade, CpfProfessor, NomeProfessor, CodDepartamento, Departamento, Classe, Nível, Regime de Trabalho, Data de Ingresso na UFBA)

Transforme-o para a 3FN.

