---
title: "Пользовательские функции (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Пользовательские функции (Entity SQL)
Entity SQL поддерживает вызов встроенных определяемых пользователем функций в запросе.  Можно определить эти встроенные функции с помощью запроса \(см. раздел [How to: Call a User\-Defined Function](http://msdn.microsoft.com/ru-ru/ad131b86-8b4e-4747-8605-d4fc64fb9d02)\) или как составляющую концептуальной модели \(см. раздел [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ru-ru/0dad7b8b-58f6-4271-b238-f34810d68e5f)\).  Функции концептуальной модели определяются как команда Entity SQL в элементе [DefiningExpression](http://msdn.microsoft.com/ru-ru/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) элемента [Function](http://msdn.microsoft.com/ru-ru/dc3beca7-55cf-4977-8db0-5064cdbab134) в концептуальной модели.  
  
 Entity SQL позволяет определить функции в самой команде запроса.  Оператор [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) определяет встроенные функции.  В одной команде можно задать несколько функций с одним и тем же именем при условии, что эти функции имеют уникальные сигнатуры.  Для получения дополнительной информации см. [Разрешение перегрузки функций](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## См. также  
 [Функции](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)