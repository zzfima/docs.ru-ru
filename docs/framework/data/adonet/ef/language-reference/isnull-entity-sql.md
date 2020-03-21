---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: b3fc2484e80b637ed5841375985f7bae476bbbf7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150204"
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)
Определяет, имеет ли выражение запроса значение null.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение запроса. Не может быть коллекцией, содержать элементы коллекции или тип записи со свойствами типа коллекции.  
  
 NOT  
 Логически инвертирует результат EDM.Boolean для IS NULL.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если выражение `expression` возвращает значение NULL, либо значение `false` - в противном случае.  
  
## <a name="remarks"></a>Remarks  
 Ключевое слово `IS NULL` позволяет определить, имеет ли элемент внешнего соединения значение NULL.  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 Ключевое слово `IS NULL` позволяет определить, имеет ли элемент фактическое значение.  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 В следующей таблице показан эффект применения оператора `IS NULL` в различных конструкциях. Все исключения формируются на стороне клиента перед вызовом поставщика.  
  
|Модель|Поведение|  
|-------------|--------------|  
|null IS NULL|Возвращает `true`.|  
|TREAT (null AS EntityType) IS NULL|Возвращает `true`.|  
|TREAT (null AS ComplexType) IS NULL|Вызывает ошибку.|  
|TREAT (null AS RowType) IS NULL|Вызывает ошибку.|  
|EntityType IS NULL|Возвращает значение `true` или `false`.|  
|ComplexType IS NULL|Вызывает ошибку.|  
|RowType IS NULL|Вызывает ошибку.|  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] следующем запросе используется оператор IS NOT NULL для определения того, является ли выражение запроса недействительным. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
