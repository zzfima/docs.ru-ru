---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: 5f0bbb0cadd736d476077685e08ba1a03b9c4001
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762888"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Результат предложения WHEN, если оно оценивается как значение `true`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `when_expression`  
 Любое допустимое выражение типа Boolean.  
  
 `then_expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию.  
  
## <a name="remarks"></a>Примечания  
 Если аргумент `when_expression` оценивается как значение `true`, результатом является соответствующее значение `then-expression`. Если не выполнено ни одно из условий предложения WHEN, оценивается выражение `else-expression` . Однако, если выражение `else-expression`отсутствует, результат равен NULL.  
  
 Пример см. в разделе [случае](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL с помощью выражения CASE оценивается набор выражений типа `Boolean` . Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>См. также  
 [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
