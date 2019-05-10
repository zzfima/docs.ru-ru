---
title: Интерфейс ICLRAppDomainResourceMonitor
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f336ac45e4bf5894c667412ff89acde4b9524c80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666070"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="2b7d7-102">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="2b7d7-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="2b7d7-103">Предоставляет методы, которые проверяют домен приложения использование памяти и ЦП.</span><span class="sxs-lookup"><span data-stu-id="2b7d7-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b7d7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2b7d7-104">Methods</span></span>  
  
|<span data-ttu-id="2b7d7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2b7d7-105">Method</span></span>|<span data-ttu-id="2b7d7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2b7d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b7d7-107">Метод GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="2b7d7-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="2b7d7-108">Получает общий размер в байтах для всех операций выделения памяти, которые были внесены доменом приложения с момента его создания, без вычитания памяти, который был удален сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="2b7d7-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="2b7d7-109">Метод GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="2b7d7-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="2b7d7-110">Получает количество байтов, оставшихся после последнего полного блокирующего сбора мусора и которые ссылается текущий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="2b7d7-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="2b7d7-111">Метод GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="2b7d7-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="2b7d7-112">Возвращает общее процессорное время, использованное всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2b7d7-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b7d7-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b7d7-113">Remarks</span></span>  
 <span data-ttu-id="2b7d7-114">`ICLRAppDomainResourceMonitor` Интерфейс предоставляет функциональность, аналогичную следующие управляемые свойства:</span><span class="sxs-lookup"><span data-stu-id="2b7d7-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="2b7d7-115">Требования</span><span class="sxs-lookup"><span data-stu-id="2b7d7-115">Requirements</span></span>  
 <span data-ttu-id="2b7d7-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b7d7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b7d7-117">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2b7d7-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2b7d7-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b7d7-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b7d7-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b7d7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7d7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2b7d7-120">See also</span></span>

- [<span data-ttu-id="2b7d7-121">\<appDomainResourceMonitoring > элемент</span><span class="sxs-lookup"><span data-stu-id="2b7d7-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="2b7d7-122">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="2b7d7-122">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="2b7d7-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="2b7d7-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2b7d7-124">Размещение</span><span class="sxs-lookup"><span data-stu-id="2b7d7-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
