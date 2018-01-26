---
title: HAVING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bfa8b49b486b2bc20009874562c42ec92aa538d1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="having-entity-sql"></a>HAVING (Entity SQL)
Задает условие поиска для группы или статистического выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a>Аргументы  
 `search_condition`  
 Определяет условие поиска, которому должна соответствовать группа или статистическое выражение. Если предложение HAVING используется в сочетании с GROUP BY ALL, то оно переопределяет ALL.  
  
## <a name="remarks"></a>Примечания  
 Предложение HAVING позволяет указать дополнительное условие фильтрации для результатов группирования. Если в выражении запроса не указано предложение GROUP BY, то предполагается неявным образом созданная группа, состоящая из одного набора.  
  
> [!NOTE]
>  Предложение HAVING можно использовать только с [ВЫБЕРИТЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) инструкции. Когда [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) — не используется, HAVING работает так же как и предложение WHERE.  
  
 Предложение HAVING работает точно так же, как и предложение WHERE, за исключением того, что применяется после операции GROUP BY. Это означает, что предложение HAVING может ссылаться только на псевдонимы и статистические выражения группирования, как показано в следующем примере.  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 Предыдущий пример производится ограничение до тех групп, которые содержат более одного товара.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL операторы HAVING и GROUP BY задают условие поиска для группы или статистического выражения. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Выражения запросов](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
