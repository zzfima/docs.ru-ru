---
title: Как выполнить Создание службы данных с помощью поставщика отражения (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 723f4759f8f3f0152e08b46163545b833727d2d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691758"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="a96e7-102">Как выполнить Создание службы данных с помощью поставщика отражения (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="a96e7-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="a96e7-103">позволяет определить модель данных на основе произвольных классов, если они предоставляются как объекты, реализующие интерфейс <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="a96e7-103">enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="a96e7-104">Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a96e7-104">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a96e7-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a96e7-105">Example</span></span>  
 <span data-ttu-id="a96e7-106">Следующий пример определяет модель данных, включающую сущности `Orders` и `Items`.</span><span class="sxs-lookup"><span data-stu-id="a96e7-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="a96e7-107">Класс контейнера сущностей `OrderItemData` имеет два публичных метода, которые возвращают интерфейсы <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="a96e7-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="a96e7-108">Эти интерфейсы являются наборами сущностей типа `Orders` и типами сущностей `Items`.</span><span class="sxs-lookup"><span data-stu-id="a96e7-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="a96e7-109">Сущность `Order` может включать несколько сущностей `Items`, поэтому тип сущности `Orders` имеет свойство навигации `Items`, возвращающее коллекцию объектов `Items`.</span><span class="sxs-lookup"><span data-stu-id="a96e7-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="a96e7-110">Класс контейнера сущностей `OrderItemData` является универсальным типом класса <xref:System.Data.Services.DataService%601>, производным которого является класс `OrderItems` службы данных.</span><span class="sxs-lookup"><span data-stu-id="a96e7-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a96e7-111">Поскольку пример демонстрирует поставщика данных в памяти и изменения не сохраняются за пределами текущих экземпляров объектов, реализация интерфейса <xref:System.Data.Services.IUpdatable> не приносит никаких выгод.</span><span class="sxs-lookup"><span data-stu-id="a96e7-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="a96e7-112">Пример, который реализует <xref:System.Data.Services.IUpdatable> интерфейсом, см. в разделе [как: Создание службы данных с использованием LINQ к источнику данных SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="a96e7-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="a96e7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a96e7-113">See also</span></span>
- [<span data-ttu-id="a96e7-114">Практическое руководство. Создание службы данных с использованием LINQ к источнику данных SQL</span><span class="sxs-lookup"><span data-stu-id="a96e7-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
- [<span data-ttu-id="a96e7-115">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="a96e7-115">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="a96e7-116">Практическое руководство. Создание службы данных с использованием источника данных ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a96e7-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
