---
title: Практическое руководство. Создание службы данных с помощью поставщика отражения (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: fb40a60850739147b2bf0f15a3babfe1d0dfa486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965798"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="cd8e1-102">Практическое руководство. Создание службы данных с помощью поставщика отражения (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="cd8e1-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="cd8e1-103">позволяет определить модель данных на основе произвольных классов, если они предоставляются как объекты, реализующие интерфейс <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="cd8e1-103">enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="cd8e1-104">Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cd8e1-104">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd8e1-105">Пример</span><span class="sxs-lookup"><span data-stu-id="cd8e1-105">Example</span></span>  
 <span data-ttu-id="cd8e1-106">Следующий пример определяет модель данных, включающую сущности `Orders` и `Items`.</span><span class="sxs-lookup"><span data-stu-id="cd8e1-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="cd8e1-107">Класс контейнера сущностей `OrderItemData` имеет два публичных метода, которые возвращают интерфейсы <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="cd8e1-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="cd8e1-108">Эти интерфейсы являются наборами сущностей типа `Orders` и типами сущностей `Items`.</span><span class="sxs-lookup"><span data-stu-id="cd8e1-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="cd8e1-109">Сущность `Order` может включать несколько сущностей `Items`, поэтому тип сущности `Orders` имеет свойство навигации `Items`, возвращающее коллекцию объектов `Items`.</span><span class="sxs-lookup"><span data-stu-id="cd8e1-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="cd8e1-110">Класс контейнера сущностей `OrderItemData` является универсальным типом класса <xref:System.Data.Services.DataService%601>, производным которого является класс `OrderItems` службы данных.</span><span class="sxs-lookup"><span data-stu-id="cd8e1-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd8e1-111">Поскольку пример демонстрирует поставщика данных в памяти и изменения не сохраняются за пределами текущих экземпляров объектов, реализация интерфейса <xref:System.Data.Services.IUpdatable> не приносит никаких выгод.</span><span class="sxs-lookup"><span data-stu-id="cd8e1-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="cd8e1-112">Пример, в <xref:System.Data.Services.IUpdatable> котором реализуется интерфейс, см [. в разделе как Создание службы данных с помощью LINQ to SQL источника](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)данных.</span><span class="sxs-lookup"><span data-stu-id="cd8e1-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="cd8e1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cd8e1-113">See also</span></span>

- [<span data-ttu-id="cd8e1-114">Практическое руководство. Создание службы данных с помощью LINQ to SQL источника данных</span><span class="sxs-lookup"><span data-stu-id="cd8e1-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
- [<span data-ttu-id="cd8e1-115">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="cd8e1-115">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="cd8e1-116">Практическое руководство. Создание службы данных с помощью источника данных ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="cd8e1-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
