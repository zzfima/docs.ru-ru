---
title: + (Добавить)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: a3c41ef8cf393a4d1b1deb362d6a3614558a34ba
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339124"
---
# <a name="-add"></a>+ (сложение)
Складывает два числа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение с любым числовым типом данных.  
  
## <a name="result-types"></a>Типы результата  
 Тип данных, который является результатом неявного повышения типов обоих аргументов. Дополнительные сведения о неявном повышении уровня типов, см. в разделе [система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).  
  
## <a name="remarks"></a>Примечания  
 Для типов EDM.String сложение является объединением строк.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL арифметический оператор сложения (+) используется для сложения двух чисел. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Типы концептуальной модели (CSDL)](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
