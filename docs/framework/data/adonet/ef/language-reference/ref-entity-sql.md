---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 40a5afd7eb99dba7cae8fe14ed0a45213fda94a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149951"
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
Возвращает ссылку на экземпляр сущности.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение, результатом которого является экземпляр типа сущности.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на указанный экземпляр сущности.  
  
## <a name="remarks"></a>Remarks  
 Ссылка на сущность состоит из ключа сущности и имени набора сущности. На одном и том же типе сущности могут быть основаны разные наборы сущностей, поэтому какой-то конкретный ключ сущности может появляться в нескольких наборах сущностей. Но ссылка на сущность всегда является уникальной. Если входное выражение представляет сохраняемую сущность, то будет возвращена ссылка на эту сущность. Если входное выражение не является сохраняемой сущностью, то возвращается ссылка null.  
  
 Если доступ к свойству сущности производится через оператор получения свойства (.), то ссылка автоматически разыменовывается.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL используется оператор REF в целях получения ссылки для входного аргумента сущности. Тот же запрос разыменовывает ссылку, поскольку для доступа к свойству сущности Product используется оператор получения свойства (.). Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Следуйте процедуре в [Как: Выполнить запрос, который возвращает результаты PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a>См. также раздел

- [DEREF](deref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [Ключ](key-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
- [Определения типов](type-definitions-entity-sql.md)
