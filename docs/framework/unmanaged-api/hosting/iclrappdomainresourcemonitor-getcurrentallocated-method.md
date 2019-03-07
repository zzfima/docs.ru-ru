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
ms.openlocfilehash: 97b00ff01125e000dec7840f122ed0c69ec9878f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502546"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="20418-102">Метод ICLRAppDomainResourceMonitor::GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="20418-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="20418-103">Получает общий размер в байтах для всех операций выделения памяти, которые были внесены доменом приложения с момента его создания, без вычитания памяти, который был удален сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="20418-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20418-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20418-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20418-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="20418-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="20418-106">[in] Идентификатор домена запрошенное приложение.</span><span class="sxs-lookup"><span data-stu-id="20418-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="20418-107">[out] Указатель на общий размер всех операций выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="20418-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20418-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="20418-108">Return Value</span></span>  
 <span data-ttu-id="20418-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="20418-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="20418-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20418-110">HRESULT</span></span>|<span data-ttu-id="20418-111">Описание</span><span class="sxs-lookup"><span data-stu-id="20418-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20418-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="20418-112">S_OK</span></span>|<span data-ttu-id="20418-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="20418-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="20418-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="20418-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="20418-115">Домен приложения был выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="20418-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20418-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="20418-116">Remarks</span></span>  
 <span data-ttu-id="20418-117">Этот метод эквивалентен неуправляемых управляемых <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="20418-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20418-118">Требования</span><span class="sxs-lookup"><span data-stu-id="20418-118">Requirements</span></span>  
 <span data-ttu-id="20418-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20418-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20418-120">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="20418-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="20418-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20418-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20418-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20418-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20418-123">См. также</span><span class="sxs-lookup"><span data-stu-id="20418-123">See also</span></span>
- [<span data-ttu-id="20418-124">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="20418-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="20418-125">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="20418-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="20418-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="20418-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="20418-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="20418-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
