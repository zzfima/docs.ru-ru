---
title: Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63f5687787a9b0cdb30790b7e80e4160cdf413f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737248"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="df8d5-102">Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="df8d5-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="df8d5-103">Возвращает общее процессорное время, использованное всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="df8d5-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df8d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df8d5-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df8d5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df8d5-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="df8d5-106">[in] Идентификатор домена запрошенное приложение.</span><span class="sxs-lookup"><span data-stu-id="df8d5-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="df8d5-107">[out] Указатель на общее процессорное время, использованное всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="df8d5-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="df8d5-108">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="df8d5-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df8d5-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="df8d5-109">Return Value</span></span>  
  
|<span data-ttu-id="df8d5-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df8d5-110">HRESULT</span></span>|<span data-ttu-id="df8d5-111">Описание</span><span class="sxs-lookup"><span data-stu-id="df8d5-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df8d5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="df8d5-112">S_OK</span></span>|<span data-ttu-id="df8d5-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="df8d5-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="df8d5-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="df8d5-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="df8d5-115">Домен приложения был выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="df8d5-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="df8d5-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df8d5-116">E_FAIL</span></span>|<span data-ttu-id="df8d5-117">Отслеживание ресурсов домена приложения не включена.</span><span class="sxs-lookup"><span data-stu-id="df8d5-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="df8d5-118">- или -</span><span class="sxs-lookup"><span data-stu-id="df8d5-118">-or-</span></span><br /><br /> <span data-ttu-id="df8d5-119">Все прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="df8d5-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df8d5-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="df8d5-120">Remarks</span></span>  
 <span data-ttu-id="df8d5-121">Этот метод эквивалентен неуправляемых управляемых <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="df8d5-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df8d5-122">Требования</span><span class="sxs-lookup"><span data-stu-id="df8d5-122">Requirements</span></span>  
 <span data-ttu-id="df8d5-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df8d5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df8d5-124">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="df8d5-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="df8d5-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df8d5-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df8d5-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df8d5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df8d5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="df8d5-127">See also</span></span>
- [<span data-ttu-id="df8d5-128">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="df8d5-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="df8d5-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="df8d5-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="df8d5-130">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="df8d5-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="df8d5-131">Размещение</span><span class="sxs-lookup"><span data-stu-id="df8d5-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
