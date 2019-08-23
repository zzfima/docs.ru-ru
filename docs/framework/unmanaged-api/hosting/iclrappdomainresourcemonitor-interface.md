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
ms.openlocfilehash: 597381c8ab31e86a02f870a24f165676d200b66e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965017"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="4fcfa-102">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="4fcfa-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="4fcfa-103">Предоставляет методы для проверки использования памяти и ЦП домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4fcfa-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4fcfa-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4fcfa-104">Methods</span></span>  
  
|<span data-ttu-id="4fcfa-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4fcfa-105">Method</span></span>|<span data-ttu-id="4fcfa-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4fcfa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4fcfa-107">Метод GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="4fcfa-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="4fcfa-108">Возвращает общий размер (в байтах) всех выделений памяти, сделанных доменом приложения с момента его создания, без вычитания памяти, которая была собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="4fcfa-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="4fcfa-109">Метод GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="4fcfa-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="4fcfa-110">Возвращает число байтов, сохранившихся последней полной блокирующей сборки мусора, на которые ссылается текущий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="4fcfa-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="4fcfa-111">Метод GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="4fcfa-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="4fcfa-112">Возвращает общее время процессора, которое использовалось всеми потоками во время выполнения в текущем домене приложения, так как был создан домен приложения.</span><span class="sxs-lookup"><span data-stu-id="4fcfa-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fcfa-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="4fcfa-113">Remarks</span></span>  
 <span data-ttu-id="4fcfa-114">`ICLRAppDomainResourceMonitor` Интерфейс предоставляет функциональные возможности, аналогичные следующим управляемым свойствам:</span><span class="sxs-lookup"><span data-stu-id="4fcfa-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="4fcfa-115">Требования</span><span class="sxs-lookup"><span data-stu-id="4fcfa-115">Requirements</span></span>  
 <span data-ttu-id="4fcfa-116">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fcfa-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fcfa-117">**Заголовок.** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="4fcfa-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4fcfa-118">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4fcfa-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fcfa-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fcfa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcfa-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4fcfa-120">See also</span></span>

- [<span data-ttu-id="4fcfa-121">\<Элемент > Аппдомаинресаурцемониторинг</span><span class="sxs-lookup"><span data-stu-id="4fcfa-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="4fcfa-122">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="4fcfa-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="4fcfa-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4fcfa-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="4fcfa-124">Размещение</span><span class="sxs-lookup"><span data-stu-id="4fcfa-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
