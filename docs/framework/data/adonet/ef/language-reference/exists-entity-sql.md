---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 44f128a292b013fd3a3a80efdd2d10a63e3cfb07
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833840"
---
# <a name="exists-entity-sql"></a>EXISTS (Entity SQL)
Определяет, является ли коллекция пустой.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение, возвращающее коллекцию.  
  
 NOT  
 Указывает, что результат оператора EXISTS должен быть инвертирован.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`, если коллекция не пуста; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 EXISTS - это один из операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о приоритетах для операторов набора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] см. в разделе [except](except-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор EXISTS используется, чтобы определить, пуста ли коллекция. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a>См. также:

- [Справочник по Entity SQL](entity-sql-reference.md)
