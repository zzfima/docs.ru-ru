---
title: '|| (ИЛИ) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b44934aa0db73f872f0ab27a4c36c5c615855de1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="-or-entity-sql"></a>|| (ИЛИ) (Entity SQL)
Объединяет два выражения типа `Boolean` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `boolean_expression`  
 Любое допустимое выражение, возвращающее значение типа `Boolean`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` , если любое из условий есть `true`; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 OR - это логический оператор [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Он используется только для объединения двух условий. Если в инструкции используется более одного логического оператора, операторы OR вычисляются после операторов AND. Однако порядок выполнения можно изменить с помощью скобок.  
  
 Двойная вертикальная черта (&#124; &#124;) имеет ту же функциональность, что и оператор OR.  
  
 В следующей таблице указаны возможные входные значения и возвращаемые типы.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL использует оператор OR, чтобы объединить два выражения типа `Boolean` . Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
