---
title: '&gt;= (больше или равно) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 1a1b75991ab97eefec67f2499bad4beb2234ea61
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761991"
---
# <a name="gt-greater-than-or-equal-to-entity-sql"></a>&gt;= (больше или равно) (Entity SQL)
Сравнивает два выражения и определяет, имеет ли левое выражение значение, большее или равное значению правого выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающих неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  
 Значение`true` , если левое выражение больше или равно правому. В противном случае - значение `false`.  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL использует оператор сравнения >= для сравнения двух выражений и определяет, имеет ли левое выражение значение, большее или равное значению правого выражения. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
