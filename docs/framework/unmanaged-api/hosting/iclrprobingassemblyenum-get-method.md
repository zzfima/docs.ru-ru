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
ms.openlocfilehash: 909e18fe9086fa954ffc389ffe1c6fe49217d2f5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492456"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="1dea6-102">Метод ICLRProbingAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="1dea6-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="1dea6-103">Получает идентификатор сборки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="1dea6-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dea6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1dea6-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dea6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1dea6-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="1dea6-106">[in] Отсчитываемый от нуля индекс удостоверение сборки для возврата.</span><span class="sxs-lookup"><span data-stu-id="1dea6-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="1dea6-107">[out] Буфер, содержащий данные идентификации сборки.</span><span class="sxs-lookup"><span data-stu-id="1dea6-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="1dea6-108">[in, out] Размер `pwzBuffer` буфера.</span><span class="sxs-lookup"><span data-stu-id="1dea6-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1dea6-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1dea6-109">Return Value</span></span>  
  
|<span data-ttu-id="1dea6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1dea6-110">HRESULT</span></span>|<span data-ttu-id="1dea6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="1dea6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1dea6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1dea6-112">S_OK</span></span>|<span data-ttu-id="1dea6-113">`Get` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1dea6-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="1dea6-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="1dea6-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="1dea6-115">`pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="1dea6-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="1dea6-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="1dea6-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="1dea6-117">Перечисление содержит больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="1dea6-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="1dea6-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1dea6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1dea6-119">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1dea6-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1dea6-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1dea6-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1dea6-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="1dea6-121">The call timed out.</span></span>|  
|<span data-ttu-id="1dea6-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1dea6-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1dea6-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="1dea6-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1dea6-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1dea6-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1dea6-125">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="1dea6-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1dea6-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1dea6-126">E_FAIL</span></span>|<span data-ttu-id="1dea6-127">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="1dea6-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1dea6-128">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1dea6-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1dea6-129">Последующие вызовы для размещения методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1dea6-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dea6-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="1dea6-130">Remarks</span></span>  
 <span data-ttu-id="1dea6-131">Идентификация по индексу 0 является удостоверением, соответствующий архитектуре процессора.</span><span class="sxs-lookup"><span data-stu-id="1dea6-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="1dea6-132">Удостоверение с индексом 1 — сборка, нейтральная архитектуры для промежуточного языка Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="1dea6-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="1dea6-133">Идентификация по индексу 2 не содержат архитектура сведений.</span><span class="sxs-lookup"><span data-stu-id="1dea6-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="1dea6-134">`Get` обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="1dea6-134">`Get` is typically called twice.</span></span> <span data-ttu-id="1dea6-135">Первый вызов предоставляет значение null для `pwzBuffer`и задает `pcchBufferSize` для размером, подходящим для `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="1dea6-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="1dea6-136">При втором вызове указывается подходящего размера `pwzBuffer`и содержит данные идентификации канонической сборки после завершения.</span><span class="sxs-lookup"><span data-stu-id="1dea6-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dea6-137">Требования</span><span class="sxs-lookup"><span data-stu-id="1dea6-137">Requirements</span></span>  
 <span data-ttu-id="1dea6-138">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dea6-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dea6-139">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1dea6-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1dea6-140">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1dea6-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1dea6-141">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dea6-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dea6-142">См. также</span><span class="sxs-lookup"><span data-stu-id="1dea6-142">See also</span></span>
- [<span data-ttu-id="1dea6-143">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="1dea6-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="1dea6-144">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="1dea6-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
