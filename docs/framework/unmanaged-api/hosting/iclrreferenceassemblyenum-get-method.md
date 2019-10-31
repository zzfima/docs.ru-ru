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
ms.openlocfilehash: 8f479443e168c3fc7c627c3227e59f1e8b54f0e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120508"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="17d1b-102">Метод ICLRReferenceAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="17d1b-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="17d1b-103">Возвращает удостоверение сборки по заданному индексу.</span><span class="sxs-lookup"><span data-stu-id="17d1b-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17d1b-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17d1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="17d1b-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="17d1b-106">окне Отсчитываемый от нуля индекс возвращаемого удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="17d1b-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="17d1b-107">заполняет Буфер, содержащий данные удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="17d1b-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="17d1b-108">[вход, выход] Размер буфера `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="17d1b-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17d1b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="17d1b-109">Return Value</span></span>  
  
|<span data-ttu-id="17d1b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17d1b-110">HRESULT</span></span>|<span data-ttu-id="17d1b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="17d1b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17d1b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="17d1b-112">S_OK</span></span>|<span data-ttu-id="17d1b-113">`Get` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="17d1b-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="17d1b-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="17d1b-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="17d1b-115">`pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="17d1b-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="17d1b-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="17d1b-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="17d1b-117">Перечисление не содержит больше элементов.</span><span class="sxs-lookup"><span data-stu-id="17d1b-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="17d1b-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17d1b-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17d1b-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="17d1b-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="17d1b-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="17d1b-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="17d1b-121">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="17d1b-121">The call timed out.</span></span>|  
|<span data-ttu-id="17d1b-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="17d1b-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="17d1b-123">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="17d1b-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="17d1b-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="17d1b-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="17d1b-125">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="17d1b-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="17d1b-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17d1b-126">E_FAIL</span></span>|<span data-ttu-id="17d1b-127">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="17d1b-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="17d1b-128">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="17d1b-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="17d1b-129">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="17d1b-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17d1b-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="17d1b-130">Remarks</span></span>  
 <span data-ttu-id="17d1b-131">`Get` обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="17d1b-131">`Get` is typically called twice.</span></span> <span data-ttu-id="17d1b-132">Первый вызов предоставляет значение NULL для `pwzBuffer`и задает для `pcchBufferSize` размер, соответствующий `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="17d1b-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="17d1b-133">Второй вызов обеспечивает соответствующий размер `pwzBuffer`и содержит канонические данные удостоверений сборки после завершения.</span><span class="sxs-lookup"><span data-stu-id="17d1b-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17d1b-134">Требования</span><span class="sxs-lookup"><span data-stu-id="17d1b-134">Requirements</span></span>  
 <span data-ttu-id="17d1b-135">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17d1b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17d1b-136">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="17d1b-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17d1b-137">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="17d1b-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17d1b-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17d1b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d1b-139">См. также</span><span class="sxs-lookup"><span data-stu-id="17d1b-139">See also</span></span>

- [<span data-ttu-id="17d1b-140">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="17d1b-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="17d1b-141">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="17d1b-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
