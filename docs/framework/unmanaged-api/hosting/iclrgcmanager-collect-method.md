---
title: Метод ICLRGCManager::Collect
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
ms.openlocfilehash: a7dae98d1f2dc2448bd3a5df2d6143b7be0bb734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129263"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="b2bfe-102">Метод ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="b2bfe-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="b2bfe-103">Вызывает принудительную сборку мусора для указанного поколения.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2bfe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2bfe-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2bfe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2bfe-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="b2bfe-106">окне Поколение, которое необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-106">[in] The generation to collect.</span></span> <span data-ttu-id="b2bfe-107">Значение-1 вызывает сбор всех поколений.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2bfe-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2bfe-108">Return Value</span></span>  
  
|<span data-ttu-id="b2bfe-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2bfe-109">HRESULT</span></span>|<span data-ttu-id="b2bfe-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b2bfe-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2bfe-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2bfe-111">S_OK</span></span>|<span data-ttu-id="b2bfe-112">`Collect` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="b2bfe-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2bfe-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2bfe-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2bfe-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2bfe-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2bfe-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-116">The call timed out.</span></span>|  
|<span data-ttu-id="b2bfe-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2bfe-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2bfe-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2bfe-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2bfe-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2bfe-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2bfe-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2bfe-121">E_FAIL</span></span>|<span data-ttu-id="b2bfe-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2bfe-123">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2bfe-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2bfe-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="b2bfe-125">Remarks</span></span>  
 <span data-ttu-id="b2bfe-126">Метод `Collect` заставляет сборщик мусора среды CLR выполнить сбор данных независимо от текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="b2bfe-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2bfe-127">Требования</span><span class="sxs-lookup"><span data-stu-id="b2bfe-127">Requirements</span></span>  
 <span data-ttu-id="b2bfe-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2bfe-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2bfe-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b2bfe-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2bfe-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2bfe-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2bfe-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2bfe-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bfe-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b2bfe-132">See also</span></span>

- [<span data-ttu-id="b2bfe-133">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="b2bfe-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="b2bfe-134">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="b2bfe-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="b2bfe-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="b2bfe-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b2bfe-136">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="b2bfe-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="b2bfe-137">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b2bfe-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="b2bfe-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b2bfe-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b2bfe-139">Размещение</span><span class="sxs-lookup"><span data-stu-id="b2bfe-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
