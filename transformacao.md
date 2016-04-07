---
layout: page
title: "Transformação de modelos: ER => relacional"
date:   2016-04-07 13:00:00 -0300
categories: aula
---

Para os exercícios a seguir, use uma das seguintes ferramentas online:

- <https://dbdesigner.net/>
- <http://vertabelo.com/>

## Farmácia

Tirado do livro de Heuser.

Projete um modelo lógico para o modelo conceitual a seguir, usando o paradigma relacional.

![]({{ "/images/der-farmacia.png" | prepend: site.baseurl}})

Para não sobrecarregar o diagrama os atributos das entidades são listados abaixo. Os atributos identificadores estão sublinhados.

- Produto (<u>Número</u>, NomeComercial, TipoEmbalagem, Quantidade, PreçoUnitário)
- Fabricante (<u>CNPJ</u>, Nome, Endereço)
- Medicamento(Tarja, Fórmula)
- Perfumaria(Tipo)
- Venda(Data, <u>NúmeroNota</u>, NomeCliente, CidadeCliente)
- PerfumariaVenda(Quantidade, Imposto)
- MedicamentoReceitaVenda(Quantidade, Imposto)
- ReceitaMédica(<u>CRM, Número</u>, Data)

## Campeonato

Projete um modelo lógico para o modelo conceitual a seguir, usando o paradigma relacional.

![]({{ "/images/der-campeonato.jpg" | prepend: site.baseurl}})

Se achar necessário, veja também os [requisitos](modelagem).

## Cinema

Projete um modelo lógico para o modelo conceitual a seguir, usando o paradigma relacional.

![]({{ "/images/der-cinema.jpg" | prepend: site.baseurl}})

Se achar necessário, veja também os [requisitos](modelagem).