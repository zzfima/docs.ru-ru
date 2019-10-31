---
title: Метод IHostSecurityManager::RevertToSelf
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
ms.openlocfilehash: b896c5509cc4862a6416381f89bc04a28959e091
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121457"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="78f2a-102">Метод IHostSecurityManager::RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="78f2a-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="78f2a-103">Завершает олицетворение текущего удостоверения пользователя и возвращает исходный маркер потока.</span><span class="sxs-lookup"><span data-stu-id="78f2a-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78f2a-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="78f2a-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="78f2a-105">Return Value</span></span>  
  
|<span data-ttu-id="78f2a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78f2a-106">HRESULT</span></span>|<span data-ttu-id="78f2a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="78f2a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78f2a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="78f2a-108">S_OK</span></span>|<span data-ttu-id="78f2a-109">`RevertToSelf` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="78f2a-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="78f2a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78f2a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78f2a-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="78f2a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78f2a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78f2a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78f2a-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="78f2a-113">The call timed out.</span></span>|  
|<span data-ttu-id="78f2a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78f2a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78f2a-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="78f2a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78f2a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78f2a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78f2a-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="78f2a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78f2a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78f2a-118">E_FAIL</span></span>|<span data-ttu-id="78f2a-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="78f2a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78f2a-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="78f2a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78f2a-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="78f2a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78f2a-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="78f2a-122">Remarks</span></span>  
 <span data-ttu-id="78f2a-123">`RevertToSelf` вызывается для возврата к исходному маркеру потока после предыдущего вызова метода [имперсонателогжедонусер](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) .</span><span class="sxs-lookup"><span data-stu-id="78f2a-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f2a-124">Требования</span><span class="sxs-lookup"><span data-stu-id="78f2a-124">Requirements</span></span>  
 <span data-ttu-id="78f2a-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78f2a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78f2a-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="78f2a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78f2a-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="78f2a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78f2a-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78f2a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f2a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="78f2a-129">See also</span></span>

- [<span data-ttu-id="78f2a-130">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="78f2a-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="78f2a-131">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="78f2a-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="78f2a-132">Метод ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="78f2a-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
