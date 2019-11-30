---
title: Практическое руководство. Создание службы данных с использованием поставщика отражений (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: cf20c1d27f22c0248217541763eaa617ed9493db
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569282"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>Практическое руководство. Создание службы данных с использованием поставщика отражений (службы данных WCF)
WCF Data Services позволяет определить модель данных, основанную на произвольных классах, если эти классы предоставляются как объекты, реализующие интерфейс <xref:System.Linq.IQueryable%601>. Дополнительные сведения см. в разделе [поставщики служб данных](data-services-providers-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример определяет модель данных, включающую сущности `Orders` и `Items`. Класс контейнера сущностей `OrderItemData` имеет два публичных метода, которые возвращают интерфейсы <xref:System.Linq.IQueryable%601>. Эти интерфейсы являются наборами сущностей типа `Orders` и типами сущностей `Items`. Сущность `Order` может включать несколько сущностей `Items`, поэтому тип сущности `Orders` имеет свойство навигации `Items`, возвращающее коллекцию объектов `Items`. Класс контейнера сущностей `OrderItemData` является универсальным типом класса <xref:System.Data.Services.DataService%601>, производным которого является класс `OrderItems` службы данных.  
  
> [!NOTE]
> Поскольку пример демонстрирует поставщика данных в памяти и изменения не сохраняются за пределами текущих экземпляров объектов, реализация интерфейса <xref:System.Data.Services.IUpdatable> не приносит никаких выгод. Пример, в котором реализуется интерфейс <xref:System.Data.Services.IUpdatable>, см. в разделе [инструкции. Создание службы данных с помощью LINQ to SQL источника данных](create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Создание службы данных с использованием источника данных LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md)
- [Поставщики служб данных](data-services-providers-wcf-data-services.md)
- [Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET](create-a-data-service-using-an-adonet-ef-data-wcf.md)
