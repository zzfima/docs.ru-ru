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
ms.openlocfilehash: 98eebd489792f57f7f98d3596d4f25be2e847441
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966282"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="fd015-102">Метод ICLRErrorReportingManager::BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="fd015-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="fd015-103">Задает конфигурацию дампов пользовательской кучи для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="fd015-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd015-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd015-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd015-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd015-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="fd015-106">окне Значение [екустомдумпфлавор](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) , указывающее тип дампа кучи, на основе которого создается дамп пользовательской кучи.</span><span class="sxs-lookup"><span data-stu-id="fd015-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="fd015-107">окне Длина `items` массива.</span><span class="sxs-lookup"><span data-stu-id="fd015-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="fd015-108">Если `dwFlavor` значение не DUMP_FLAVOR_Mini, `dwNumItems` должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="fd015-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="fd015-109">окне Массив экземпляров [кустомдумпитем](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) , указывающий элементы для добавления в мини-дамп.</span><span class="sxs-lookup"><span data-stu-id="fd015-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="fd015-110">Если `dwFlavor` значение не DUMP_FLAVOR_Mini, `items` должно быть равно null.</span><span class="sxs-lookup"><span data-stu-id="fd015-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="fd015-111">окне Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="fd015-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd015-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd015-112">Return Value</span></span>  
  
|<span data-ttu-id="fd015-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd015-113">HRESULT</span></span>|<span data-ttu-id="fd015-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fd015-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd015-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd015-115">S_OK</span></span>|<span data-ttu-id="fd015-116">Метод успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="fd015-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="fd015-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd015-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd015-118">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fd015-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd015-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd015-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd015-120">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fd015-120">The call timed out.</span></span>|  
|<span data-ttu-id="fd015-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd015-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd015-122">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fd015-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd015-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd015-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd015-124">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fd015-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd015-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd015-125">E_FAIL</span></span>|<span data-ttu-id="fd015-126">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fd015-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd015-127">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fd015-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd015-128">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd015-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd015-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd015-129">Remarks</span></span>  
 <span data-ttu-id="fd015-130">`BeginCustomDump` Метод задает конфигурацию дампа пользовательской кучи.</span><span class="sxs-lookup"><span data-stu-id="fd015-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="fd015-131">Метод [ендкустомдумп](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) очищает конфигурацию дампа пользовательской кучи и освобождает любое связанное состояние.</span><span class="sxs-lookup"><span data-stu-id="fd015-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="fd015-132">Он должен вызываться после завершения создания дампа пользовательской кучи.</span><span class="sxs-lookup"><span data-stu-id="fd015-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fd015-133">Сбой вызова `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="fd015-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd015-134">Требования</span><span class="sxs-lookup"><span data-stu-id="fd015-134">Requirements</span></span>  
 <span data-ttu-id="fd015-135">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd015-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd015-136">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd015-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd015-137">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fd015-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd015-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd015-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd015-139">См. также</span><span class="sxs-lookup"><span data-stu-id="fd015-139">See also</span></span>

- [<span data-ttu-id="fd015-140">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="fd015-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="fd015-141">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="fd015-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="fd015-142">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="fd015-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
