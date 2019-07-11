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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30159748c1103cbc8efaf8929387052bbe5c3ec7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773125"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="3afdd-102">Метод ICLRDebugManager::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="3afdd-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="3afdd-103">Получает значение, показывающее, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="3afdd-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3afdd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3afdd-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3afdd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3afdd-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="3afdd-106">[out] `true` Если отладчик присоединен к процессу; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="3afdd-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3afdd-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3afdd-107">Return Value</span></span>  
  
|<span data-ttu-id="3afdd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3afdd-108">HRESULT</span></span>|<span data-ttu-id="3afdd-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3afdd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3afdd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3afdd-110">S_OK</span></span>|<span data-ttu-id="3afdd-111">`IsDebuggerAttached` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3afdd-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="3afdd-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3afdd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3afdd-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3afdd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3afdd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3afdd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3afdd-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3afdd-115">The call timed out.</span></span>|  
|<span data-ttu-id="3afdd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3afdd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3afdd-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3afdd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3afdd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3afdd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3afdd-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3afdd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3afdd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3afdd-120">E_FAIL</span></span>|<span data-ttu-id="3afdd-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="3afdd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3afdd-122">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="3afdd-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3afdd-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3afdd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3afdd-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="3afdd-124">Remarks</span></span>  
 <span data-ttu-id="3afdd-125">`IsDebuggerAttached` позволяет основному приложению запрашивать CLR, чтобы определить, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="3afdd-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3afdd-126">Требования</span><span class="sxs-lookup"><span data-stu-id="3afdd-126">Requirements</span></span>  
 <span data-ttu-id="3afdd-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3afdd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3afdd-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3afdd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3afdd-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3afdd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3afdd-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3afdd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3afdd-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3afdd-131">See also</span></span>

- [<span data-ttu-id="3afdd-132">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="3afdd-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3afdd-133">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="3afdd-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="3afdd-134">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="3afdd-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
