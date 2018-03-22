---
title: '! (NOT) (язык Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: f3786724280cc077574f37e4d373c85faf5340f3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="-not-entity-sql"></a>! (NOT) (язык Entity SQL)
Изменяет значение выражения типа `Boolean` на обратное.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `boolean_expression`  
 Любое допустимое выражение, возвращающее значение типа Boolean.  
  
## <a name="remarks"></a>Примечания  
 Восклицательный знак (!) имеет ту же функциональность, что и оператор NOT.  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL использует оператор NOT, чтобы изменить на обратное выражение типа `Boolean` . Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
