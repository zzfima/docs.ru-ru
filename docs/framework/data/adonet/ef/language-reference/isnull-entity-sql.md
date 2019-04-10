---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: aaecce3ff74d64b8e07b31329ced5b5e581fca5b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295098"
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)
Определяет, имеет ли выражение запроса значение null.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение запроса. Не может быть коллекцией, содержать элементы коллекции или тип записи со свойствами типа коллекции.  
  
 NOT  
 Логически инвертирует результат EDM.Boolean для IS NULL.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` Если `expression` возвращает значение null, в противном случае — `false`.  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово `IS NULL` позволяет определить, имеет ли элемент внешнего соединения значение NULL.  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 Ключевое слово `IS NULL` позволяет определить, имеет ли элемент фактическое значение.  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 В следующей таблице показан эффект применения оператора `IS NULL` в различных конструкциях. Все исключения формируются на стороне клиента перед вызовом поставщика.  
  
|Шаблон|Поведение|  
|-------------|--------------|  
|null IS NULL|Возвращает `true`.|  
|TREAT (null AS EntityType) IS NULL|Возвращает `true`.|  
|TREAT (null AS ComplexType) IS NULL|Вызывает ошибку.|  
|TREAT (null AS RowType) IS NULL|Вызывает ошибку.|  
|EntityType IS NULL|Возвращает значение `true` или `false`.|  
|ComplexType IS NULL|Вызывает ошибку.|  
|RowType IS NULL|Вызывает ошибку.|  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запросе используется оператор IS NOT NULL, чтобы определить, если выражение запроса не равно null. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
