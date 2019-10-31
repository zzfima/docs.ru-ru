---
title: Метод IHostIoCompletionManager::SetCLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
ms.openlocfilehash: b84e92ca356ad83421d788a732926b614ffa4a8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133792"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="a76c2-102">Метод IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a76c2-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="a76c2-103">Предоставляет узлу указатель интерфейса на экземпляр [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) , реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="a76c2-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a76c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a76c2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a76c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a76c2-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="a76c2-106">окне Указатель интерфейса на экземпляр `ICLRIoCompletionManager`, предоставленный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="a76c2-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a76c2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a76c2-107">Return Value</span></span>  
  
|<span data-ttu-id="a76c2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a76c2-108">HRESULT</span></span>|<span data-ttu-id="a76c2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a76c2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a76c2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a76c2-110">S_OK</span></span>|<span data-ttu-id="a76c2-111">`SetCLRIoCompletionManager` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a76c2-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="a76c2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a76c2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a76c2-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a76c2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a76c2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a76c2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a76c2-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="a76c2-115">The call timed out.</span></span>|  
|<span data-ttu-id="a76c2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a76c2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a76c2-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="a76c2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a76c2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a76c2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a76c2-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="a76c2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a76c2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a76c2-120">E_FAIL</span></span>|<span data-ttu-id="a76c2-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="a76c2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a76c2-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a76c2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a76c2-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a76c2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a76c2-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="a76c2-124">Remarks</span></span>  
 <span data-ttu-id="a76c2-125">После того как среда CLR вызовет `SetCLRIoCompletionManager`, узел должен вызвать метод [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) , чтобы уведомить CLR о завершении запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="a76c2-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a76c2-126">Требования</span><span class="sxs-lookup"><span data-stu-id="a76c2-126">Requirements</span></span>  
 <span data-ttu-id="a76c2-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a76c2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a76c2-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a76c2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a76c2-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a76c2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a76c2-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a76c2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76c2-131">См. также</span><span class="sxs-lookup"><span data-stu-id="a76c2-131">See also</span></span>

- [<span data-ttu-id="a76c2-132">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a76c2-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="a76c2-133">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a76c2-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
