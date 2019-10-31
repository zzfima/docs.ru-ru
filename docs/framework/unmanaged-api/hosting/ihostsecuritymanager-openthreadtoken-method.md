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
ms.openlocfilehash: 2ced153798355aff882f0244f3dd946c39dea2bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121467"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="84458-102">Метод IHostSecurityManager::OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="84458-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="84458-103">Открывает маркер доступа на уровне пользователей, связанный с выполняющимся в данный момент потоком.</span><span class="sxs-lookup"><span data-stu-id="84458-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84458-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84458-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84458-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84458-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="84458-106">окне Маска значений доступа, указывающих запрошенные типы доступа к токену потока.</span><span class="sxs-lookup"><span data-stu-id="84458-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="84458-107">Эти значения определены в функции Win32 `OpenThreadToken`.</span><span class="sxs-lookup"><span data-stu-id="84458-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="84458-108">Запрошенные типы доступа согласовываются с избирательным списком управления доступом (DACL) маркера, чтобы определить, какие типы доступа следует предоставить или запретить.</span><span class="sxs-lookup"><span data-stu-id="84458-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="84458-109">[in] `true`, чтобы указать, что проверка доступа должна выполняться с помощью контекста безопасности процесса для вызывающего потока; `false`, чтобы указать, что проверку доступа следует выполнять с помощью контекста безопасности для самого вызывающего потока.</span><span class="sxs-lookup"><span data-stu-id="84458-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="84458-110">Если поток олицетворяет клиента, контекст безопасности может быть таким же, как у клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="84458-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="84458-111">заполняет Указатель на вновь открытый маркер доступа.</span><span class="sxs-lookup"><span data-stu-id="84458-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84458-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84458-112">Return Value</span></span>  
  
|<span data-ttu-id="84458-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84458-113">HRESULT</span></span>|<span data-ttu-id="84458-114">Описание</span><span class="sxs-lookup"><span data-stu-id="84458-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84458-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="84458-115">S_OK</span></span>|<span data-ttu-id="84458-116">`OpenThreadToken` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="84458-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="84458-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84458-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84458-118">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="84458-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84458-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84458-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84458-120">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="84458-120">The call timed out.</span></span>|  
|<span data-ttu-id="84458-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84458-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84458-122">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="84458-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84458-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84458-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84458-124">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="84458-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84458-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84458-125">E_FAIL</span></span>|<span data-ttu-id="84458-126">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="84458-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84458-127">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="84458-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84458-128">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="84458-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84458-129">Заметки</span><span class="sxs-lookup"><span data-stu-id="84458-129">Remarks</span></span>  
 <span data-ttu-id="84458-130">`IHostSecurityManager::OpenThreadToken` ведет себя аналогично соответствующей функции Win32 с тем же именем, за исключением того, что функция Win32 позволяет вызывающему объекту передать обработчик произвольному потоку, тогда как `IHostSecurityManager::OpenThreadToken` открывает только маркер, связанный с вызывающим потоком.</span><span class="sxs-lookup"><span data-stu-id="84458-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="84458-131">Тип `HANDLE` не совместим с COM, то есть его размер зависит от операционной системы и требует настраиваемого маршалирования.</span><span class="sxs-lookup"><span data-stu-id="84458-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="84458-132">Таким же маркер предназначен только для использования внутри процесса между средой CLR и узлом.</span><span class="sxs-lookup"><span data-stu-id="84458-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84458-133">Требования</span><span class="sxs-lookup"><span data-stu-id="84458-133">Requirements</span></span>  
 <span data-ttu-id="84458-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84458-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84458-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84458-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84458-136">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84458-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84458-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84458-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84458-138">См. также</span><span class="sxs-lookup"><span data-stu-id="84458-138">See also</span></span>

- [<span data-ttu-id="84458-139">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="84458-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="84458-140">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="84458-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
