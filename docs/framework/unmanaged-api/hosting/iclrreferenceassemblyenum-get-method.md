---
title: Метод ICLRReferenceAssemblyEnum::Get
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a69e32d418478071f9b99a391e6bef9095d6f4ad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749918"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="e13e6-102">Метод ICLRReferenceAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="e13e6-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="e13e6-103">Получает идентификатор сборки с заданным индексом.</span><span class="sxs-lookup"><span data-stu-id="e13e6-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e13e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e13e6-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e13e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e13e6-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="e13e6-106">[in] Отсчитываемый от нуля индекс удостоверение сборки для возврата.</span><span class="sxs-lookup"><span data-stu-id="e13e6-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="e13e6-107">[out] Буфер, содержащий данные идентификации сборки.</span><span class="sxs-lookup"><span data-stu-id="e13e6-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="e13e6-108">[in, out] Размер `pwzBuffer` буфера.</span><span class="sxs-lookup"><span data-stu-id="e13e6-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e13e6-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e13e6-109">Return Value</span></span>  
  
|<span data-ttu-id="e13e6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e13e6-110">HRESULT</span></span>|<span data-ttu-id="e13e6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e13e6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e13e6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e13e6-112">S_OK</span></span>|<span data-ttu-id="e13e6-113">`Get` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e13e6-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="e13e6-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e13e6-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e13e6-115">`pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="e13e6-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="e13e6-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="e13e6-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="e13e6-117">Перечисление содержит больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="e13e6-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="e13e6-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e13e6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e13e6-119">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e13e6-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e13e6-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e13e6-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e13e6-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e13e6-121">The call timed out.</span></span>|  
|<span data-ttu-id="e13e6-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e13e6-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e13e6-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e13e6-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e13e6-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e13e6-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e13e6-125">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e13e6-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e13e6-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e13e6-126">E_FAIL</span></span>|<span data-ttu-id="e13e6-127">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e13e6-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e13e6-128">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e13e6-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e13e6-129">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e13e6-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e13e6-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="e13e6-130">Remarks</span></span>  
 <span data-ttu-id="e13e6-131">`Get` обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="e13e6-131">`Get` is typically called twice.</span></span> <span data-ttu-id="e13e6-132">Первый вызов предоставляет значение null для `pwzBuffer`и задает `pcchBufferSize` для размером, подходящим для `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="e13e6-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="e13e6-133">При втором вызове указывается подходящего размера `pwzBuffer`и содержит данные идентификации канонической сборки после завершения.</span><span class="sxs-lookup"><span data-stu-id="e13e6-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e13e6-134">Требования</span><span class="sxs-lookup"><span data-stu-id="e13e6-134">Requirements</span></span>  
 <span data-ttu-id="e13e6-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e13e6-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e13e6-136">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e13e6-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e13e6-137">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e13e6-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e13e6-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e13e6-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e13e6-139">См. также</span><span class="sxs-lookup"><span data-stu-id="e13e6-139">See also</span></span>

- [<span data-ttu-id="e13e6-140">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="e13e6-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e13e6-141">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="e13e6-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
