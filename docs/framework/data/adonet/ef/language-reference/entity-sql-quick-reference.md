---
title: "Краткий справочник по языку Entity SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Краткий справочник по языку Entity SQL
В этом разделе содержится краткий справочник по запросам [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  Запросы, описанные в этом разделе, основаны на модели AdventureWorks Sales.  
  
## Литералы  
  
### Строковое  
 Существуют строковые литералы в Юникоде и не в Юникоде.  Строки в Юникоде предваряются символом N.  Например, `N'hello'`.  
  
 Ниже приведен пример строкового литерала не в Юникоде:  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 Результат  
  
|Значение|  
|--------------|  
|hello|  
  
### DateTime  
 В литералах DateTime обязательными являются и часть даты, и часть времени.  Значения по умолчанию отсутствуют.  
  
 Пример  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 Результат  
  
|Значение|  
|--------------|  
|Понедельник, 25.12.06, 01:01:00|  
  
### Целое число  
 Целочисленные литералы могут иметь тип Int32 \(123\), UInt32 \(123U\), Int64 \(123L\) и UInt64 \(123UL\).  
  
 Пример  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 Результат  
  
|Значение|  
|--------------|  
|1|  
|2|  
|3|  
  
### Другой  
 Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает и другие типы литералов \- Guid, Binary, Float\/Double, Decimal и `null`.  Литералы NULL в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] считаются совместимыми с любым из других типов в концептуальной модели.  
  
## Конструкторы типов  
  
### ROW  
 [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) Конструктор создает анонимное значение \(запись\) со структурной типизацией, как показано в следующем примере: `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 Пример  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 Результат  
  
|ProductID|Имя|  
|---------------|---------|  
|1|Adjustable Race|  
|879|All\-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### MULTISET  
 Конструктор [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) создает коллекции, например, следующим образом:  
  
 `MULTISET(1,2,2,3)` `--same as`\-`{1,2,2,3}.`  
  
 Пример  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 Результат  
  
|ProductID|Имя|ProductNumber|…|  
|---------------|---------|-------------------|-------|  
|842|Touring\-Panniers, Large|PA\-T100|…|  
  
### Объект  
 Конструктор [Конструктор именованных типов](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) создает определяемые пользователем \(именованные\) объекты, например `person("abc", 12)`.  
  
 Пример  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 Результат  
  
|SalesOrderDetailID|CarrierTrackingNumber|OrderQty|ProductID|...|  
|------------------------|---------------------------|--------------|---------------|---------|  
|1|4911\-403C\-98|1|776|...|  
|2|4911\-403C\-98|3|777|...|  
|...|...|...|...|...|  
  
## Ссылки  
  
### REF  
 Оператор [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) создает ссылку на экземпляр типа сущности.  Например, следующий запрос возвращает ссылки на каждую сущность Order в наборе сущностей Orders:  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 Результат  
  
|Значение|  
|--------------|  
|1|  
|2|  
|3|  
|...|  
  
 В следующем примере оператор извлечения свойства \(.\) используется для доступа к свойству сущности.  При использовании этого оператора автоматически выполняется разыменование ссылки.  
  
 Пример  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 Результат  
  
|Значение|  
|--------------|  
|Adjustable Race|  
|All\-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### DEREF  
 Оператор [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) разыменовывает значение ссылки и возвращает результат разыменования.  Например, следующий запрос возвращает сущности Order для каждой из записей Order в наборе сущностей Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.  
  
 Пример  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 Результат  
  
|Значение|  
|--------------|  
|Adjustable Race|  
|All\-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### CREATEREF и KEY  
 Оператор [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) создает ссылку, передавая ключ.  Оператор [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) извлекает ключевую часть из выражения со ссылкой на тип.  
  
 Пример  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 Результат  
  
|ProductID|  
|---------------|  
|980|  
|365|  
|771|  
|...|  
  
## Функции  
  
### Канонические  
 Доступ к [каноническим функциям](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) производится через пространство имен Edm, например `Edm.Length("string")`.  Если не импортировано другое пространство имен, содержащее функцию, имя которой совпадает с именем канонической функции, то указывать пространство имен не обязательно.  Если в двух пространствах имен имеется функция с тем же именем, то пользователь должен указать полное имя функции.  
  
 Пример  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 Результат  
  
|NameLen|  
|-------------|  
|6|  
|6|  
|5|  
  
### Функции поставщиков данных \(Майкрософт\)  
 [Функции поставщиков данных \(Майкрософт\)](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) находятся в пространстве имен `SqlServer`.  
  
 Пример  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 Результат  
  
|EmailLen|  
|--------------|  
|27|  
|27|  
|26|  
  
## Пространства имен  
 Оператор [USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) задает пространства имен, используемые в выражении запроса.  
  
 Пример  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 Результат  
  
|Значение|  
|--------------|  
|aa|  
  
## Разбивка на страницы  
 Разбиение на страницы можно выразить, задав объявления вложенных предложений [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) и [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) в предложении [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
 Пример  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 Результат  
  
|Идентификатор|Имя|  
|-------------------|---------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## Группирование  
 Ключевое слово [GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) определяет группы, в которые должны быть помещены объекты, возвращаемые выражением запроса \([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)\).  
  
 Пример  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 Результат  
  
|имя|  
|---------|  
|LL Mountain Seat Assembly|  
|ML Mountain Seat Assembly|  
|HL Mountain Seat Assembly|  
|...|  
  
## Навигация  
 Оператор навигации по связям позволяет переходить по связям от одной сущности \(исходный элемент\) к другой \(конечный элемент\).  Оператор [NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) принимает в качестве аргумента тип связи, заданный в формате \<пространство\_имен\>.\<имя\_типа\_связи\>.  Если количество элементов в конечной составляющей связи равно 1, оператор Navigate возвращает значение Ref\<T\>.  Если же количество элементов в конечной составляющей связи равно n, то будет возвращено значение Collection\<Ref\<T\>\>.  
  
 Пример  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 Результат  
  
|AddressID|  
|---------------|  
|1|  
|2|  
|3|  
|...|  
  
## SELECT VALUE и SELECT  
  
### SELECT VALUE  
 Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает предложение SELECT VALUE, позволяющее пропустить неявное построение строки.  В предложении SELECT VALUE может быть указан только один элемент.  При использовании такого предложения для элементов в предложении SELECT оболочка строк не создается, что позволяет получить коллекцию необходимой формы, например: `SELECT VALUE a`.  
  
 Пример  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 Результат  
  
|Имя|  
|---------|  
|Adjustable Race|  
|All\-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### SELECT  
 Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает также конструктор строк, позволяющий создавать произвольные строки.  Предложение SELECT принимает один или несколько элементов в проекции и возвращает запись данных с полями, например: `SELECT a, b, c`.  
  
 Пример  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:  
  
|Имя|ProductID|  
|---------|---------------|  
|Adjustable Race|1|  
|All\-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## Выражение варианта выбора  
 [Выражение варианта выбора](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) для определения результата вычисляет набор логических выражений.  
  
 Пример  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 Результат  
  
|Значение|  
|--------------|  
|TRUE|  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)