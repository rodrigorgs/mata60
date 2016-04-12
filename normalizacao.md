---
layout: page
title: "Normalização"
date:   2016-04-12 13:00:00 -0300
categories: aula
---

<!--
Exemplos:

- https://twiki.ufba.br/twiki/pub/SUPAC/GradGuiaAreaI/112.html
- Exemplo do livro do Silberschatz

Jura dizer a verdade, somente a verdade, nada mais do que a verdade?

-->

## Referências

- <https://en.wikipedia.org/wiki/Database_normalization>
- <http://www.studytonight.com/dbms/database-normalization.php>
- Heuser: engenharia reversa e normalização (cap. 6)
- <http://stackoverflow.com/questions/539324/what-is-a-good-kiss-description-of-boyce-codd-normal-form/539990>
- <http://stackoverflow.com/questions/723998/what-are-1nf-2nf-and-3nf-in-database-design>

## Anomalias



## Domínios atômicos e 1FN

## Dependência funcional

## 2FN

## Exemplo

<https://twiki.ufba.br/twiki/pub/SUPAC/GradGuiaAreaI/112.html>

```
Aula (disc, turma, vagas, dia, horario, docente)

== 1 FN ==>

Aula (*cod_disc*, nome_disc, *turma*, vagas, *dia*, *hora_ini*, hora_fim, docente)

== 2 FN ==>

Aula (*cod_disc*, *turma*, *dia*, *hora_ini*, hora_fim, docente)
Disciplina (*cod_disc*, nome_disc)
Vagas (*cod_disc*, *turma*, num_vagas)

== 3 FN ==>

(igual)
```