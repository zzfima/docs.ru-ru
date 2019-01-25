---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 0b9cf9bdb211a74acd8fc229c53f3565b48e5ddd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670580"
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
Предложение WHERE применяется непосредственно после [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) предложение.  
  
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
- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Выражения запросов](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
