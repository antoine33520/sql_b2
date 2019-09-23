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
