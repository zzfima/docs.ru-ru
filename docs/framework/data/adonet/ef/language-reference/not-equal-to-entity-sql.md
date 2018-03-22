---
title: '!= (не равно) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 237dae641c272260e37fa7757792247700784d17
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="-not-equal-to-entity-sql"></a>!= (не равно) (Entity SQL)
Сравнивает два выражения, чтобы определить, является ли значение левого выражения не равным значению правого выражения. Действие оператора != (не равно) эквивалентно действию оператора <>.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающих неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  
 `true` , если значение левого выражения не равно значению правого; в противном случае - `false`.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор != используется для сравнения двух выражений, чтобы определить, отличается ли значение левого выражения от значения правого. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
