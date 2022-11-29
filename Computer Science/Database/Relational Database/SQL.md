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
```