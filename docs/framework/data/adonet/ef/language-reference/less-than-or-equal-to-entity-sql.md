---
title: < = (меньше или равно) (язык Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 9e5a61cb68895982344eadec083a697bdaff54e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193958"
---
# <a name="-less-than-or-equal-to-entity-sql"></a>\<= (меньше или равно) (Entity SQL)
Сравнивает два выражения и определяет, имеет ли левое выражение значение, меньшее или равное значению правого выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающих неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  
 `true` Если левое выражение значение, меньшее или равное значению правого выражения; в противном случае `false`.  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL использует оператор сравнения <= для сравнения двух выражений и определяет, имеет ли левое выражение значение, меньшее или равное значению правого выражения. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
