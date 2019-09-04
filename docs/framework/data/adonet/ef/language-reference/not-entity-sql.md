---
title: '! (NOT) (язык Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 4055d56d878b817fe88bb0dacb53ea39061bc4b2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249863"
---
# <a name="-not-entity-sql"></a>! (NOT) (язык Entity SQL)
Изменяет значение выражения типа `Boolean` на обратное.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `boolean_expression`  
 Любое допустимое выражение, возвращающее значение типа Boolean.  
  
## <a name="remarks"></a>Примечания  
 Восклицательный знак (!) имеет ту же функциональность, что и оператор NOT.  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL использует оператор NOT, чтобы изменить на обратное выражение типа `Boolean` . Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
