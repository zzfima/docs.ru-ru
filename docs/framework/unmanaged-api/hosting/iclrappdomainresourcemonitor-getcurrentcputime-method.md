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
ms.openlocfilehash: de57fec05c338e51d0691ccfa0d0bffb334848de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126788"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="e2701-102">Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="e2701-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="e2701-103">Возвращает общее время процессора, которое использовалось всеми потоками во время выполнения в текущем домене приложения, так как был создан домен приложения.</span><span class="sxs-lookup"><span data-stu-id="e2701-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2701-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2701-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2701-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2701-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="e2701-106">окне ИДЕНТИФИКАТОР запрошенного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e2701-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="e2701-107">заполняет Указатель на общее время процессора, которое использовалось всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e2701-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="e2701-108">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="e2701-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2701-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2701-109">Return Value</span></span>  
  
|<span data-ttu-id="e2701-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2701-110">HRESULT</span></span>|<span data-ttu-id="e2701-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e2701-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2701-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2701-112">S_OK</span></span>|<span data-ttu-id="e2701-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e2701-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="e2701-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="e2701-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="e2701-115">Домен приложения был выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="e2701-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="e2701-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2701-116">E_FAIL</span></span>|<span data-ttu-id="e2701-117">Отслеживание ресурсов домена приложений не включено.</span><span class="sxs-lookup"><span data-stu-id="e2701-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="e2701-118">\- или -</span><span class="sxs-lookup"><span data-stu-id="e2701-118">-or-</span></span><br /><br /> <span data-ttu-id="e2701-119">Все остальные сбои.</span><span class="sxs-lookup"><span data-stu-id="e2701-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2701-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="e2701-120">Remarks</span></span>  
 <span data-ttu-id="e2701-121">Этот метод является неуправляемым эквивалентом управляемого свойства <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2701-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2701-122">Требования</span><span class="sxs-lookup"><span data-stu-id="e2701-122">Requirements</span></span>  
 <span data-ttu-id="e2701-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2701-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2701-124">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="e2701-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e2701-125">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2701-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2701-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2701-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2701-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e2701-127">See also</span></span>

- [<span data-ttu-id="e2701-128">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="e2701-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="e2701-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e2701-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e2701-130">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="e2701-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="e2701-131">Размещение</span><span class="sxs-lookup"><span data-stu-id="e2701-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
