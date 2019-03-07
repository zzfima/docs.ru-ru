---
title: Метод ICLRErrorReportingManager::BeginCustomDump
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af752ae52956ae1d97fb14ec3b494effdaed35c9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496616"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="6b207-102">Метод ICLRErrorReportingManager::BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="6b207-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="6b207-103">Указывает конфигурацию пользовательских дампов кучи для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="6b207-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b207-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b207-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b207-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b207-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="6b207-106">[in] Объект [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) значение, указывающее тип дампа кучи, на которых можно создать дамп пользовательской кучи.</span><span class="sxs-lookup"><span data-stu-id="6b207-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="6b207-107">[in] Длина `items` массива.</span><span class="sxs-lookup"><span data-stu-id="6b207-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="6b207-108">Если `dwFlavor` не DUMP_FLAVOR_Mini, `dwNumItems` должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="6b207-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="6b207-109">[in] Массив [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) экземпляров, указав элементы для добавления мини-дампа.</span><span class="sxs-lookup"><span data-stu-id="6b207-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="6b207-110">Если `dwFlavor` не DUMP_FLAVOR_Mini, `items` должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="6b207-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="6b207-111">[in] Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="6b207-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b207-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6b207-112">Return Value</span></span>  
  
|<span data-ttu-id="6b207-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b207-113">HRESULT</span></span>|<span data-ttu-id="6b207-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6b207-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b207-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b207-115">S_OK</span></span>|<span data-ttu-id="6b207-116">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="6b207-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="6b207-117">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6b207-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6b207-118">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6b207-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6b207-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6b207-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6b207-120">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="6b207-120">The call timed out.</span></span>|  
|<span data-ttu-id="6b207-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b207-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6b207-122">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="6b207-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6b207-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6b207-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6b207-124">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="6b207-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6b207-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6b207-125">E_FAIL</span></span>|<span data-ttu-id="6b207-126">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="6b207-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6b207-127">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="6b207-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6b207-128">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6b207-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b207-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b207-129">Remarks</span></span>  
 <span data-ttu-id="6b207-130">`BeginCustomDump` Метод задает конфигурацию пользовательского дампа кучи.</span><span class="sxs-lookup"><span data-stu-id="6b207-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="6b207-131">[EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) метод очищает конфигурации дампов пользовательской кучи и освобождает все связанные состояния.</span><span class="sxs-lookup"><span data-stu-id="6b207-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="6b207-132">Он должен вызываться после завершения пользовательской кучи дампа.</span><span class="sxs-lookup"><span data-stu-id="6b207-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b207-133">Сбой при вызове `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="6b207-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b207-134">Требования</span><span class="sxs-lookup"><span data-stu-id="6b207-134">Requirements</span></span>  
 <span data-ttu-id="6b207-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b207-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b207-136">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6b207-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b207-137">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b207-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b207-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b207-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b207-139">См. также</span><span class="sxs-lookup"><span data-stu-id="6b207-139">See also</span></span>
- [<span data-ttu-id="6b207-140">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="6b207-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="6b207-141">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="6b207-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="6b207-142">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="6b207-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
