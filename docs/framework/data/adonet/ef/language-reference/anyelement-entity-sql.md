---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 4eea3d43ef6ae9ea91432ea277326526e5e91fbc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251333"
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)
Извлекает элемент из многозначной коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию, из которой извлекается элемент.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Единственный элемент коллекции или произвольный элемент, если в коллекции их несколько. Если коллекция пустая, возвращается значение `null`. Если `collection` является коллекцией типа `Collection<T>`, то `ANYELEMENT(collection)` является допустимым выражением, результатом которого является экземпляр типа `T`.  
  
## <a name="remarks"></a>Примечания  
 Оператор ANYELEMENT извлекает произвольный элемент из многозначной коллекции. Например, в следующем примере извлекается один элемент из набора `Customers`.  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a>Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор ANYELEMENT используется для извлечения элемента из многозначной коллекции. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Допускающие значения NULL структурированные типы](nullable-structured-types-entity-sql.md)
