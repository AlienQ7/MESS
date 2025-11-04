```
INSERT INTO WORDS VALUES ('Oracle');
INSERT INTO WORDS VALUES ('SQL');
INSERT INTO WORDS VALUES ('MapReduce');
INSERT INTO WORDS VALUES ('SQL');
INSERT INTO WORDS VALUES ('SQL');
INSERT INTO WORDS VALUES ('Oracle');
INSERT INTO WORDS VALUES ('BigData');
COMMIT;
```
```
SELECT
    word,
    1 AS occurrence
FROM
    WORDS;
```
```

SELECT
    word,
    COUNT(*) AS total_count
FROM
    WORDS
GROUP BY
    word
ORDER BY
    total_count DESC; -- Optional: Sorts by frequency
```
```
SELECT
    word,
    COUNT(*) AS total_count
FROM
    WORDS
GROUP BY
    word
HAVING
    COUNT(*) > 1;
```
```
SELECT
    word,
    COUNT(*) AS total_count
FROM
    WORDS
GROUP BY
    word
HAVING
    COUNT(*) = (SELECT MAX(COUNT(*)) FROM WORDS GROUP BY word);
```
```
SELECT
    word,
    COUNT(*) AS total_count
FROM
    WORDS
GROUP BY
    word
HAVING
    COUNT(*) = (SELECT MAX(COUNT(*)) FROM WORDS GROUP BY word);

```
```
SELECT
    word,
    ROUND((COUNT(*) / (SELECT COUNT(*) FROM WORDS)) * 100, 2) AS percentage
FROM
    WORDS
GROUP BY
    word
ORDER BY
    percentage DESC;
```
