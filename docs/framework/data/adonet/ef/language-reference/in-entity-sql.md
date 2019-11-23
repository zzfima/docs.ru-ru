---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: e46db63600b6baa03697615a2f5eb9240f55d15e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833697"
---
# <a name="in-entity-sql"></a>IN (Entity SQL)
Определяет, совпадает ли значение с каким-либо значением в коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `value`  
 Любое допустимое выражение, возвращающее значение для сопоставления.  
  
 [ NOT ]  
 Указывает, что значение `Boolean` оператора IN следует инвертировать.  
  
 `expression`  
 Любое допустимое выражение, возвращающее коллекцию для проверки соответствия. Все выражения должны иметь тот же тип, что и аргумент `value`, или принадлежать к базовому или производному типу для типа этого аргумента.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`, если значение найдено в коллекции; значение null, если значение равно null или коллекция имеет значение null; в противном случае `false`. Использование NOT IN логически инвертирует результат IN.  
  
## <a name="example"></a>Пример  
 В следующем запросе на языке Entity SQL оператор IN используется для определения, совпадает ли значение с каким-либо значением в коллекции. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>См. также:

- [Справочник по Entity SQL](entity-sql-reference.md)
