---
title: Метод ICLRAppDomainResourceMonitor::GetCurrentAllocated
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d02478c2421823ce2acb533d2abea2ea8b13c74
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950291"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="103b1-102">Метод ICLRAppDomainResourceMonitor::GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="103b1-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="103b1-103">Возвращает общий размер (в байтах) всех выделений памяти, сделанных доменом приложения с момента его создания, без вычитания памяти, которая была собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="103b1-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="103b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="103b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="103b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="103b1-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="103b1-106">окне ИДЕНТИФИКАТОР запрошенного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="103b1-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="103b1-107">заполняет Указатель на общий размер всех выделений памяти.</span><span class="sxs-lookup"><span data-stu-id="103b1-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="103b1-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="103b1-108">Return Value</span></span>  
 <span data-ttu-id="103b1-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="103b1-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="103b1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="103b1-110">HRESULT</span></span>|<span data-ttu-id="103b1-111">Описание</span><span class="sxs-lookup"><span data-stu-id="103b1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="103b1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="103b1-112">S_OK</span></span>|<span data-ttu-id="103b1-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="103b1-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="103b1-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="103b1-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="103b1-115">Домен приложения был выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="103b1-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="103b1-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="103b1-116">Remarks</span></span>  
 <span data-ttu-id="103b1-117">Этот метод является неуправляемым эквивалентом управляемого <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="103b1-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="103b1-118">Требования</span><span class="sxs-lookup"><span data-stu-id="103b1-118">Requirements</span></span>  
 <span data-ttu-id="103b1-119">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="103b1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="103b1-120">**Заголовок.** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="103b1-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="103b1-121">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="103b1-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="103b1-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="103b1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="103b1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="103b1-123">See also</span></span>

- [<span data-ttu-id="103b1-124">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="103b1-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="103b1-125">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="103b1-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="103b1-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="103b1-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="103b1-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="103b1-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
