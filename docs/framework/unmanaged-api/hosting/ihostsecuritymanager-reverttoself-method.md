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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c34d9243e4ed7ed2492784154b157189c7d22cd2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440584"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="4b990-102">Метод IHostSecurityManager::RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="4b990-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="4b990-103">Завершает олицетворение удостоверения текущего пользователя и возвращает исходный маркер потока.</span><span class="sxs-lookup"><span data-stu-id="4b990-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b990-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b990-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4b990-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4b990-105">Return Value</span></span>  
  
|<span data-ttu-id="4b990-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b990-106">HRESULT</span></span>|<span data-ttu-id="4b990-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4b990-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b990-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b990-108">S_OK</span></span>|<span data-ttu-id="4b990-109">`RevertToSelf` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4b990-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="4b990-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4b990-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4b990-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4b990-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4b990-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4b990-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4b990-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4b990-113">The call timed out.</span></span>|  
|<span data-ttu-id="4b990-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4b990-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4b990-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4b990-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4b990-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4b990-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4b990-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4b990-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4b990-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b990-118">E_FAIL</span></span>|<span data-ttu-id="4b990-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="4b990-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b990-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4b990-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4b990-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4b990-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b990-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b990-122">Remarks</span></span>  
 <span data-ttu-id="4b990-123">`RevertToSelf` вызывается для возврата исходный маркер потока после предыдущего вызова [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4b990-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b990-124">Требования</span><span class="sxs-lookup"><span data-stu-id="4b990-124">Requirements</span></span>  
 <span data-ttu-id="4b990-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b990-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b990-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b990-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b990-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b990-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b990-128">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b990-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b990-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4b990-129">See Also</span></span>  
 [<span data-ttu-id="4b990-130">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="4b990-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="4b990-131">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="4b990-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="4b990-132">Метод ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="4b990-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
