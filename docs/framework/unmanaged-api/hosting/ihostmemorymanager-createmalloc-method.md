---
title: Метод IHostMemoryManager::CreateMAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 8bcb01f4a19e6043bd59fe6f1565cdf35ed1f77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136727"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="a9648-102">Метод IHostMemoryManager::CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="a9648-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="a9648-103">Возвращает указатель интерфейса на экземпляр [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) , который используется для выполнения запросов на выделение из кучи, созданной узлом.</span><span class="sxs-lookup"><span data-stu-id="a9648-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9648-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9648-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9648-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9648-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="a9648-106">окне Сочетание флагов [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) , определяющих характеристики выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="a9648-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="a9648-107">заполняет Указатель на адрес экземпляра `IHostMAlloc`, предоставленного узлом.</span><span class="sxs-lookup"><span data-stu-id="a9648-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9648-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a9648-108">Return Value</span></span>  
  
|<span data-ttu-id="a9648-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9648-109">HRESULT</span></span>|<span data-ttu-id="a9648-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a9648-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9648-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9648-111">S_OK</span></span>|<span data-ttu-id="a9648-112">`CreateMAlloc` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a9648-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="a9648-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9648-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9648-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a9648-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9648-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9648-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9648-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="a9648-116">The call timed out.</span></span>|  
|<span data-ttu-id="a9648-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9648-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9648-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="a9648-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9648-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9648-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9648-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="a9648-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9648-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9648-121">E_FAIL</span></span>|<span data-ttu-id="a9648-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="a9648-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9648-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a9648-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9648-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a9648-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a9648-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a9648-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a9648-126">Недостаточно физической памяти для завершения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="a9648-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9648-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="a9648-127">Remarks</span></span>  
 <span data-ttu-id="a9648-128">`CreateMAlloc` возвращает объект, позволяющий среде CLR выполнять запросы на выделение через основное приложение, а не использовать стандартные функции Win32.</span><span class="sxs-lookup"><span data-stu-id="a9648-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9648-129">Требования</span><span class="sxs-lookup"><span data-stu-id="a9648-129">Requirements</span></span>  
 <span data-ttu-id="a9648-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9648-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9648-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a9648-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9648-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a9648-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9648-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9648-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9648-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a9648-134">See also</span></span>

- [<span data-ttu-id="a9648-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="a9648-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="a9648-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="a9648-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
