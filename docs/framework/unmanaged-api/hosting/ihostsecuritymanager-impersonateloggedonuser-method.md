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
ms.openlocfilehash: 93051ca9a0b6f57f41d0d17335a838fe92832d8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121501"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="e1be8-102">Метод IHostSecurityManager::ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="e1be8-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="e1be8-103">Запрашивает выполнение кода с использованием учетных данных удостоверения текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1be8-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1be8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1be8-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1be8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1be8-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="e1be8-106">окне Маркер, представляющий учетные данные пользователя, для которого необходимо выполнить олицетворение.</span><span class="sxs-lookup"><span data-stu-id="e1be8-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1be8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e1be8-107">Return Value</span></span>  
  
|<span data-ttu-id="e1be8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1be8-108">HRESULT</span></span>|<span data-ttu-id="e1be8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e1be8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1be8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1be8-110">S_OK</span></span>|<span data-ttu-id="e1be8-111">`ImpersonateLoggedOnUser` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="e1be8-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="e1be8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1be8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1be8-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e1be8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e1be8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e1be8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e1be8-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="e1be8-115">The call timed out.</span></span>|  
|<span data-ttu-id="e1be8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1be8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e1be8-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="e1be8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e1be8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e1be8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e1be8-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="e1be8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e1be8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1be8-120">E_FAIL</span></span>|<span data-ttu-id="e1be8-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="e1be8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e1be8-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e1be8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e1be8-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e1be8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1be8-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="e1be8-124">Remarks</span></span>  
 <span data-ttu-id="e1be8-125">Вызовите `LogonUser` или связанную функцию Win32, чтобы получить маркер для учетных данных удостоверения текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1be8-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="e1be8-126">Тип `HANDLE` не совместим с COM, то есть его размер зависит от операционной системы и требует настраиваемого маршалирования.</span><span class="sxs-lookup"><span data-stu-id="e1be8-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="e1be8-127">Таким же маркер предназначен только для использования внутри процесса между средой CLR и узлом.</span><span class="sxs-lookup"><span data-stu-id="e1be8-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1be8-128">Требования</span><span class="sxs-lookup"><span data-stu-id="e1be8-128">Requirements</span></span>  
 <span data-ttu-id="e1be8-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1be8-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1be8-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e1be8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1be8-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e1be8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1be8-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1be8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1be8-133">См. также</span><span class="sxs-lookup"><span data-stu-id="e1be8-133">See also</span></span>

- [<span data-ttu-id="e1be8-134">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="e1be8-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="e1be8-135">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="e1be8-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="e1be8-136">Метод RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="e1be8-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
