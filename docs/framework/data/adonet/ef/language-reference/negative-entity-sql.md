---
title: "- (Отрицательное значение) (Язык entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2ceedd99221047ab73474ad5dc2478e527618b87
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="--negative-entity-sql"></a>- (отрицательное) (Entity SQL)
Возвращает значение числового выражения с противоположным знаком.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
- expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение с любым числовым типом данных.  
  
## <a name="result-types"></a>Типы результата  
 Тип данных `expression`.  
  
## <a name="remarks"></a>Примечания  
 Если аргумент `expression` имеет тип данных без знака, то типом результата становится тип данных со знаком, который в наибольшей степени связан с типом аргумента `expression`. Например, если аргумент `expression` имеет тип Byte, то возвращается значение типа Int16.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL используется арифметический оператор «-» для возврата значения числового выражения с противоположным знаком. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
