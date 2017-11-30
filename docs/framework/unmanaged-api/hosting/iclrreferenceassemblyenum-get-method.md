---
title: "Метод ICLRReferenceAssemblyEnum::Get"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRReferenceAssemblyEnum.Get
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab64f7983b5825505421e7bfbcf6866004778a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="99c70-102">Метод ICLRReferenceAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="99c70-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="99c70-103">Возвращает удостоверение сборки с заданным индексом.</span><span class="sxs-lookup"><span data-stu-id="99c70-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99c70-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99c70-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99c70-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="99c70-106">[in] Отсчитываемый от нуля индекс удостоверение сборки для возврата.</span><span class="sxs-lookup"><span data-stu-id="99c70-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="99c70-107">[out] Буфер, содержащий данные идентификации сборки.</span><span class="sxs-lookup"><span data-stu-id="99c70-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="99c70-108">[in, out] Размер `pwzBuffer` буфера.</span><span class="sxs-lookup"><span data-stu-id="99c70-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99c70-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="99c70-109">Return Value</span></span>  
  
|<span data-ttu-id="99c70-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99c70-110">HRESULT</span></span>|<span data-ttu-id="99c70-111">Описание</span><span class="sxs-lookup"><span data-stu-id="99c70-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99c70-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="99c70-112">S_OK</span></span>|<span data-ttu-id="99c70-113">`Get`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="99c70-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="99c70-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="99c70-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="99c70-115">`pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="99c70-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="99c70-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="99c70-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="99c70-117">Перечисление не содержит несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="99c70-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="99c70-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99c70-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99c70-119">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="99c70-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99c70-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99c70-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99c70-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="99c70-121">The call timed out.</span></span>|  
|<span data-ttu-id="99c70-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99c70-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99c70-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="99c70-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99c70-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99c70-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99c70-125">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="99c70-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99c70-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99c70-126">E_FAIL</span></span>|<span data-ttu-id="99c70-127">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="99c70-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99c70-128">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="99c70-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99c70-129">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="99c70-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c70-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="99c70-130">Remarks</span></span>  
 <span data-ttu-id="99c70-131">`Get`обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="99c70-131">`Get` is typically called twice.</span></span> <span data-ttu-id="99c70-132">Первый вызов предоставляет значение null для `pwzBuffer`и задает `pcchBufferSize` соответствующие размеру `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="99c70-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="99c70-133">При втором вызове указывается подходящего размера `pwzBuffer`и содержит данные идентификации канонической сборки после завершения.</span><span class="sxs-lookup"><span data-stu-id="99c70-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99c70-134">Требования</span><span class="sxs-lookup"><span data-stu-id="99c70-134">Requirements</span></span>  
 <span data-ttu-id="99c70-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99c70-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99c70-136">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="99c70-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99c70-137">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99c70-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99c70-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99c70-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c70-139">См. также</span><span class="sxs-lookup"><span data-stu-id="99c70-139">See Also</span></span>  
 [<span data-ttu-id="99c70-140">ICLRAssemblyReferenceList-интерфейс</span><span class="sxs-lookup"><span data-stu-id="99c70-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="99c70-141">ICLRReferenceAssemblyEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="99c70-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
