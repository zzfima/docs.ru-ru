---
title: Краткий справочник по Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785259"
---
# <a name="entity-sql-quick-reference"></a>Краткий справочник по Entity SQL
В этом разделе содержится краткий справочник по запросам [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Запросы в этом разделе основаны на модели AdventureWorks Sales.  
  
## <a name="literals"></a>Литералы  
  
### <a name="string"></a>String  
 Существуют строковые литералы в Юникоде и не в Юникоде. Строки в Юникоде предваряются символом N. Например `N'hello'`.  
  
 Ниже приведен пример строкового литерала не в Юникоде:  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 Результат  
  
|Значение|  
|-----------|  
|hello|  
  
### <a name="datetime"></a>DateTime  
 В литералах DateTime обязательными являются и часть даты, и часть времени. Значения по умолчанию отсутствуют.  
  
 Пример  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 Результат  
  
|Значение|  
|-----------|  
|Понедельник, 25.12.06, 01:01:00|  
  
### <a name="integer"></a>Целое число  
 Целочисленные литералы могут иметь тип Int32 (123), UInt32 (123U), Int64 (123L) и UInt64 (123UL).  
  
 Пример  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 Результат  
  
|Значение|  
|-----------|  
|1|  
|2|  
|3|  
  
### <a name="other"></a>Другое  
 Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает и другие типы литералов - Guid, Binary, Float/Double, Decimal и `null`. Литералы NULL в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] считаются совместимыми с любым из других типов в концептуальной модели.  
  
## <a name="type-constructors"></a>Конструкторы типов  
  
### <a name="row"></a>ROW  
 [СТРОКИ](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) создает анонимные структурно типизированные (значение запись), как в: `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 Пример  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 Результат  
  
|ProductID|name|  
|---------------|----------|  
|1|Adjustable Race|  
|879|All-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### <a name="multiset"></a>MULTISET  
 [МУЛЬТИНАБОР](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) создает коллекции, такие как:  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 Пример  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 Результат  
  
|ProductID|name|ProductNumber|…|  
|---------------|----------|-------------------|-------|  
|842|Touring-Panniers, Large|PA-T100|…|  
  
### <a name="object"></a>Object  
 [С именем конструктор типа](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) конструкции (именованные) объекты, определяемые пользователем, такие как `person("abc", 12)`.  
  
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
|1|4911-403C-98|1|776|...|  
|2|4911-403C-98|3|777|...|  
|...|...|...|...|...|  
  
## <a name="references"></a>Ссылки  
  
### <a name="ref"></a>REF  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) создает ссылку на экземпляр типа сущности. Например, следующий запрос возвращает ссылки на каждую сущность Order в наборе сущностей Orders:  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 Результат  
  
|Значение|  
|-----------|  
|1|  
|2|  
|3|  
|...|  
  
 В следующем примере оператор извлечения свойства (.) используется для доступа к свойству сущности. При использовании этого оператора автоматически выполняется разыменование ссылки.  
  
 Пример  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 Результат  
  
|Значение|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="deref"></a>DEREF  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) разыменовывает значение ссылки и выдает результат разыменования. Например, следующий запрос возвращает сущности Order для каждой из записей Order в наборе сущностей Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.  
  
 Пример  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 Результат  
  
|Значение|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="createref-and-key"></a>CREATEREF и KEY  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) создает ссылку, передавая ключ. [КЛЮЧ](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) извлекает ключевую часть выражения со ссылкой на тип.  
  
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
  
## <a name="functions"></a>Функции  
  
### <a name="canonical"></a>Канонические  
 Пространство имен для [канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) является модель Edm, как показано на `Edm.Length("string")`. Если не импортировано другое пространство имен, содержащее функцию, имя которой совпадает с именем канонической функции, то указывать пространство имен не обязательно. Если в двух пространствах имен имеется функция с тем же именем, то пользователь должен указать полное имя функции.  
  
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
  
### <a name="microsoft-provider-specific"></a>Функции поставщиков данных (Майкрософт)  
 [Функции поставщика Microsoft](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) в `SqlServer` пространства имен.  
  
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
  
## <a name="namespaces"></a>Пространства имен  
 [С помощью](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) задает пространства имен, используемые в выражении запроса.  
  
 Пример  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 Результат  
  
|Значение|  
|-----------|  
|aa|  
  
## <a name="paging"></a>Разбивка на страницы  
 Разбиение на страницы можно выразить, задав объявления [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) и [ограничение](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) вложенными предложениями для [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) предложение.  
  
 Пример  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 Результат  
  
|ID|name|  
|--------|----------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## <a name="grouping"></a>Группирование  
 [ГРУППИРОВАНИЕ по](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) определяет группы, в объекты, возвращаемые запросом ([ВЫБЕРИТЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) выражения должны быть помещены.  
  
 Пример  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 Результат  
  
|имя|  
|----------|  
|LL Mountain Seat Assembly|  
|ML Mountain Seat Assembly|  
|HL Mountain Seat Assembly|  
|...|  
  
## <a name="navigation"></a>Навигация  
 Оператор навигации по связям позволяет переходить по связям от одной сущности (исходный элемент) к другой (конечный элемент). [NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) принимает тип связи, заданный как \<пространства имен >.\< имя_типа_связи >. Перейдите возвращает значение Ref\<T > Если количество элементов равно 1. Если количество элементов равно n, коллекции < Ref\<T >> будут возвращены.  
  
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
  
## <a name="select-value-and-select"></a>SELECT VALUE и SELECT  
  
### <a name="select-value"></a>SELECT VALUE  
 Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает предложение SELECT VALUE, позволяющее пропустить неявное построение строки. В предложении SELECT VALUE может быть указан только один элемент. При использовании такого предложения для элементов, в предложении SELECT оболочка строк не создается и коллекцию необходимой формы могут быть созданы, например: `SELECT VALUE a`.  
  
 Пример  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 Результат  
  
|name|  
|----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="select"></a>SELECT  
 Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает также конструктор строк, позволяющий создавать произвольные строки. Предложение SELECT принимает один или несколько элементов в проекции и возвращает запись данных с полями, например: `SELECT a, b, c`.  
  
 Пример  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:  
  
|name|ProductID|  
|----------|---------------|  
|Adjustable Race|1|  
|All-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## <a name="case-expression"></a>Выражение варианта выбора  
 [Выражение case](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) вычисляет набор логических выражений для определения результата.  
  
 Пример  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 Результат  
  
|Значение|  
|-----------|  
|true|  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
