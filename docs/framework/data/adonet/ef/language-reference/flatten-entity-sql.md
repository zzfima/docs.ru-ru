---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 84b846e3db86c664bc42363f3d983a1001f5c318
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833806"
---
# <a name="flatten-entity-sql"></a>FLATTEN (Entity SQL)
Преобразовывает коллекцию коллекций в плоскую коллекцию. Новая коллекция содержит все те же элементы, что и старая коллекция, но без структуры вложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a>Аргументы  
 `collection`  
 Любое допустимое выражение, которое возвращает коллекцию коллекций значений, предназначенных для сведения в плоскую коллекцию.  
  
## <a name="remarks"></a>Примечания  
 Оператор`FLATTEN` - это один из операторов работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Дополнительные сведения см. в разделе, [за исключением](except-entity-sql.md) сведений о приоритетах для операторов набора [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL используется оператор `FLATTEN` для преобразования коллекции коллекций в плоскую коллекцию. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a>См. также:

- [Справочник по Entity SQL](entity-sql-reference.md)
