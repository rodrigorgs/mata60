---
layout: page
title: "Modelagem conceitual"
date:   2016-03-31 13:00:00 -0300
categories: aula
---

Para os exercícios a seguir, use um dos seguintes editores de diagramas:

- <https://www.gliffy.com/>
- <https://www.draw.io/> (não está funcionando no lab)

# Exercício 1: campeonato

(baseado no material da profa. Fabíola Araújo)

Faça o modelo de um banco de dados utilizando os diagramas vistos no Modelo Entidade-Relacionamento (MER), que armazene informações sobre campeonatos de futebol. Os requisitos do sistema são:

1. É necessário armazenar informações sobre vários times de futebol que compõem apenas um campeonato;
2. Cada time possui um técnico e vários jogadores;
3. Um time possui um nome e a data de fundação;
4. Registram-se os jogos que um time realizou com informações sobre o placar, renda, a data do jogo e o público pagante;
5. Um time pode jogar vários jogos e cada jogo acontece em um estádio;
6. Cada estádio possui uma localização (endereço), uma capacidade e um nome;
7. É necessário registrar as seguintes informações dos jogadores e técnicos: nome, idade, sexo, endereço e telefone;
8. Cada um dos técnicos e jogadores tem seus relacionamentos com os times, sendo que cada técnico ou jogador só pertence a um único time;

Ao realizar a modelagem, defina no seu modelo:

a. Entidades.
b. Atributos de cada entidade, incluindo chave primária.
c. Relacionamentos
d. Cardinalidade dos relacionamentos (mínima e máxima).
e. Generalização/especialização

<!-- R: http://www.gliffy.com/go/publish/10328161 -->

# Exercício 2: cinema

(baseado no material do prof. Benjamin Moreira)

Construa um diagrama entidade-relacionamento (DER) de acordo com os requisitos a seguir.

Um cinema possui várias salas de cinema, as quais exibem filmes em horários diversos. O cinema tem interesse em saber quais filmes estão atualmente em cartaz, em que salas e em que horários.

Cada sala possui um nome (único) e capacidade (número de lugares). Os filmes são caracterizados por seu nome em português, nome na língua original (se estrangeiro), diretor, ano de lançamento, tipo, e sinopse. Não existem dois filmes com o mesmo nome (em português) e ano de lançamento.

Eventualmente, podem existir para o filme premiações ou indicações para premiação (e.g. Palma de Ouro em 1987, Oscar de melhor atriz em 89, indicado para melhor filme estrangeiro em 1996), e esta informação é usada para divulgação dos filmes.

Uma exibição de filme ocorre em uma dada sala e horário. Um mesmo filme pode ser exibido na mesma sala, em vários horários. Para filmes muito procurados, o cinema pode ter exibição simultâneas em várias salas (em horários simultâneos ou não). Filmes diferentes podem passar na mesma sala, desde que obviamente não no mesmo horário.

O cinema só trabalha com horários fixos de filmes, os quais atualmente são: 16:00, 17:00, 18:00, 19:30, 20:00, 22:00, 24:00.

A cada um destes horários está vinculado um conjunto de funcionários responsáveis pelo bom andamento das atividades do cinema naquele horário, e que desempenham uma função (ex: caixa, balas, lanterninha, bilheteiro).

Cada funcionário é caracterizado pelo número da carteira da trabalho (único), nome, data de admissão e salário. Para maior satisfação dos funcionários, existe um rodízio das funções conforme o horario (ex: um mesmo funcionário pode ser caixa no horario das 16:00, e baleiro no horário das 21:00). Todo horário tem pelo menos três funcionários alocados. 
