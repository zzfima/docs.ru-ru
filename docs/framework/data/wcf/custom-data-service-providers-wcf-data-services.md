---
title: "Специализированные поставщики служб данных (службы WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7db780b97c1a7eadffbfa71f60be4afe590ccb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a><span data-ttu-id="638d8-102">Специализированные поставщики служб данных (службы WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="638d8-102">Custom Data Service Providers (WCF Data Services)</span></span>
<span data-ttu-id="638d8-103">Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включают набор поставщиков, которые позволяют определить модель данных на основе типов данных с поздним связыванием.</span><span class="sxs-lookup"><span data-stu-id="638d8-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] includes a set of providers that enables you to define a data model based on late-bound data types.</span></span>  
  
|<span data-ttu-id="638d8-104">Поставщик</span><span class="sxs-lookup"><span data-stu-id="638d8-104">Provider</span></span>|<span data-ttu-id="638d8-105">Описание</span><span class="sxs-lookup"><span data-stu-id="638d8-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="638d8-106">Поставщик метаданных</span><span class="sxs-lookup"><span data-stu-id="638d8-106">Metadata provider</span></span>|<span data-ttu-id="638d8-107">Это базовый специализированный поставщик служб данных, позволяющий определить специализированную модель данных во время выполнения путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.</span><span class="sxs-lookup"><span data-stu-id="638d8-107">This is the core custom data service provider that enables you to define a custom data model at runtime by implementing the <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interface.</span></span>|  
|<span data-ttu-id="638d8-108">Поставщик запросов</span><span class="sxs-lookup"><span data-stu-id="638d8-108">Query provider</span></span>|<span data-ttu-id="638d8-109">Этот поставщик позволяет выполнять запросы к специализированной модели данных, определенной при помощи интерфейса <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.</span><span class="sxs-lookup"><span data-stu-id="638d8-109">This provider enables you to execute queries against a custom data model that is defined by using the <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interface.</span></span> <span data-ttu-id="638d8-110">Поставщик запросов создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.</span><span class="sxs-lookup"><span data-stu-id="638d8-110">The query provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceQueryProvider> interface.</span></span>|  
|<span data-ttu-id="638d8-111">Поставщик обновлений</span><span class="sxs-lookup"><span data-stu-id="638d8-111">Update provider</span></span>|<span data-ttu-id="638d8-112">Этот поставщик позволяет производить обновления типов, предоставляемых специализированным поставщиком служб данных, а также управлять параллелизмом.</span><span class="sxs-lookup"><span data-stu-id="638d8-112">This provider enables you to make updates to types that are exposed in a custom data service provider and to manage concurrency.</span></span> <span data-ttu-id="638d8-113">Поставщик обновлений создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>.</span><span class="sxs-lookup"><span data-stu-id="638d8-113">An update provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> interface</span></span>|  
|<span data-ttu-id="638d8-114">Поставщик подкачки</span><span class="sxs-lookup"><span data-stu-id="638d8-114">Paging provider</span></span>|<span data-ttu-id="638d8-115">Этот поставщик используется вместе со специализированным поставщиком служб данных для поддержки подкачки страниц на сервере.</span><span class="sxs-lookup"><span data-stu-id="638d8-115">This provider is used with the custom data service provider to enable server-driven paging support.</span></span> <span data-ttu-id="638d8-116">Поставщик подкачки для специализированной службы данных создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServicePagingProvider>.</span><span class="sxs-lookup"><span data-stu-id="638d8-116">A paging provider for a custom data service is created by implementing the <xref:System.Data.Services.Providers.IDataServicePagingProvider> interface.</span></span>|  
|<span data-ttu-id="638d8-117">Потоковый поставщик</span><span class="sxs-lookup"><span data-stu-id="638d8-117">Streaming provider</span></span>|<span data-ttu-id="638d8-118">Этот поставщик позволяет предоставлять данные больших двоичных объектов в виде потока.</span><span class="sxs-lookup"><span data-stu-id="638d8-118">This provider enables you to expose binary large object data types as a stream.</span></span> <span data-ttu-id="638d8-119">Потоковый поставщик создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.</span><span class="sxs-lookup"><span data-stu-id="638d8-119">A streaming provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceStreamProvider> interface.</span></span> <span data-ttu-id="638d8-120">Поставщик потока также может использоваться вместе с платформой Entity Framework и поставщиками отражений источников данных.</span><span class="sxs-lookup"><span data-stu-id="638d8-120">The streaming provider can also be used with Entity Framework and reflection data source providers.</span></span> <span data-ttu-id="638d8-121">Дополнительные сведения см. в разделе [потокового поставщика](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="638d8-121">For more information, see [Streaming Provider](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).</span></span>|  
  
 <span data-ttu-id="638d8-122">Дополнительные сведения см. в статье [настраиваемых поставщиков данных](http://go.microsoft.com/fwlink/?LinkID=186850) и [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Provider Toolkit in [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).</span><span class="sxs-lookup"><span data-stu-id="638d8-122">For more information, see the article [Custom Data Service Providers](http://go.microsoft.com/fwlink/?LinkID=186850) and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Provider Toolkit in the [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638d8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="638d8-123">See Also</span></span>  
 [<span data-ttu-id="638d8-124">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="638d8-124">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="638d8-125">Поставщик Entity Framework</span><span class="sxs-lookup"><span data-stu-id="638d8-125">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [<span data-ttu-id="638d8-126">Поставщик отражений</span><span class="sxs-lookup"><span data-stu-id="638d8-126">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
