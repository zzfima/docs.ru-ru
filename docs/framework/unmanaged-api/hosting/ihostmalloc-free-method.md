---
title: Метод IHostMAlloc::Free
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
ms.openlocfilehash: f7ae4e4cbb757edea242c57720baeb70ced5c428
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192059"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="5ef5e-102">Метод IHostMAlloc::Free</span><span class="sxs-lookup"><span data-stu-id="5ef5e-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="5ef5e-103">Освобождает память, выделенную с помощью функции [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5ef5e-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef5e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ef5e-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ef5e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ef5e-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="5ef5e-106">окне Указатель на память, которую необходимо освободить.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ef5e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5ef5e-107">Return Value</span></span>  
  
|<span data-ttu-id="5ef5e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ef5e-108">HRESULT</span></span>|<span data-ttu-id="5ef5e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5ef5e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ef5e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ef5e-110">S_OK</span></span>|<span data-ttu-id="5ef5e-111">`Free` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="5ef5e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5ef5e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5ef5e-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5ef5e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5ef5e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5ef5e-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-115">The call timed out.</span></span>|  
|<span data-ttu-id="5ef5e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5ef5e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5ef5e-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5ef5e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5ef5e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5ef5e-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5ef5e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ef5e-120">E_FAIL</span></span>|<span data-ttu-id="5ef5e-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5ef5e-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5ef5e-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5ef5e-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="5ef5e-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="5ef5e-125">Предпринята попытка освободить память, которая не была выделена через узел.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ef5e-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="5ef5e-126">Remarks</span></span>  
 <span data-ttu-id="5ef5e-127">Если параметр `pMem` ссылается на область памяти, которая не была выделена с помощью вызова `Alloc`, узел должен вернуть HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="5ef5e-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ef5e-128">Требования</span><span class="sxs-lookup"><span data-stu-id="5ef5e-128">Requirements</span></span>  
 <span data-ttu-id="5ef5e-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ef5e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ef5e-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5ef5e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ef5e-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5ef5e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ef5e-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ef5e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef5e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5ef5e-133">See also</span></span>

- [<span data-ttu-id="5ef5e-134">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="5ef5e-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="5ef5e-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="5ef5e-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
