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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a262ab26c9bbb93e42a11217fbeea6b3c55c7eb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966267"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="03198-102">Метод ICLRErrorReportingManager::EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="03198-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="03198-103">Удаляет конфигурацию пользовательского дампа стека, которая была указана в предыдущем вызове метода [iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="03198-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03198-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03198-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="03198-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="03198-105">Return Value</span></span>  
  
|<span data-ttu-id="03198-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03198-106">HRESULT</span></span>|<span data-ttu-id="03198-107">Описание</span><span class="sxs-lookup"><span data-stu-id="03198-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03198-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="03198-108">S_OK</span></span>|<span data-ttu-id="03198-109">`EndCustomDump`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="03198-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="03198-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03198-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03198-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="03198-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="03198-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03198-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03198-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="03198-113">The call timed out.</span></span>|  
|<span data-ttu-id="03198-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03198-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03198-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="03198-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03198-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03198-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03198-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="03198-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03198-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03198-118">E_FAIL</span></span>|<span data-ttu-id="03198-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="03198-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03198-120">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="03198-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03198-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="03198-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03198-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="03198-122">Remarks</span></span>  
 <span data-ttu-id="03198-123">Метод очищает конфигурацию пользовательского дампа стека, заданную предыдущим вызовом `BeginCustomDump` метода, и освобождает любое связанное состояние. `EndCustomDump`</span><span class="sxs-lookup"><span data-stu-id="03198-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="03198-124">Он должен вызываться после завершения создания пользовательского дампа стека.</span><span class="sxs-lookup"><span data-stu-id="03198-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="03198-125">Сбой вызова `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="03198-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03198-126">Требования</span><span class="sxs-lookup"><span data-stu-id="03198-126">Requirements</span></span>  
 <span data-ttu-id="03198-127">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03198-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03198-128">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="03198-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03198-129">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="03198-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03198-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03198-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03198-131">См. также</span><span class="sxs-lookup"><span data-stu-id="03198-131">See also</span></span>

- [<span data-ttu-id="03198-132">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="03198-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="03198-133">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="03198-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="03198-134">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="03198-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
