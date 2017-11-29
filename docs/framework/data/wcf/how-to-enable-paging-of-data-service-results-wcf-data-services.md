---
title: "Практическое руководство. Включение разбивки на страницы результатов службы данных (службы данных WCF)"
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
helpviewer_keywords: paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6bf267cdc4ab3ec3bdc82a3da52cef21ef1d6b2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="587c0-102">Практическое руководство. Включение разбивки на страницы результатов службы данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="587c0-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>
<span data-ttu-id="587c0-103">Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют ограничить количество сущностей, возвращаемых запросом службы данных.</span><span class="sxs-lookup"><span data-stu-id="587c0-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="587c0-104">Пределы разбиения на страницы определены в методе, который вызывается при инициализации службы, и могут устанавливаться отдельно для каждого набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="587c0-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="587c0-105">Если включена подкачка страниц, то последняя запись в канале содержит ссылку на следующую страницу данных.</span><span class="sxs-lookup"><span data-stu-id="587c0-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="587c0-106">Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="587c0-106">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="587c0-107">В этом разделе показывается, как изменить службу данных, чтобы включить разбиение на страницы возвращаемых `Customers` и наборов сущностей `Orders`.</span><span class="sxs-lookup"><span data-stu-id="587c0-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="587c0-108">В примере этого раздела используется образец службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="587c0-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="587c0-109">Эта служба создается после завершения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="587c0-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="587c0-110">Как включить разбиение на страницы возвращаемых клиентов и наборов сущностей Orders</span><span class="sxs-lookup"><span data-stu-id="587c0-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
-   <span data-ttu-id="587c0-111">В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="587c0-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="587c0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="587c0-112">See Also</span></span>  
 [<span data-ttu-id="587c0-113">Загрузка отложенного содержимого</span><span class="sxs-lookup"><span data-stu-id="587c0-113">Loading Deferred Content</span></span>](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 [<span data-ttu-id="587c0-114">Как: загрузка разбитых на страницы результатов</span><span class="sxs-lookup"><span data-stu-id="587c0-114">How to: Load Paged Results</span></span>](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
