# Praticando SQL Curso Proz...

Lembre-se, cada desafio é uma chance de crescer. Não se desanime com os erros; eles são degraus no caminho do aprendizado. E acima de tudo, divirta-se! 
O aprendizado mais eficaz acontece quando nos engajamos e nos interessamos pelo que estamos fazendo.

 Vamos imaginar uma tabela de alunos com as seguintes colunas: ID, Nome, Ano, Nota e uma tabela de professores com as colunas ID, PNome, UNome.

#### Tabela Alunos (Exemplo)
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/1#issuecomment-2224265488.png"/>

```

#### Tabela Professor (Exemplo)
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/2#issue-2404493027.png"/>

```
#### Tabela Professor (Exemplo)

1. Mostre as informações apenas dos alunos aprovados (nota acima de 7.0):
```sql
SELECT * FROM ALUNO WHERE Nota > 7.0;
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/2#issue-2404493027.png"/>

2. Exiba as informações dos alunos do primeiro ano com nota maior ou igual a 8.0:
```sql
SELECT * FROM ALUNO WHERE Ano = 1 AND Nota >= 8.0;
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/3#issue-2404501419.png"/>

3. Exiba apenas os nomes e as notas dos alunos:
```sql
SELECT Nome, Nota FROM ALUNO;
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/4#issue-2404518512.png"/>

4. Crie uma tabela PROFESSOR que apresente apenas o primeiro e o último nome do professor:
 ```sql
   CREATE TABLE NOVO_PROFESSOR AS 
SELECT PNome, UNome FROM PROFESSOR;
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/5#issue-2404520732.png"/>

5. Crie uma tabela ALUNO com o primeiro e o último nome de cada:
Primeiro, vamos supor que temos os nomes completos e precisamos dividi-los:
 ```sql
CREATE TABLE NOVO_ALUNO AS
SELECT SUBSTRING_INDEX(Nome, ' ', 1) AS PNome, SUBSTRING_INDEX(Nome, ' ', -1) AS UNome FROM ALUNO;
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/6#issue-2404522315.png"/>

6. Mostre o resultado da união entre a tabela ALUNO(PNome, UNome) e a tabela PROFESSOR:
 ```sql
SELECT PNome, UNome FROM NOVO_ALUNO
UNION
SELECT PNome, UNome FROM NOVO_PROFESSOR;
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/7#issue-2404524308.png"/>

7. Exiba o resultado da intersecção entre a tabela ALUNO(PNome, UNome) e a tabela PROFESSOR:
```sql
SELECT PNome, UNome FROM NOVO_ALUNO
INTERSECT
SELECT PNome, UNome FROM NOVO_PROFESSOR;
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/8#issue-2404525252.png"/>

8. Exiba o resultado da diferença entre a tabela ALUNO(PNome, UNome) e a tabela PROFESSOR:
 ```sql
SELECT PNome, UNome FROM NOVO_ALUNO
EXCEPT
SELECT PNome, UNome FROM NOVO_PROFESSOR;
```
<img src="https://github.com/DanniNascimento/Praticando_SQL_Aluno_PROZ/issues/9#issue-2404525971.png"/>

