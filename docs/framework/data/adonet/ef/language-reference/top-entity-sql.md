---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 25afda64aafcd5a97dee7ad4cee25b152ef55907
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764662"
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
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]  
  
## <a name="see-also"></a>См. также  
 [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
