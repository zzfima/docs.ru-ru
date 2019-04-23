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
ms.openlocfilehash: f5e14749c3596ad22a435a11f75c928110c434de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196610"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="9a30e-102">Метод ICLRErrorReportingManager::EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="9a30e-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="9a30e-103">Удаляет конфигурацию пользовательского дампа стека, указанное в вызове [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9a30e-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a30e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a30e-104">Syntax</span></span>  
  
```  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9a30e-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a30e-105">Return Value</span></span>  
  
|<span data-ttu-id="9a30e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a30e-106">HRESULT</span></span>|<span data-ttu-id="9a30e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9a30e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a30e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a30e-108">S_OK</span></span>|<span data-ttu-id="9a30e-109">`EndCustomDump` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="9a30e-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="9a30e-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a30e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a30e-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9a30e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a30e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a30e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a30e-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="9a30e-113">The call timed out.</span></span>|  
|<span data-ttu-id="9a30e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a30e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a30e-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="9a30e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a30e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a30e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a30e-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="9a30e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a30e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a30e-118">E_FAIL</span></span>|<span data-ttu-id="9a30e-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="9a30e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a30e-120">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="9a30e-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a30e-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9a30e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a30e-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a30e-122">Remarks</span></span>  
 <span data-ttu-id="9a30e-123">`EndCustomDump` Метод очищает конфигурацию пользовательского дампа стека задается предыдущими вызовами `BeginCustomDump` метода и освобождает все связанные состояния.</span><span class="sxs-lookup"><span data-stu-id="9a30e-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="9a30e-124">Он должен вызываться после завершения создания пользовательского дампа стека.</span><span class="sxs-lookup"><span data-stu-id="9a30e-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9a30e-125">Сбой при вызове `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="9a30e-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a30e-126">Требования</span><span class="sxs-lookup"><span data-stu-id="9a30e-126">Requirements</span></span>  
 <span data-ttu-id="9a30e-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a30e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a30e-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a30e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a30e-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a30e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a30e-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a30e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a30e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9a30e-131">See also</span></span>

- [<span data-ttu-id="9a30e-132">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="9a30e-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="9a30e-133">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="9a30e-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="9a30e-134">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="9a30e-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
