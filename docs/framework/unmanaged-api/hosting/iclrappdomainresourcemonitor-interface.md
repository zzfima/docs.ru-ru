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
ms.openlocfilehash: 208d567aa5c19ddcf8bf9b13b452cb4fc48c976f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126768"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="ad210-102">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="ad210-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="ad210-103">Предоставляет методы для проверки использования памяти и ЦП домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ad210-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad210-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ad210-104">Methods</span></span>  
  
|<span data-ttu-id="ad210-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ad210-105">Method</span></span>|<span data-ttu-id="ad210-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ad210-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad210-107">Метод GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="ad210-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="ad210-108">Возвращает общий размер (в байтах) всех выделений памяти, сделанных доменом приложения с момента его создания, без вычитания памяти, которая была собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="ad210-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="ad210-109">Метод GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="ad210-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="ad210-110">Возвращает число байтов, сохранившихся последней полной блокирующей сборки мусора, на которые ссылается текущий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="ad210-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="ad210-111">Метод GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="ad210-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="ad210-112">Возвращает общее время процессора, которое использовалось всеми потоками во время выполнения в текущем домене приложения, так как был создан домен приложения.</span><span class="sxs-lookup"><span data-stu-id="ad210-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad210-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="ad210-113">Remarks</span></span>  
 <span data-ttu-id="ad210-114">Интерфейс `ICLRAppDomainResourceMonitor` предоставляет функциональные возможности, аналогичные следующим управляемым свойствам:</span><span class="sxs-lookup"><span data-stu-id="ad210-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="ad210-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ad210-115">Requirements</span></span>  
 <span data-ttu-id="ad210-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad210-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad210-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="ad210-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ad210-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ad210-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad210-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad210-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad210-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ad210-120">See also</span></span>

- [<span data-ttu-id="ad210-121">\<Аппдомаинресаурцемониторинг > элемент</span><span class="sxs-lookup"><span data-stu-id="ad210-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="ad210-122">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="ad210-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="ad210-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ad210-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ad210-124">Размещение</span><span class="sxs-lookup"><span data-stu-id="ad210-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
