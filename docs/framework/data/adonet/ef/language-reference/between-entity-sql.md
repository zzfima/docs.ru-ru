---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 611e90f362bbc0eac521e1e1998fb85200169c19
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039949"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Определяет, находится ли значение выражения в указанном диапазоне. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] между выражениями имеет те же функциональные возможности, что и Transact-SQL между выражениями.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение для проверки на принадлежность диапазону в пределах от `begin_expression` до `end_expression`. Аргумент `expression` должен быть того же типа данных, что и аргументы `begin_expression` и `end_expression`.  
  
 `begin_expression`  
 Любое допустимое выражение. Аргумент `begin_expression` должен быть того же типа данных, что и аргументы `expression` и `end_expression`. Значение `begin_expression` должно быть меньше `end_expression`, иначе возвращаемое значение будет инвертировано.  
  
 `end_expression`  
 Любое допустимое выражение. Аргумент `end_expression` должен быть того же типа данных, что и аргументы `expression` и `begin_expression`.  
  
 NOT  
 Указывает, что результат оператора BETWEEN должен быть инвертирован.  
  
 AND  
 Играет роль местозаполнителя и указывает на то, что значение выражения `expression` должно находиться в пределах заданных значений аргументов `begin_expression` и `end_expression`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если аргумент `expression` находится в диапазоне между `begin_expression` и `end_expression`; в противном случае - значение `false`. Возвращает `null`, если `expression` равно `null` или если `begin_expression` или `end_expression` равно `null`.  
  
## <a name="remarks"></a>Заметки  
 Чтобы указать эксклюзивный диапазон, используйте операторы "больше" (>) и "меньше" (<), а не между ними.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор BETWEEN определяет, входит ли значение выражения в указанный диапазон. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
