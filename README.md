# Refinando os Projeto Conceitual de Banco de Dados – E-COMMERCE e UNIVERSIDADE
## Objetivo:
Refine o modelo apresentado acrescentando os seguintes pontos:
- Cliente PJ e PF – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
- Pagamento – Pode ter cadastrado mais de uma forma de pagamento;
- Entrega – Possui status e código de rastreio;

##  E-COMMERCE
Resumo Narrativo do Modelo:
- Cliente cadastra-se na plataforma utilizando CPF ou CNPJ e fornece seu endereço, que será usado para calcular o frete.
- Pedido é criado pelo Cliente e registra informações da compra, incluindo o endereço de entrega, status (que pode indicar se o pedido foi cancelado) e o período de carência para devolução.
- Cada Pedido pode conter um ou mais Produtos – informação capturada através da entidade associativa ItemPedido.
- Cada Produto é ofertado na plataforma e está associado a um único Fornecedor, que é responsável pelo fornecimento do item.
- O Fornecedor administra um ou mais Estoques, que armazenam os produtos. A disponibilidade dos produtos em cada estoque é controlada pela associação ProdutoEstoque.
  
![E-commerce](https://github.com/user-attachments/assets/d9772706-4692-4c24-86e4-7aa1ecdefb8d)

## Universidade
Narrativa do Projeto
A narrativa descreve o seguinte cenário:
- Alunos podem se matricular em mais de um curso de graduação.
- Alunos podem fazer cursos extras (internos ou externos) para contar como horas complementares.
- Não há restrição quanto ao número de disciplinas que um aluno pode cursar, desde que não haja sobreposição de horário.
- Disciplinas são oferecidas por professores, e algumas disciplinas possuem pré-requisitos.
- Professores estão associados a departamentos e coordenam cursos.
- Cada disciplina é avaliada por meio de duas provas por semestre, e trabalhos podem compor a nota final.
- O ciclo de vida das disciplinas é semestral.

## Regras de Negócio
- Média para aprovação:
A nota final é calculada como a média das duas provas.
Aprovado se Nota_Final >= 8.0.

- Restrições:
Um aluno não pode se matricular em disciplinas com sobreposição de horário.
Um professor só pode ministrar disciplinas do seu departamento.

- Visões:
Visão para alunos: Ver notas, horários, disciplinas matriculadas.
Visão para professores: Ver turmas, alunos matriculados, notas.
Visão para coordenação: Ver desempenho dos cursos e professores.

## Passos de Refinamento
- Identificação das entidades principais: Aluno, Curso, Disciplina, Professor, Departamento, Matrícula, Turma, Prova, Curso Extra, Horas Complementares.
- Definição dos relacionamentos entre as entidades.
- Identificação dos atributos essenciais para cada entidade.
  
![Universidade](https://github.com/user-attachments/assets/adda2016-7421-46be-8881-e2fb16340b52)

## Respostas às Perguntas
- Quais informações de aluno e professor guardar?
 Aluno: Nome, CPF, data de nascimento, endereço, email, telefone.
 Professor: Nome, CPF, titulação, área de atuação, departamento.

- Qual média para aprovação?
Média 8.0, calculada com base nas duas provas.

- Haverá restrição ou diferentes visões?
Restrição de horário para matrícula.

- Visões separadas para alunos, professores e coordenação.
- Pagamentos, o aluno escolhe o metodo.
