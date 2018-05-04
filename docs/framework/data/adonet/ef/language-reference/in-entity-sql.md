---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 1f3be5717c27a691e073cee46df757d0166fe78a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="in-entity-sql"></a>IN (Entity SQL)
Определяет, совпадает ли значение с каким-либо значением в коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 Значение `true`, если значение найдено в коллекции. Значение NULL, если параметр value имеет значение NULL или коллекция пуста. В противном случае - значение `false`. Использование NOT IN логически инвертирует результат IN.  
  
## <a name="example"></a>Пример  
 В следующем запросе на языке Entity SQL оператор IN используется для определения, совпадает ли значение с каким-либо значением в коллекции. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
