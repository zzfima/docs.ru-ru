---
title: "Интерфейс ICLRAppDomainResourceMonitor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor
helpviewer_keywords: ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f2cb7fd41e3f5b192974d61ddd9cf2b5845690ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="5a4e6-102">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="5a4e6-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="5a4e6-103">Предоставляет методы, проверяющие домен приложения использование памяти и ЦП.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a4e6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5a4e6-104">Methods</span></span>  
  
|<span data-ttu-id="5a4e6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5a4e6-105">Method</span></span>|<span data-ttu-id="5a4e6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5a4e6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a4e6-107">Getcurrentallocated-метод</span><span class="sxs-lookup"><span data-stu-id="5a4e6-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="5a4e6-108">Возвращает общий размер в байтах для всех операций выделения памяти, которые были внесены в домене приложения с момента его создания, без вычитания памяти, которая была собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="5a4e6-109">Getcurrentsurvived-метод</span><span class="sxs-lookup"><span data-stu-id="5a4e6-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="5a4e6-110">Возвращает количество байтов, оставшихся после последней полной, блокирующей сборки мусора и которые ссылается текущий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="5a4e6-111">Getcurrentcputime-метод</span><span class="sxs-lookup"><span data-stu-id="5a4e6-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="5a4e6-112">Возвращает общее процессорное время, использованное всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a4e6-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a4e6-113">Remarks</span></span>  
 <span data-ttu-id="5a4e6-114">`ICLRAppDomainResourceMonitor` Интерфейс предоставляет функциональные возможности, схожие следующие управляемые свойства:</span><span class="sxs-lookup"><span data-stu-id="5a4e6-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
-   <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="5a4e6-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5a4e6-115">Requirements</span></span>  
 <span data-ttu-id="5a4e6-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a4e6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a4e6-117">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5a4e6-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5a4e6-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a4e6-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a4e6-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4e6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4e6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5a4e6-120">See Also</span></span>  
 [<span data-ttu-id="5a4e6-121">\<appDomainResourceMonitoring > элемент</span><span class="sxs-lookup"><span data-stu-id="5a4e6-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [<span data-ttu-id="5a4e6-122">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="5a4e6-122">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="5a4e6-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5a4e6-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="5a4e6-124">Размещение</span><span class="sxs-lookup"><span data-stu-id="5a4e6-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
