# Commands

```SQL
MIN() # Get MIN Value in a Group
MAX() # Get MAX Value in a Group
AVG() # Get Average Value in a Group

# Example of a GROUP BY Query
SELECT  m.codf, COUNT(DISTINCT(p.cache)) FROM MOVIE m 
INNER JOIN CHARACTER c ON m.codf = c.codf  
WHERE c.cache > 2000
GROUP BY m.codf 
HAVING SUM(c.cache) < 8000;

# Example of a GROUP BY Query
SELECT a.name, SUM(p.cache) FROM ACTOR a 
INNER JOIN CHARACTER c ON a.coda = c.coda 
WHERE c.cache > (SELECT AVG(ch.cache) FROM CHARACTER ch)
GROUP BY a.coda;

# Case with IN
SELECT m.nome FROM Medico m 
WHERE m.cod IN (SELECT fp.medico_cod FROM Folha_Pagto fp WHERE fp.valor > (SELECT AVG(fp2.valor) FROM Folha_Pagto fp2));

# Case with NOT IN
SELECT m.nome FROM Medico m 
WHERE m.cod NOT IN (SELECT m2.cod FROM Medico m2 
WHERE m2.cod NOT IN (SELECT fp.medico_cod FROM Folha_Pagto fp)
OR m2.cod IN (SELECT fp2.medico_cod FROM Folha_Pagto fp2 GROUP BY fp2.medico_cod HAVING MAX(fp2.valor) < (SELECT AVG(fp3.valor) FROM Folha_Pagto fp3)));

# Case with ANY
SELECT m.nome FROM Medico m 
WHERE (SELECT AVG(fp2.valor) FROM Folha_Pagto fp2) < ANY (SELECT fp.valor FROM Folha_Pagto fp WHERE fp.medico_cod = m.cod);

SELECT e.cod, e.nome  FROM Medico m, MedicoEspecialidade me, Especialidade e  
WHERE me.medico_cod = m.cod AND m.nome = 'Paulo' AND me.especialidade_cod  = e.cod 

```