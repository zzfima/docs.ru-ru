---
title: '- Деление (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 79fdbebc648daac4f695387d52d2a915383f99ca
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833892"
---
# <a name="-divide-entity-sql"></a>/ (деление) (Entity SQL)
Делит одно число на другое.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a>Аргументы  
 `dividend`  
 Подлежащее делению численное выражение. `dividend` - любое допустимое выражение с любым числовым типом данных.  
  
 `divisor`  
 Численное выражение для деления делимого. `divisor` - любое допустимое выражение с любым числовым типом данных.  
  
## <a name="result-types"></a>Типы результатов  
 Тип данных, который является результатом неявного повышения типов обоих аргументов. Дополнительные сведения о неявном повышении типа см. в разделе [System Type](type-system-entity-sql.md).  
  
## <a name="example"></a>Пример  
 Следующий Entity SQL запрос использует арифметический оператор/для деления одного числа на другое. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a>См. также:

- [Справочник по Entity SQL](entity-sql-reference.md)
