---
title: Метод ICLRAppDomainResourceMonitor::GetCurrentSurvived
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a24f51884b5dc55e45d22f33735fe07db770d06
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466925"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="59001-102">Метод ICLRAppDomainResourceMonitor::GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="59001-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="59001-103">Получает количество байтов, оставшихся после последнего полного блокирующего сбора мусора и которые ссылается текущий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="59001-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59001-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59001-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59001-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="59001-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="59001-106">[in] Идентификатор домена запрошенное приложение.</span><span class="sxs-lookup"><span data-stu-id="59001-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="59001-107">[out] Указатель на число байтов, оставшихся после последней сборки мусора, содержащихся в этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="59001-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="59001-108">После полной сборки мусора это число является точным и полным.</span><span class="sxs-lookup"><span data-stu-id="59001-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="59001-109">После эфемерной сборки это число является потенциально неполным.</span><span class="sxs-lookup"><span data-stu-id="59001-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="59001-110">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="59001-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="59001-111">[out] Указатель на общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="59001-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="59001-112">После полной сборки мусора это количество представляет собой число байтов, которые хранятся в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="59001-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="59001-113">После эфемерной сборки это количество представляет собой число байтов, которые хранятся в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="59001-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="59001-114">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="59001-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59001-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="59001-115">Return Value</span></span>  
 <span data-ttu-id="59001-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="59001-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="59001-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59001-117">HRESULT</span></span>|<span data-ttu-id="59001-118">Описание</span><span class="sxs-lookup"><span data-stu-id="59001-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59001-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="59001-119">S_OK</span></span>|<span data-ttu-id="59001-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="59001-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="59001-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="59001-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="59001-122">Домен приложения был выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="59001-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59001-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="59001-123">Remarks</span></span>  
 <span data-ttu-id="59001-124">Статистические данные обновляются только после полной блокирующей сборки мусора; то есть происходит коллекции, включающий в себя все поколения и который останавливает приложение при коллекции.</span><span class="sxs-lookup"><span data-stu-id="59001-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="59001-125">Например <xref:System.GC.Collect?displayProperty=nameWithType> перегрузку метода выполняет полного блокирующего сбора.</span><span class="sxs-lookup"><span data-stu-id="59001-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="59001-126">Параллельная сборка мусора происходит в фоновом режиме и не блокирует приложение.</span><span class="sxs-lookup"><span data-stu-id="59001-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="59001-127">`GetCurrentSurvived` Метод эквивалентен неуправляемых управляемых <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="59001-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59001-128">Требования</span><span class="sxs-lookup"><span data-stu-id="59001-128">Requirements</span></span>  
 <span data-ttu-id="59001-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59001-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59001-130">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="59001-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="59001-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59001-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59001-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59001-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59001-133">См. также</span><span class="sxs-lookup"><span data-stu-id="59001-133">See also</span></span>
- [<span data-ttu-id="59001-134">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="59001-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="59001-135">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="59001-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="59001-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="59001-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="59001-137">Размещение</span><span class="sxs-lookup"><span data-stu-id="59001-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
