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
ms.openlocfilehash: 62fcdb60b83c88738ebe2e39455b8eae60fb705e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126782"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="9ac32-102">Метод ICLRAppDomainResourceMonitor::GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="9ac32-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="9ac32-103">Возвращает число байтов, сохранившихся последней полной блокирующей сборки мусора, на которые ссылается текущий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="9ac32-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ac32-104">Syntax</span></span>  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ac32-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ac32-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="9ac32-106">окне ИДЕНТИФИКАТОР запрошенного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9ac32-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="9ac32-107">заполняет Указатель на число байтов, сохранившихся после последней сборки мусора, удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="9ac32-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="9ac32-108">После полного сбора это число является точным и полным.</span><span class="sxs-lookup"><span data-stu-id="9ac32-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="9ac32-109">После эфемерной коллекции это число может быть неполным.</span><span class="sxs-lookup"><span data-stu-id="9ac32-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="9ac32-110">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="9ac32-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="9ac32-111">заполняет Указатель на общее число байтов, сохранившихся из последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="9ac32-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="9ac32-112">После полной сборки мусора это число представляет число байтов, хранящихся в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="9ac32-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="9ac32-113">После эфемерной коллекции это число представляет число байтов, которые удерживаются в режиме эфемерного поколения.</span><span class="sxs-lookup"><span data-stu-id="9ac32-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="9ac32-114">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="9ac32-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ac32-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9ac32-115">Return Value</span></span>  
 <span data-ttu-id="9ac32-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="9ac32-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9ac32-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ac32-117">HRESULT</span></span>|<span data-ttu-id="9ac32-118">Описание</span><span class="sxs-lookup"><span data-stu-id="9ac32-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ac32-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ac32-119">S_OK</span></span>|<span data-ttu-id="9ac32-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="9ac32-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="9ac32-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="9ac32-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="9ac32-122">Домен приложения был выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="9ac32-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ac32-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="9ac32-123">Remarks</span></span>  
 <span data-ttu-id="9ac32-124">Статистика обновляется только после полной блокированной сборки мусора; то есть коллекция, включающая все поколения и останавливающая работу приложения во время сбора.</span><span class="sxs-lookup"><span data-stu-id="9ac32-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="9ac32-125">Например, перегрузка метода <xref:System.GC.Collect?displayProperty=nameWithType> выполняет полную блокированную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="9ac32-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="9ac32-126">Параллельная сборка мусора выполняется в фоновом режиме и не блокирует приложение.</span><span class="sxs-lookup"><span data-stu-id="9ac32-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="9ac32-127">Метод `GetCurrentSurvived` является неуправляемым эквивалентом управляемого свойства <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9ac32-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ac32-128">Требования</span><span class="sxs-lookup"><span data-stu-id="9ac32-128">Requirements</span></span>  
 <span data-ttu-id="9ac32-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ac32-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ac32-130">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="9ac32-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9ac32-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9ac32-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ac32-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ac32-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac32-133">См. также</span><span class="sxs-lookup"><span data-stu-id="9ac32-133">See also</span></span>

- [<span data-ttu-id="9ac32-134">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="9ac32-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="9ac32-135">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="9ac32-135">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="9ac32-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9ac32-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9ac32-137">Размещение</span><span class="sxs-lookup"><span data-stu-id="9ac32-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
