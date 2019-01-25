---
title: Метод ICLRProbingAssemblyEnum::Get
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54d0f4582805b140aafd5825e34c429992e9bbcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707743"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="47a43-102">Метод ICLRProbingAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="47a43-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="47a43-103">Получает идентификатор сборки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="47a43-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47a43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47a43-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47a43-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47a43-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="47a43-106">[in] Отсчитываемый от нуля индекс удостоверение сборки для возврата.</span><span class="sxs-lookup"><span data-stu-id="47a43-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="47a43-107">[out] Буфер, содержащий данные идентификации сборки.</span><span class="sxs-lookup"><span data-stu-id="47a43-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="47a43-108">[in, out] Размер `pwzBuffer` буфера.</span><span class="sxs-lookup"><span data-stu-id="47a43-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47a43-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47a43-109">Return Value</span></span>  
  
|<span data-ttu-id="47a43-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47a43-110">HRESULT</span></span>|<span data-ttu-id="47a43-111">Описание</span><span class="sxs-lookup"><span data-stu-id="47a43-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47a43-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="47a43-112">S_OK</span></span>|<span data-ttu-id="47a43-113">`Get` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="47a43-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="47a43-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="47a43-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="47a43-115">`pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="47a43-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="47a43-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="47a43-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="47a43-117">Перечисление содержит больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="47a43-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="47a43-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47a43-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47a43-119">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="47a43-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47a43-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47a43-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47a43-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="47a43-121">The call timed out.</span></span>|  
|<span data-ttu-id="47a43-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47a43-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47a43-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="47a43-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47a43-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47a43-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47a43-125">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="47a43-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47a43-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47a43-126">E_FAIL</span></span>|<span data-ttu-id="47a43-127">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="47a43-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47a43-128">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="47a43-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47a43-129">Последующие вызовы для размещения методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="47a43-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47a43-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="47a43-130">Remarks</span></span>  
 <span data-ttu-id="47a43-131">Идентификация по индексу 0 является удостоверением, соответствующий архитектуре процессора.</span><span class="sxs-lookup"><span data-stu-id="47a43-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="47a43-132">Удостоверение с индексом 1 — сборка, нейтральная архитектуры для промежуточного языка Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="47a43-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="47a43-133">Идентификация по индексу 2 не содержат архитектура сведений.</span><span class="sxs-lookup"><span data-stu-id="47a43-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="47a43-134">`Get` обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="47a43-134">`Get` is typically called twice.</span></span> <span data-ttu-id="47a43-135">Первый вызов предоставляет значение null для `pwzBuffer`и задает `pcchBufferSize` для размером, подходящим для `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="47a43-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="47a43-136">При втором вызове указывается подходящего размера `pwzBuffer`и содержит данные идентификации канонической сборки после завершения.</span><span class="sxs-lookup"><span data-stu-id="47a43-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47a43-137">Требования</span><span class="sxs-lookup"><span data-stu-id="47a43-137">Requirements</span></span>  
 <span data-ttu-id="47a43-138">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47a43-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47a43-139">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="47a43-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47a43-140">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47a43-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47a43-141">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47a43-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a43-142">См. также</span><span class="sxs-lookup"><span data-stu-id="47a43-142">See also</span></span>
- [<span data-ttu-id="47a43-143">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="47a43-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="47a43-144">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="47a43-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
