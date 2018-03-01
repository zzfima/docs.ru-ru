---
title: "Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2781cfb1e23db02ab8192c78bd0a3e585ee28b2b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="d815e-102">Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="d815e-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="d815e-103">Возвращает общее процессорное время, использованное всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="d815e-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d815e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d815e-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d815e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d815e-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="d815e-106">[in] Идентификатор домена запрошенное приложение.</span><span class="sxs-lookup"><span data-stu-id="d815e-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="d815e-107">[out] Указатель на общее процессорное время, использованное всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="d815e-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="d815e-108">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="d815e-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d815e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d815e-109">Return Value</span></span>  
  
|<span data-ttu-id="d815e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d815e-110">HRESULT</span></span>|<span data-ttu-id="d815e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d815e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d815e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d815e-112">S_OK</span></span>|<span data-ttu-id="d815e-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="d815e-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="d815e-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="d815e-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="d815e-115">Домен приложения выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="d815e-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="d815e-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d815e-116">E_FAIL</span></span>|<span data-ttu-id="d815e-117">Отслеживание ресурсов домена приложения не включен.</span><span class="sxs-lookup"><span data-stu-id="d815e-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="d815e-118">- или -</span><span class="sxs-lookup"><span data-stu-id="d815e-118">-or-</span></span><br /><br /> <span data-ttu-id="d815e-119">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="d815e-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d815e-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="d815e-120">Remarks</span></span>  
 <span data-ttu-id="d815e-121">Этот метод эквивалентен неуправляемые управляемый <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="d815e-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d815e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="d815e-122">Requirements</span></span>  
 <span data-ttu-id="d815e-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d815e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d815e-124">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d815e-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d815e-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d815e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d815e-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d815e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d815e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d815e-127">See Also</span></span>  
 [<span data-ttu-id="d815e-128">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="d815e-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="d815e-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="d815e-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="d815e-130">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="d815e-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="d815e-131">Размещение</span><span class="sxs-lookup"><span data-stu-id="d815e-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
