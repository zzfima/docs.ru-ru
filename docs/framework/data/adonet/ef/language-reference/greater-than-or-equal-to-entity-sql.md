---
title: '>= (Больше или равно) (язык Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 4b7b2aa7be0b978fb6b1317393fb3c6e9a87c621
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289020"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a>>= (больше или равно) (Entity SQL)
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
  
1.  Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a>См. также
- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
