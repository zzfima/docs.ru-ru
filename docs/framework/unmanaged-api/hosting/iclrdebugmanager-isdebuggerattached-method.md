---
title: Метод ICLRDebugManager::IsDebuggerAttached
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
ms.openlocfilehash: a58fcb6c1fa2aad96cdd29194a21eaf590536cdd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129398"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="fa92f-102">Метод ICLRDebugManager::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="fa92f-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="fa92f-103">Получает значение, показывающее, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="fa92f-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa92f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa92f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa92f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa92f-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="fa92f-106">[out] `true`, если к процессу присоединен отладчик; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="fa92f-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa92f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fa92f-107">Return Value</span></span>  
  
|<span data-ttu-id="fa92f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa92f-108">HRESULT</span></span>|<span data-ttu-id="fa92f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fa92f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa92f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa92f-110">S_OK</span></span>|<span data-ttu-id="fa92f-111">`IsDebuggerAttached` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fa92f-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="fa92f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa92f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa92f-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fa92f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa92f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa92f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa92f-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fa92f-115">The call timed out.</span></span>|  
|<span data-ttu-id="fa92f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa92f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa92f-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fa92f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa92f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa92f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa92f-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fa92f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa92f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa92f-120">E_FAIL</span></span>|<span data-ttu-id="fa92f-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fa92f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa92f-122">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fa92f-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa92f-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fa92f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa92f-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="fa92f-124">Remarks</span></span>  
 <span data-ttu-id="fa92f-125">`IsDebuggerAttached` позволяет основному приложению запрашивать среду CLR, чтобы определить, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="fa92f-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa92f-126">Требования</span><span class="sxs-lookup"><span data-stu-id="fa92f-126">Requirements</span></span>  
 <span data-ttu-id="fa92f-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa92f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa92f-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fa92f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa92f-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fa92f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa92f-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa92f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa92f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="fa92f-131">See also</span></span>

- [<span data-ttu-id="fa92f-132">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="fa92f-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="fa92f-133">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="fa92f-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="fa92f-134">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="fa92f-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
