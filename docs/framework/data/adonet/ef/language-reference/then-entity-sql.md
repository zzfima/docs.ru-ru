---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ba01a978c53b58f7e6c1ac9bc42a97277ac64bbc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319286"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Результат предложения WHEN, если оно оценивается как значение `true`.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `when_expression`  
 Любое допустимое выражение типа Boolean.  
  
 `then_expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию.  
  
## <a name="remarks"></a>Заметки  
 Если аргумент `when_expression` оценивается как значение `true`, результатом является соответствующее значение `then-expression`. Если не выполнено ни одно из условий предложения WHEN, оценивается выражение `else-expression` . Однако, если выражение `else-expression`отсутствует, результат равен NULL.  
  
 Пример см. в разделе [case](case-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL с помощью выражения CASE оценивается набор выражений типа `Boolean` . Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a>См. также

- [CASE](case-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
