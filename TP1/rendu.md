# SQL

## Lab 01

```sql
SELECT * FROM employee;
```

```sql
SELECT invoiceId, CustomerId, InvoiceDate FROM Invoice;
```

```sql
SELECT concat(UPPER(LastName),',',FirstName), Phone FROM Employee;
```

```sql
SELECT concat(InvoiceId,'(',Total,')'), REPLACE(FORMAT(InvoiceDate,'yyyy-mm-dd'), '-','.') FROM Invoice;
```

```sql
SELECT TrackId, concat(Name,' - ',ISNULL(Composer,'Now Sport / NA') ) FROM Track;
```

## Lab 02

```sql
SELECT DISTINCT City FROM Customer
```

```sql
SELECT TOP 10 InvoiceId, Total
FROM Invoice
ORDER BY Total DESC
```

```sql
SELECT * FROM Customer WHERE CustomerId = 47
```

```sql
SELECT CustomerId, FirstName, LastName FROM Customer WHERE City = 'Bordeaux' OR  City = 'Chicago' OR  City = 'Lisbon' OR  City = 'Berlin'
```

...

## Lab 03

```sql
SELECT i.InvoiceId, concat(c.FirstName , c.LastName), i.Total
FROM Invoice i
JOIN Customer c
ON i.CustomerId = c.CustomerId ;
```

```sql
SELECT i.InvoiceId, CONCAT(c.LastName, ' ', c.FirstName) AS "Nom et prénom du client", i.Total, CONCAT(e.LastName, ' ', e.FirstName) AS "Nom et prénom de l'employé",
art.Name AS "Nom de l'artiste"
FROM Invoice i
JOIN Customer c
ON i.CustomerId = c.CustomerId
JOIN Employee e
ON c.SupportRepId = e.EmployeeId
JOIN InvoiceLine il
ON i.InvoiceId = il.InvoiceId
JOIN Track t
ON il.TrackId = t.trackId
JOIN Album alb
ON t.AlbumId = alb.AlbumId
JOIN Artist art
ON alb.ArtistId = art.ArtistId;
```

```sql
SELECT t.TrackId, t.Name, t.album
FROM Invotce i
RIGHT JOIN Track t
ON t.trackId = i.trackId
WHERE InvoiceId is NULL;
```

```sql
SELECT e.employeeID, e.lastName, e.Email, e.RespondsTo, m.lastName, m.Email
FROM Employee e
LEFT JOIN Employee m
ON m.EmployeeId = e.ReportsTo;
```

## Lab 04

```sql
SELECT c.Address, c.City, c.Country, e.Address, e.City, e.Country
FROM  Customer c
JOIN Employee e
ON c.SupportRepId = e.EmployeeId
```

```sql
SELECT c.Country, I.BillingCountry
FROM Customer c
INNER JOIN Invoice I on c.CustomerId = I.CustomerId
GROUP BY c.Country, I.BillingCountry
HAVING count(*)>1
```

```sql
SELECT C.Address
FROM Customer C
LEFT JOIN Invoice I on C.CustomerId = I.CustomerId
WHERE I.CustomerId IS NULL
```
