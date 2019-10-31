---
title: Метод ICLRErrorReportingManager::EndCustomDump
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
ms.openlocfilehash: 2acbe72377e4c5b291ab062fcb5faa6503bd7937
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129291"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="27cd6-102">Метод ICLRErrorReportingManager::EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="27cd6-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="27cd6-103">Удаляет конфигурацию пользовательского дампа стека, которая была указана в предыдущем вызове метода [iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="27cd6-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27cd6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27cd6-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="27cd6-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27cd6-105">Return Value</span></span>  
  
|<span data-ttu-id="27cd6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27cd6-106">HRESULT</span></span>|<span data-ttu-id="27cd6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="27cd6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27cd6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="27cd6-108">S_OK</span></span>|<span data-ttu-id="27cd6-109">`EndCustomDump` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="27cd6-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="27cd6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27cd6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27cd6-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="27cd6-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27cd6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27cd6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27cd6-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="27cd6-113">The call timed out.</span></span>|  
|<span data-ttu-id="27cd6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27cd6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27cd6-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="27cd6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27cd6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27cd6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27cd6-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="27cd6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27cd6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27cd6-118">E_FAIL</span></span>|<span data-ttu-id="27cd6-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="27cd6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27cd6-120">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="27cd6-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27cd6-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="27cd6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27cd6-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="27cd6-122">Remarks</span></span>  
 <span data-ttu-id="27cd6-123">Метод `EndCustomDump` очищает конфигурацию дампа пользовательского стека, заданную предыдущим вызовом метода `BeginCustomDump` и освобождает любое связанное состояние.</span><span class="sxs-lookup"><span data-stu-id="27cd6-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="27cd6-124">Он должен вызываться после завершения создания пользовательского дампа стека.</span><span class="sxs-lookup"><span data-stu-id="27cd6-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="27cd6-125">Сбой вызова `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="27cd6-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27cd6-126">Требования</span><span class="sxs-lookup"><span data-stu-id="27cd6-126">Requirements</span></span>  
 <span data-ttu-id="27cd6-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27cd6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27cd6-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="27cd6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27cd6-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="27cd6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27cd6-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27cd6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27cd6-131">См. также</span><span class="sxs-lookup"><span data-stu-id="27cd6-131">See also</span></span>

- [<span data-ttu-id="27cd6-132">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="27cd6-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="27cd6-133">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="27cd6-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="27cd6-134">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="27cd6-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
