---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 2c411fd7fcac9d98323d5fcfb1874f98bc664991
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225265"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Определяет, находится ли значение выражения в указанном диапазоне. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Выражение BETWEEN имеет ту же функциональность, что и выражение Transact-SQL BETWEEN.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение для проверки на принадлежность диапазону в пределах от `begin_expression` до `end_expression`. `expression` должен быть тот же тип, что и `begin_expression` и `end_expression`.  
  
 `begin_expression`  
 Любое допустимое выражение. `begin_expression` должен быть тот же тип, что и `expression` и `end_expression`. `begin_expression` должно быть меньше, чем `end_expression`, в противном случае возвращаемое значение будет инвертировано.  
  
 `end_expression`  
 Любое допустимое выражение. `end_expression` должен быть тот же тип, что и `expression` и `begin_expression`.  
  
 NOT  
 Указывает, что результат оператора BETWEEN должен быть инвертирован.  
  
 AND  
 Играет роль местозаполнителя и указывает на то, что значение выражения `expression` должно находиться в пределах заданных значений аргументов `begin_expression` и `end_expression`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` Если `expression` между диапазона, обозначенного `begin_expression` и `end_expression`; в противном случае `false`. `null` Если будет возвращаться `expression` — `null` или, если `begin_expression` или `end_expression` является `null`.  
  
## <a name="remarks"></a>Примечания  
 Для указания исключающего диапазона, используйте больше (>) и меньше, чем операторы (<) вместо BETWEEN.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор BETWEEN определяет, входит ли значение выражения в указанный диапазон. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
