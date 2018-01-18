---
title: WHERE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 11687b1218c61acde7a68bb8fc112e287e5e1c38
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
Предложение WHERE применяется непосредственно после [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) предложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Тип Boolean.  
  
## <a name="remarks"></a>Примечания  
 Предложение WHERE имеет такую же семантику, которая описана для [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]. Она ограничивает набор объектов, полученный выражением запроса, выбирая из исходной коллекции только те элементы, которые соответствуют условию.  
  
```  
select c from cs as c where e  
```  
  
 Выражение `e` должно иметь тип Boolean.  
  
 Предложение WHERE применяется непосредственно после предложения FROM, до выполнения любого группирования, упорядочения или проекции. Все имена элементов, определенные в предложении FROM, доступны в выражении предложения WHERE.  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Выражения запросов](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
