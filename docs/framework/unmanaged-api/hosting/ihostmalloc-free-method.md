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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21342af13f9d77ebab979102172e1a2c28402273
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108060"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="277c3-102">Метод IHostMAlloc::Free</span><span class="sxs-lookup"><span data-stu-id="277c3-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="277c3-103">Освобождает память, выделенную с помощью [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) функции.</span><span class="sxs-lookup"><span data-stu-id="277c3-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="277c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="277c3-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="277c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="277c3-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="277c3-106">[in] Указатель на область памяти, который требуется освободить.</span><span class="sxs-lookup"><span data-stu-id="277c3-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="277c3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="277c3-107">Return Value</span></span>  
  
|<span data-ttu-id="277c3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="277c3-108">HRESULT</span></span>|<span data-ttu-id="277c3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="277c3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="277c3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="277c3-110">S_OK</span></span>|<span data-ttu-id="277c3-111">`Free` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="277c3-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="277c3-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="277c3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="277c3-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="277c3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="277c3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="277c3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="277c3-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="277c3-115">The call timed out.</span></span>|  
|<span data-ttu-id="277c3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="277c3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="277c3-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="277c3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="277c3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="277c3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="277c3-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="277c3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="277c3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="277c3-120">E_FAIL</span></span>|<span data-ttu-id="277c3-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="277c3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="277c3-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="277c3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="277c3-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="277c3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="277c3-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="277c3-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="277c3-125">Для освобождения памяти, который не был выделен через узел была предпринята.</span><span class="sxs-lookup"><span data-stu-id="277c3-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="277c3-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="277c3-126">Remarks</span></span>  
 <span data-ttu-id="277c3-127">Если `pMem` параметр ссылается на область памяти, который не был выделен с помощью вызова `Alloc`, основное приложение должно возвратить значение HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="277c3-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="277c3-128">Требования</span><span class="sxs-lookup"><span data-stu-id="277c3-128">Requirements</span></span>  
 <span data-ttu-id="277c3-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="277c3-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="277c3-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="277c3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="277c3-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="277c3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="277c3-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="277c3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277c3-133">См. также</span><span class="sxs-lookup"><span data-stu-id="277c3-133">See also</span></span>

- [<span data-ttu-id="277c3-134">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="277c3-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="277c3-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="277c3-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
