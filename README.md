CREATE TABLE [dbo].[Products] (
    [ProductID]     INT           NOT NULL,
    [ProductName]   NVARCHAR (50) NOT NULL,
    [Category]      NVARCHAR (50) NOT NULL,
    [StockQuantity] INT NOT NULL
 
);

//Question no. 1

INSERT INTO Products (ProductID,ProductName, Category, StockQuantity)
VALUES (1,'Laptop', 'Electronics', 50);

INSERT INTO Products (ProductID,ProductName, Category, StockQuantity)
VALUES (2,'Running Shoes', 'Sportswear', 120);

INSERT INTO Products (ProductID,ProductName, Category, StockQuantity)
VALUES (3,'Coffee Maker', 'Kitchen Appliances', 30);

INSERT INTO Products (ProductID,ProductName, Category, StockQuantity)
VALUES (4,'Notebook', 'Stationery', 200);

Select * from Products;

//Question no. 2


UPDATE Products
SET Category = 'Appliances'
WHERE ProductName = 'Coffee Maker';
Select * from Products WHERE ProductName = 'Coffee Maker';

//Question no.3


UPDATE Products
SET StockQuantity = 100
WHERE ProductName = 'Running Shoes';
 Select * from Products WHERE ProductName = 'Running Shoes';

//Question no.4


CREATE VIEW LowStockAlert AS
SELECT ProductName, Category, StockQuantity
FROM Products
WHERE StockQuantity < 50;
Select * from LowStockAlert;


//Question no.5


DELETE FROM Products
WHERE ProductName = 'Notebook';
Select * from Products WHERE ProductName = 'Notebook';

//Question no. 6


UPDATE Products
SET StockQuantity = StockQuantity + 20
WHERE ProductName = 'Laptop';
Select * from Products WHERE ProductName = 'Laptop';

//Question no.7


SELECT Category, COUNT(*) AS ProductCount
FROM Products
GROUP BY Category;

//Question no.8


SELECT ProductName, Category, (50 - StockQuantity) AS RestockQuantity
FROM Products
WHERE StockQuantity < 50;

//Question no.9

SELECT Category, SUM(StockQuantity) AS TotalStock
FROM Products
GROUP BY Category;

//Question no.10

ALTER TABLE PRODUCTS
ADD ExpirationDate DATE;

UPDATE PRODUCTS
SET ExpirationDate='2024-10-07'
WHERE ProductName='Laptop';
 
 SELECT * FROM PRODUCTS WHERE ProductName='Laptop';
