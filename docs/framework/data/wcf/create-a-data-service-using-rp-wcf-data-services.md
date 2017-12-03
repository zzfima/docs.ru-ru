---
title: "Практическое руководство. Создание службы данных с использованием поставщика отражений (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11f01a88e1d276321384f00f3e103322ccaef339
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>Практическое руководство. Создание службы данных с использованием поставщика отражений (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет определить модель данных на основе произвольных классов, если они предоставляются как объекты, реализующие интерфейс <xref:System.Linq.IQueryable%601>. Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример определяет модель данных, включающую сущности `Orders` и `Items`. Класс контейнера сущностей `OrderItemData` имеет два публичных метода, которые возвращают интерфейсы <xref:System.Linq.IQueryable%601>. Эти интерфейсы являются наборами сущностей типа `Orders` и типами сущностей `Items`. Сущность `Order` может включать несколько сущностей `Items`, поэтому тип сущности `Orders` имеет свойство навигации `Items`, возвращающее коллекцию объектов `Items`. Класс контейнера сущностей `OrderItemData` является универсальным типом класса <xref:System.Data.Services.DataService%601>, производным которого является класс `OrderItems` службы данных.  
  
> [!NOTE]
>  Поскольку пример демонстрирует поставщика данных в памяти и изменения не сохраняются за пределами текущих экземпляров объектов, реализация интерфейса <xref:System.Data.Services.IUpdatable> не приносит никаких выгод. Например, который реализует <xref:System.Data.Services.IUpdatable> интерфейса см. в разделе [как: создание службы данных с помощью LINQ to SQL источника данных](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>См. также  
 [Как: создание службы данных с использованием LINQ к источнику данных SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)  
 [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Как: создание службы данных с использованием источника данных ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
