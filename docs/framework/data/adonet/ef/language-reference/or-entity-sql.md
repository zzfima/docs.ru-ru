---
title: '|| (ИЛИ) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: c88e041638fbe6f32717ce9c4f9c2ff6fb56d803
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249764"
---
# <a name="-or-entity-sql"></a>|| (ИЛИ) (Entity SQL)
Объединяет два выражения типа `Boolean` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `boolean_expression`  
 Любое допустимое выражение, возвращающее значение типа `Boolean`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` , если любое из условий есть `true`; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 OR - это логический оператор [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Он используется только для объединения двух условий. Если в инструкции используется более одного логического оператора, операторы OR вычисляются после операторов AND. Однако порядок выполнения можно изменить с помощью скобок.  
  
 Двойные вертикальные&#124;&#124;черты () имеют те же функциональные возможности, что и оператор OR.  
  
 В следующей таблице указаны возможные входные значения и возвращаемые типы.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL использует оператор OR, чтобы объединить два выражения типа `Boolean` . Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
