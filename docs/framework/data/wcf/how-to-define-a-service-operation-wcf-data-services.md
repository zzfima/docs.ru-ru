---
title: Практическое руководство. Определение операции службы (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: 88e9b20f3ecefbd39789dfbc942af3938a9a2117
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326402"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="064e3-102">Практическое руководство. Определение операции службы (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="064e3-102">How to: Define a Service Operation (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="064e3-103">предоставляют методы, определенные на сервере в качестве операций службы.</span><span class="sxs-lookup"><span data-stu-id="064e3-103">expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="064e3-104">Операции службы позволяют службе данных предоставить доступ через URI-адрес метода, который определен на сервере.</span><span class="sxs-lookup"><span data-stu-id="064e3-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="064e3-105">Чтобы определить операцию службы, примените [`WebGet]` или `[WebInvoke]` к методу атрибут.</span><span class="sxs-lookup"><span data-stu-id="064e3-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="064e3-106">Для поддержки операторов запросов операция службы должна возвращать <xref:System.Linq.IQueryable%601> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="064e3-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="064e3-107">Операции службы могут обращаться к базовому источнику данных через свойство <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> объекта <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="064e3-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="064e3-108">Дополнительные сведения см. в разделе [операций службы](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="064e3-108">For more information, see [Service Operations](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="064e3-109">Пример в этом разделе определяет операцию службы с именем `GetOrdersByCity`, возвращающую фильтрованный экземпляр <xref:System.Linq.IQueryable%601>`Orders` и связанные объекты `Order_Details`.</span><span class="sxs-lookup"><span data-stu-id="064e3-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="064e3-110">Пример обращается к экземпляру <xref:System.Data.Objects.ObjectContext>, являющемуся источником данных для образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="064e3-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="064e3-111">Эта служба создается после завершения [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="064e3-111">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="064e3-112">Определение операции службы в службе данных Northwind</span><span class="sxs-lookup"><span data-stu-id="064e3-112">To define a service operation in the Northwind data service</span></span>  
  
1. <span data-ttu-id="064e3-113">Откройте в проекте службы данных Northwind файл Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="064e3-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="064e3-114">Определите в классе `Northwind` метод операции службы с именем `GetOrdersByCity`, как показано дальше:</span><span class="sxs-lookup"><span data-stu-id="064e3-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3. <span data-ttu-id="064e3-115">Добавьте в метод `InitializeService` класса `Northwind` следующий код, разрешающий доступ к операции службы:</span><span class="sxs-lookup"><span data-stu-id="064e3-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="064e3-116">Запрос к операции службы GetOrdersByCity</span><span class="sxs-lookup"><span data-stu-id="064e3-116">To query the GetOrdersByCity service operation</span></span>  
  
-   <span data-ttu-id="064e3-117">Введите в веб-браузере один из следующих URI для вызова операции службы, определенной в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="064e3-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## <a name="example"></a><span data-ttu-id="064e3-118">Пример</span><span class="sxs-lookup"><span data-stu-id="064e3-118">Example</span></span>  
 <span data-ttu-id="064e3-119">В следующем примере реализована операция службы с именем `GetOrderByCity` в службе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="064e3-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="064e3-120">Эта операция использует ADO.NET Entity Framework для возвращения набора сущностей `Orders` и связанных объектов `Order_Details` в виде экземпляра <xref:System.Linq.IQueryable%601> на основе переданного названия города.</span><span class="sxs-lookup"><span data-stu-id="064e3-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="064e3-121">Операторы запросов поддерживаются для этой конечной точки операции службы, потому что метод возвращает экземпляр <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="064e3-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## <a name="see-also"></a><span data-ttu-id="064e3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="064e3-122">See also</span></span>

- [<span data-ttu-id="064e3-123">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="064e3-123">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
