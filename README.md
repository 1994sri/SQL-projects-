# SQL-projects- 1 


select * from salesman
 -- Insert a new record in your Orders tabl
 insert into dbo.orders values( 5002,4567,103,'2021-06-05',1000) 

 -- select * from Salesman .Add default constraint for City column in Salesman table .  Add Foreign key constraint for SalesmanId column in Customer table.
-- Add not null constraint in Customer_name column for the
-- Customer table
ALTER TABLE salesman
ADD default (salesmanid); 

ALTER TABLE salesman ADD CONSTRAINT DF_SomeName DEFAULT N'cities' FOR City; 

 
ALTER TABLE customer ADD CONSTRAINT FK_salesmanid FOREIGN KEY (salesmanid) REFERENCES salesmanid (salesman); 

ALTER TABLE customer
Alter column customername varchar(255) not null 

--Fetch the data where the Customer’s name is ending with ‘N’ also get the purchase amount value greater than 500. 


 select *
from Customer
where right(CustomerName, 1) = 'N' and PurchaseAmount > 500;

 -- Using SET operators, retrieve the first result with unique SalesmanId values from two
--tables, and the other result containing SalesmanId with duplicates from bot table  

select SalesmanId
from Salesman
union 
select SalesmanId
from Customer


select SalesmanId
from Salesman
union all
select SalesmanId
from Customer

--- Display the below columns which has the matching data Orderdate,  
--Salesman Name, Customer Name, Commission, and City which has the range of Purchase Amount between 500 to 1500. 


 Select
 O.Orderdate,
 S.name as 'Salesman Name',
 C.CustomerName as 'Customer Name',
 S.Commission,
 S.City
from
 Orders O
join
 Salesman S on O.SalesmanId = S.SalesmanId
JOIN
 Customer C on O.CustomerId = C.CustomerId
where
 C.PurchaseAmount BETWEEN 500 AND 1500;
       
-- Using right join fetch all the results from Salesman and Orders table 

select * from Salesman
right join orders on Salesman.SalesmanId = order


