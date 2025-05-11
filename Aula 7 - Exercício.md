Aluno: Victor Jorge Carvalho Chaves
RA: 156.740

---

# Parte 1

**Questão 2**

![[Pasted image 20250507212713.png]]

Teve o tempo de demora de 0,00092821 segundos

**Questão 3**

![[Pasted image 20250507212756.png]]

**type**: ALL, significa uma varredura completa da tabela.
**key**: NULL, indica que nenhum índice (index) está sendo utilizado.
**rows**: Contém 510 linhas nesta leitura.

**Questão 5**
![[Pasted image 20250507213235.png]]


**type**: ALL, significa uma varredura completa da tabela.
**key**: NULL, indica que nenhum índice (index) está sendo utilizado.
**rows**: Contém 510 linhas nesta leitura.

Porém, comparado na ultima consulta, há a informação do **idx_cidade** na coluna **possible_keys**.

**Questão 6**
![[Pasted image 20250507213452.png]]

Ocorreu uma melhoria de 0,0009 para 0,0008

**Questão G**

![[Pasted image 20250507213558.png]]

Sim, indica o índice `email`

**Questão 11**

![[Pasted image 20250507213707.png]]

Ocorreu uma mudança, na coluna `possible_keys` foi adicionado o índice `idx_email`. 

---

# Parte 2

**Questão 2**

![[Pasted image 20250507213923.png]]

Não, ela não utilizou nenhum índice.

**Questão 4**

![[Pasted image 20250507214038.png]]

Sim, o índice composto `idx_cidade_nome` foi utilizado.

![[Pasted image 20250507214203.png]]

Caso troque a ordem na condição não altera o índice.

---

# Parte 3

**Questão 2 e 4 e 5**

Antes de criar o `INDEX`.
![[Pasted image 20250507214407.png]]

Após de criar o `INDEX`.
![[Pasted image 20250507214505.png]]

Após a criação do *INDEX* *idx_conteudo_fulltext*, ele consta sendo utilizado como índice na consulta.

E o *type* deixa de ser *ALL*  e vira *idx_conteudo_fulltext*.

E a quantidade de *rows* se torna 1 do que 3.

Demonstrado na tabela abaixo, houve uma otimização no tempo da consulta `SELECT * FROM artigos WHERE MATCH (conteudo) AGAINST ('MariaDB');`, de 0,001 segundos para 0,0004 segundos
![[Pasted image 20250507215216.png]]

**Questão 1: Em quais situações a criação de um índice é mais benéfica? **

- Consultas utilizando as cláusulas: *WHERE*, *JOIN*, *ORDER BY* e *GROUP BY*
- Colunas com alta cardinalidade (alta variedade nos dados).

**Questão 2: Ǫuais são os custos associados à criação de índices?**

- Maior consumo de espaço na memória física
- Aumento no custo nas operações de *INSERT*, *UPDATE* e *DELETE* (pois, necessitam estar criando/alterando os índices).

**Questão 3: Como a cardinalidade de uma coluna afeta a utilidade de um índice?**

Índice com alta cardinalidade permitem melhor seletividade em operações de filtro, enquanto índices com baixa cardinalidade, não possibilitam isso, já que a alta repetição de informações prejudica na distinção nas linhas. Todavia, isso pode ser amenizado com a criação de índices compotos.