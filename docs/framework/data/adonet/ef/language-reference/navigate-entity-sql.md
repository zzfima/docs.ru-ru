---
title: NAVIGATE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c82149fb5d76ac7b95198ce2b29550eade54b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)
Производит переход по связи, установленной между сущностями.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a>Аргументы  
 `instance-expresssion`  
 Экземпляр сущности.  
  
 `relationship-type`  
 Имя типа связи из CSDL-файла. `relationship-type` Квалифицируется как \<пространство имен >.\< имя_типа_связи >.  
  
 `to`  
 Элемент связи.  
  
 `from`  
 Начало связи.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если количество элементов в конечной составляющей связи равно 1, то будет возвращено значение `Ref<T>`. Если же количество элементов в конечной составляющей связи равно n, то будет возвращено значение `Collection<Ref<T>>`.  
  
## <a name="remarks"></a>Примечания  
 Связи являются конструкция первого класса в модели [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] . Связи могут устанавливаться между двумя или несколькими типами сущностей, а пользователи могут переходить по связи от одного элемента (от одной сущности) к другому. `from` и `to` являются необязательными при том условии, что нет неоднозначности в разрешении имен в пределах связи.  
  
 Оператор NAVIGATE является допустимым в пространствах O и C.  
  
 Конструкция перехода имеет следующую общую форму.  
  
 navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )  
  
 Например:  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 Здесь OrderCustomer является значением параметра `relationship`, а Customer и Order являются элементами связи `to-end` (customer) и `from-end` (order). Если OrderCustomer был отношения n: 1, то типом результата выражения перехода будет Ref\<клиента >.  
  
 Для этого выражение существует следующая упрощенная форма.  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 Аналогичным образом в запросе следующей формы выражение перехода вернет значение Collection < Ref\<порядок >>.  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 Выражение экземпляра должно иметь тип сущности или ссылки.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор NAVIGATE используется для перехода по связи, заданной между типами сущностей Address и SalesOrderHeader. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Как: перейдите связи с помощью оператора Navigate](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
