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
ms.openlocfilehash: f19ac39737d08c10c23ce0bde03131f52b660cac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126814"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="8a4f9-102">Метод ICLRAppDomainResourceMonitor::GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="8a4f9-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="8a4f9-103">Возвращает общий размер (в байтах) всех выделений памяти, сделанных доменом приложения с момента его создания, без вычитания памяти, которая была собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="8a4f9-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a4f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a4f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a4f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a4f9-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="8a4f9-106">окне ИДЕНТИФИКАТОР запрошенного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8a4f9-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="8a4f9-107">заполняет Указатель на общий размер всех выделений памяти.</span><span class="sxs-lookup"><span data-stu-id="8a4f9-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a4f9-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8a4f9-108">Return Value</span></span>  
 <span data-ttu-id="8a4f9-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="8a4f9-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8a4f9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a4f9-110">HRESULT</span></span>|<span data-ttu-id="8a4f9-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8a4f9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a4f9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a4f9-112">S_OK</span></span>|<span data-ttu-id="8a4f9-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="8a4f9-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="8a4f9-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="8a4f9-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="8a4f9-115">Домен приложения был выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="8a4f9-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a4f9-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="8a4f9-116">Remarks</span></span>  
 <span data-ttu-id="8a4f9-117">Этот метод является неуправляемым эквивалентом управляемого свойства <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8a4f9-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a4f9-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8a4f9-118">Requirements</span></span>  
 <span data-ttu-id="8a4f9-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a4f9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a4f9-120">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="8a4f9-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8a4f9-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8a4f9-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a4f9-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a4f9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a4f9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8a4f9-123">See also</span></span>

- [<span data-ttu-id="8a4f9-124">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="8a4f9-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="8a4f9-125">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="8a4f9-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="8a4f9-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8a4f9-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="8a4f9-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="8a4f9-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
