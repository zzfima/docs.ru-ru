---
title: '>= (Больше или равно) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: fb97786687616ff92f0e4402c86aef02de2e70c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250871"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a>> = (больше или равно) (Entity SQL)
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
  
1. Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
