---
title: '- (Вычитание) (Язык entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 5ca2bc8cb34d99421962289930c26de84eaa68e2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="--subtract-entity-sql"></a>- (вычитание) (Entity SQL)
Вычитает одно число из другого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение с любым числовым типом данных.  
  
## <a name="result-types"></a>Типы результата  
 Тип данных, который является результатом неявного повышения типов обоих аргументов. Дополнительные сведения о неявном повышении уровня типов см. в разделе [системы типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL использует арифметический оператор вычитания (-) для вычитания одного числа из другого. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
