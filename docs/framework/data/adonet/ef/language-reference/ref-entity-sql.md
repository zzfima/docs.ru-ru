---
title: REF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 226a14daa706f6cf0481b752fa03dc95db3eff81
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
Возвращает ссылку на экземпляр сущности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение, результатом которого является экземпляр типа сущности.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на указанный экземпляр сущности.  
  
## <a name="remarks"></a>Примечания  
 Ссылка на сущность состоит из ключа сущности и имени набора сущности. На одном и том же типе сущности могут быть основаны разные наборы сущностей, поэтому какой-то конкретный ключ сущности может появляться в нескольких наборах сущностей. Но ссылка на сущность всегда является уникальной. Если входное выражение представляет сохраняемую сущность, то будет возвращена ссылка на эту сущность. Если входное выражение не является сохраняемой сущностью, то возвращается ссылка null.  
  
 Если доступ к свойству сущности производится через оператор получения свойства (.), то ссылка автоматически разыменовывается.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL используется оператор REF в целях получения ссылки для входного аргумента сущности. Тот же запрос разыменовывает ссылку, поскольку для доступа к свойству сущности Product используется оператор получения свойства (.). Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a>См. также  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Определения типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
