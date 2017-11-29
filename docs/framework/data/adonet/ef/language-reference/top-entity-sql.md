---
title: TOP (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9b1d3d1b07a349ab1a5efb4a7c41f9b9b34fc55f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="top-entity-sql"></a>TOP (Entity SQL)
Предложение SELECT может иметь необязательное вложенное предложение TOP, которое следует за необязательным модификатором ALL/DISTINCT. Предложение TOP указывает, что в результатах запроса возвращается только набор первых строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ TOP (n) ]  
```  
  
## <a name="arguments"></a>Аргументы  
 `n`  
 Числовое выражение, указывающее количество строк, которые необходимо вернуть. `n` может быть одним числовым литералом или одним параметром.  
  
## <a name="remarks"></a>Примечания  
 Выражение TOP должно быть одним числовым литералом или одним параметром. При использовании постоянного литерала он должен поддерживать неявное повышение до Edm.Int64 (byte, int16, int32 и int64 или любой тип поставщика, который сопоставляется с типом, поддерживающим повышение до Edm.Int64), а его значение должно быть больше или равно нулю. В противном случае возникнет исключение. Если в качестве выражения используется параметр, то тип параметра также должен поддерживать неявное повышение до Edm.Int64, однако проверка фактического значения параметра во время компиляции проводиться не будет, поскольку значения параметров связываются в режиме позднего связывания.  
  
 Ниже приведен пример постоянного выражения TOP:  
  
 `select distinct top(10) c.a1, c.a2 from T as a`  
  
 Ниже приведен пример параметризованного выражения TOP:  
  
 `select distinct top(@topParam) c.a1, c.a2 from T as a`  
  
 Выражение TOP является недетерминированным, если запрос не отсортирован. При необходимости в детерминированном результате используйте вложенные предложения [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) и [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) в предложении [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) . Предложения TOP и SKIP/LIMIT являются взаимоисключающими.  
  
## <a name="example"></a>Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] для указания верхней строки, которую следует вернуть из результата запроса, используется выражение TOP. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]  
  
## <a name="see-also"></a>См. также  
 [ВЫБЕРИТЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [ПРОПУСТИТЬ](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [ОГРАНИЧЕНИЯ](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
