---
title: "Как создать службу данных с помощью поставщика отражения (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы WCF Data Services, поставщики"
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как создать службу данных с помощью поставщика отражения (службы WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет определить модель данных на основе произвольных классов, если они предоставляются как объекты, реализующие интерфейс <xref:System.Linq.IQueryable%601>.  Для получения дополнительной информации см. [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
## Пример  
 Следующий пример определяет модель данных, включающую сущности `Orders` и `Items`.  Класс контейнера сущностей `OrderItemData` имеет два публичных метода, которые возвращают интерфейсы <xref:System.Linq.IQueryable%601>.  Эти интерфейсы являются наборами сущностей типа `Orders` и типами сущностей `Items`.  Сущность `Order` может включать несколько сущностей `Items`, поэтому тип сущности `Orders` имеет свойство навигации `Items`, возвращающее коллекцию объектов `Items`.  Класс контейнера сущностей `OrderItemData` является универсальным типом класса <xref:System.Data.Services.DataService%601>, производным которого является класс `OrderItems` службы данных.  
  
> [!NOTE]
>  Поскольку пример демонстрирует поставщика данных в памяти и изменения не сохраняются за пределами текущих экземпляров объектов, реализация интерфейса <xref:System.Data.Services.IUpdatable> не приносит никаких выгод.  Пример реализации интерфейса <xref:System.Data.Services.IUpdatable> см. в разделе [Как создать службу данных с помощью источника данных LINQ to SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## См. также  
 [Как создать службу данных с помощью источника данных LINQ to SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)   
 [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Как создать службу данных с использованием источника данных ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)