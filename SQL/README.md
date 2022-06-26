## SQL QUERIES BEYOND THE BASICS

# Return all rows where field !== null/specified arg

SELECT field1, field2 FROM  
TABLE1  
WHERE field is NOT NULL  
ORDER BY field2 ASC

# Adding Logic VIA CASE statement

    SELECT firstname, lastname, age               <--- Returned Fields
    CASE                                     <--- Case statement opens
    WHEN Age = 38 THEN "Stanley" conditions.
    WHEN Age > 30 THEN "Old"
    ELSE "Baby"
    END                                                  <--- End Case
    FROM employees                               <--- Destination/Table
    WHERE Age is NOT NULL                             <--- Where Clause
    ORDER BY Age

## Find n delete duplicate (keeping lowerID document)

DELETE t1 FROM Person t1
INNER JOIN Person t2
WHERE
t1.id > t2.id AND
t1.email = t2.email;

## Find Duplicates

SELECT email as Email
FROM Person
GROUP BY email
HAVING COUNT(email) = 2 OR COUNT(email) > 2

## Find shared value(Id/parentId) and make a comparison

SELECT t2.name as Employee FROM Employee t1
INNER JOIN Employee t2
WHERE
t1.id = t2.managerId
AND
t1.salary < t2.salary;
