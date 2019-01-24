---
title: Метод IHostSecurityManager::ImpersonateLoggedOnUser
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ceb199e027b111c8e29166d3b91027a3df2d534e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658615"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="85531-102">Метод IHostSecurityManager::ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="85531-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="85531-103">Запросы на выполнение кода с использованием учетных данных удостоверения текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="85531-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85531-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85531-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85531-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="85531-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="85531-106">[in] Токен, представляющий учетные данные пользователя для олицетворения.</span><span class="sxs-lookup"><span data-stu-id="85531-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85531-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85531-107">Return Value</span></span>  
  
|<span data-ttu-id="85531-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85531-108">HRESULT</span></span>|<span data-ttu-id="85531-109">Описание</span><span class="sxs-lookup"><span data-stu-id="85531-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85531-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="85531-110">S_OK</span></span>|<span data-ttu-id="85531-111">`ImpersonateLoggedOnUser` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="85531-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="85531-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85531-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85531-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="85531-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85531-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85531-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85531-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="85531-115">The call timed out.</span></span>|  
|<span data-ttu-id="85531-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85531-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85531-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="85531-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85531-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85531-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85531-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="85531-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85531-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85531-120">E_FAIL</span></span>|<span data-ttu-id="85531-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="85531-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85531-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="85531-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85531-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85531-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85531-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="85531-124">Remarks</span></span>  
 <span data-ttu-id="85531-125">Вызовите `LogonUser` или соответствующую функцию Win32 для получения дескриптора учетных данных удостоверения текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="85531-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="85531-126">`HANDLE` Типа не удовлетворяет требованиям COM, то есть его размер зависит от операционной системы и требует пользовательский маршалинг.</span><span class="sxs-lookup"><span data-stu-id="85531-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="85531-127">Таким образом этот токен предназначен для использования только внутри процесса, в среде CLR и узла.</span><span class="sxs-lookup"><span data-stu-id="85531-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85531-128">Требования</span><span class="sxs-lookup"><span data-stu-id="85531-128">Requirements</span></span>  
 <span data-ttu-id="85531-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85531-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85531-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85531-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85531-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85531-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85531-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85531-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85531-133">См. также</span><span class="sxs-lookup"><span data-stu-id="85531-133">See also</span></span>
- [<span data-ttu-id="85531-134">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="85531-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="85531-135">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="85531-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="85531-136">Метод RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="85531-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
