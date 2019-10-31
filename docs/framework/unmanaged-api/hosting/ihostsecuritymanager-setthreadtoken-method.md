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
ms.openlocfilehash: aa17f637ef71373697db5ce66e4a6540c5cc5fbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139493"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="311e2-102">Метод IHostSecurityManager::SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="311e2-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="311e2-103">Задает обработчик для текущего выполняющегося потока.</span><span class="sxs-lookup"><span data-stu-id="311e2-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="311e2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="311e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="311e2-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="311e2-106">окне Маркер, который задается для выполняемого в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="311e2-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="311e2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="311e2-107">Return Value</span></span>  
  
|<span data-ttu-id="311e2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="311e2-108">HRESULT</span></span>|<span data-ttu-id="311e2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="311e2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="311e2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="311e2-110">S_OK</span></span>|<span data-ttu-id="311e2-111">`SetThreadToken` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="311e2-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="311e2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="311e2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="311e2-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="311e2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="311e2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="311e2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="311e2-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="311e2-115">The call timed out.</span></span>|  
|<span data-ttu-id="311e2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="311e2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="311e2-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="311e2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="311e2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="311e2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="311e2-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="311e2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="311e2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="311e2-120">E_FAIL</span></span>|<span data-ttu-id="311e2-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="311e2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="311e2-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="311e2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="311e2-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="311e2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="311e2-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="311e2-124">Remarks</span></span>  
 <span data-ttu-id="311e2-125">`IHostSecurityManager::SetThreadToken` ведет себя аналогично соответствующей функции Win32 с тем же именем, за исключением того, что функция Win32 позволяет вызывающему объекту передать обработчик произвольному потоку, тогда как `IHostSecurityManager::SetThreadToken` может связать маркер только с текущим выполняющимся потоком.</span><span class="sxs-lookup"><span data-stu-id="311e2-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="311e2-126">Тип `HANDLE` не совместим с COM; то есть его размер зависит от операционной системы и требует настраиваемого маршалирования.</span><span class="sxs-lookup"><span data-stu-id="311e2-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="311e2-127">Таким же маркер предназначен только для использования внутри процесса между средой CLR и узлом.</span><span class="sxs-lookup"><span data-stu-id="311e2-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="311e2-128">Требования</span><span class="sxs-lookup"><span data-stu-id="311e2-128">Requirements</span></span>  
 <span data-ttu-id="311e2-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="311e2-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="311e2-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="311e2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="311e2-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="311e2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="311e2-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="311e2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311e2-133">См. также</span><span class="sxs-lookup"><span data-stu-id="311e2-133">See also</span></span>

- [<span data-ttu-id="311e2-134">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="311e2-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="311e2-135">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="311e2-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
