---
title: Метод IHostSecurityManager::SetThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c67471c0d88ccffbfe9b7c77809124452ccc2e5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696643"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="ba197-102">Метод IHostSecurityManager::SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="ba197-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="ba197-103">Задает дескриптор для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="ba197-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba197-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba197-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba197-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba197-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="ba197-106">[in] Дескриптор токен, который требуется для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="ba197-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba197-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba197-107">Return Value</span></span>  
  
|<span data-ttu-id="ba197-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba197-108">HRESULT</span></span>|<span data-ttu-id="ba197-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ba197-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba197-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba197-110">S_OK</span></span>|<span data-ttu-id="ba197-111">`SetThreadToken` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ba197-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="ba197-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba197-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba197-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ba197-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba197-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba197-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba197-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="ba197-115">The call timed out.</span></span>|  
|<span data-ttu-id="ba197-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba197-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba197-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="ba197-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba197-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba197-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba197-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="ba197-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba197-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba197-120">E_FAIL</span></span>|<span data-ttu-id="ba197-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="ba197-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba197-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ba197-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba197-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ba197-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba197-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba197-124">Remarks</span></span>  
 <span data-ttu-id="ba197-125">`IHostSecurityManager::SetThreadToken` ведет себя точно так же для соответствующей функции Win32 с тем же именем, за исключением того, функцию Win32 позволяет вызывающей стороне передать в дескриптор в произвольном потоке, пока `IHostSecurityManager::SetThreadToken` можно связать маркер только с текущим выполняемым потоком.</span><span class="sxs-lookup"><span data-stu-id="ba197-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="ba197-126">`HANDLE` Тип не является COM-совместимым; то есть его размер зависит от операционной системы и требует пользовательский маршалинг.</span><span class="sxs-lookup"><span data-stu-id="ba197-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="ba197-127">Таким образом этот токен предназначен для использования только внутри процесса, в среде CLR и узла.</span><span class="sxs-lookup"><span data-stu-id="ba197-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba197-128">Требования</span><span class="sxs-lookup"><span data-stu-id="ba197-128">Requirements</span></span>  
 <span data-ttu-id="ba197-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba197-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba197-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ba197-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba197-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba197-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba197-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba197-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba197-133">См. также</span><span class="sxs-lookup"><span data-stu-id="ba197-133">See also</span></span>

- [<span data-ttu-id="ba197-134">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="ba197-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="ba197-135">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="ba197-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
