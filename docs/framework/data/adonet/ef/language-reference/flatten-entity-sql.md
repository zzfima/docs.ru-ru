---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 75463ed622ac969eb2690c4118861823479a2caa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="flatten-entity-sql"></a>FLATTEN (Entity SQL)
Преобразовывает коллекцию коллекций в плоскую коллекцию. Новая коллекция содержит все те же элементы, что и старая коллекция, но без структуры вложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a>Аргументы  
 `collection`  
 Любое допустимое выражение, которое возвращает коллекцию коллекций значений, предназначенных для сведения в плоскую коллекцию.  
  
## <a name="remarks"></a>Примечания  
 Оператор`FLATTEN` - это один из операторов работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. В разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов работы с наборами.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL используется оператор `FLATTEN` для преобразования коллекции коллекций в плоскую коллекцию. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
