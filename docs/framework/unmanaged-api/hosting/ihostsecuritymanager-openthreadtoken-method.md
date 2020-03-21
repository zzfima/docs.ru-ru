---
title: Метод IHostSecurityManager::OpenThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176270"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="c81d2-102">Метод IHostSecurityManager::OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="c81d2-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="c81d2-103">Открывает дискреционный маркер доступа, связанный с в настоящее время исполняющим потоком.</span><span class="sxs-lookup"><span data-stu-id="c81d2-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c81d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c81d2-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c81d2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c81d2-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="c81d2-106">(в) Маска значений доступа, которые указывают запрашиваемые типы доступа к маркеру потока.</span><span class="sxs-lookup"><span data-stu-id="c81d2-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="c81d2-107">Эти значения определены в функции Win32. `OpenThreadToken`</span><span class="sxs-lookup"><span data-stu-id="c81d2-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="c81d2-108">Запрошенные типы доступа согласовываются со списком управления дискреционным доступом токена (DACL), чтобы определить, какие типы доступа к предоставлению или отказу.</span><span class="sxs-lookup"><span data-stu-id="c81d2-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="c81d2-109">(в) `true` указать, что проверка доступа должна быть сделана с использованием контекста безопасности процесса для потока вызова; `false` указать, что проверка доступа должна быть выполнена с использованием контекста безопасности для самого потока вызова.</span><span class="sxs-lookup"><span data-stu-id="c81d2-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="c81d2-110">Если поток выдает себя за клиента, контекст безопасности может быть контекстом процесса клиента.</span><span class="sxs-lookup"><span data-stu-id="c81d2-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="c81d2-111">(ваут) Указатель на недавно открытый токен доступа.</span><span class="sxs-lookup"><span data-stu-id="c81d2-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c81d2-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c81d2-112">Return Value</span></span>  
  
|<span data-ttu-id="c81d2-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c81d2-113">HRESULT</span></span>|<span data-ttu-id="c81d2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c81d2-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c81d2-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c81d2-115">S_OK</span></span>|<span data-ttu-id="c81d2-116">`OpenThreadToken`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="c81d2-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="c81d2-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c81d2-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c81d2-118">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c81d2-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c81d2-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c81d2-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c81d2-120">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="c81d2-120">The call timed out.</span></span>|  
|<span data-ttu-id="c81d2-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c81d2-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c81d2-122">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="c81d2-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c81d2-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c81d2-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c81d2-124">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="c81d2-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c81d2-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c81d2-125">E_FAIL</span></span>|<span data-ttu-id="c81d2-126">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="c81d2-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c81d2-127">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="c81d2-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c81d2-128">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c81d2-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c81d2-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="c81d2-129">Remarks</span></span>  
 <span data-ttu-id="c81d2-130">`IHostSecurityManager::OpenThreadToken`ведет себя аналогично соответствующей функции Win32 с тем же именем, за исключением того, что функция `IHostSecurityManager::OpenThreadToken` Win32 позволяет абоненту передавать в ручку произвольному потоку, в то время как открывается только маркер, связанный с потоком вызова.</span><span class="sxs-lookup"><span data-stu-id="c81d2-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="c81d2-131">Тип `HANDLE` не соответствует COM, то есть его размер специфичен для операционной системы, и он требует пользовательского маршалинга.</span><span class="sxs-lookup"><span data-stu-id="c81d2-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="c81d2-132">Таким образом, этот маркер предназначен для использования только в процессе, между CLR и хостом.</span><span class="sxs-lookup"><span data-stu-id="c81d2-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c81d2-133">Требования</span><span class="sxs-lookup"><span data-stu-id="c81d2-133">Requirements</span></span>  
 <span data-ttu-id="c81d2-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c81d2-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c81d2-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c81d2-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c81d2-136">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c81d2-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c81d2-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c81d2-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81d2-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c81d2-138">See also</span></span>

- [<span data-ttu-id="c81d2-139">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="c81d2-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c81d2-140">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="c81d2-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
