---
title: "Метод IHostSecurityManager::OpenThreadToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b5c39632d7628d30149a0a0278f9bf6c865bc29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="a13d7-102">Метод IHostSecurityManager::OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="a13d7-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="a13d7-103">Открывает маркер доступом, связанный с текущей выполняемой потоком.</span><span class="sxs-lookup"><span data-stu-id="a13d7-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a13d7-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a13d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a13d7-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="a13d7-106">[in] Маска доступа значений, указывающих запрошенных типов доступа к маркер потока.</span><span class="sxs-lookup"><span data-stu-id="a13d7-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="a13d7-107">Эти значения определяются в Win32 `OpenThreadToken` функции.</span><span class="sxs-lookup"><span data-stu-id="a13d7-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="a13d7-108">Запрошенные типы доступа сравниваются со списком управления доступом маркера (DACL), чтобы определить, какие типы доступа, чтобы предоставить или отменить.</span><span class="sxs-lookup"><span data-stu-id="a13d7-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="a13d7-109">[in] `true` для указания, что проверка доступа следует выполнить, используя контекст безопасности процесса для вызывающего потока; `false` для указания, что проверка доступа должны выполняться с использованием контекста безопасности для самого вызывающего потока.</span><span class="sxs-lookup"><span data-stu-id="a13d7-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="a13d7-110">Если поток олицетворяет клиента, контекст безопасности может быть клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="a13d7-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="a13d7-111">[out] Указатель на токен открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="a13d7-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a13d7-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a13d7-112">Return Value</span></span>  
  
|<span data-ttu-id="a13d7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a13d7-113">HRESULT</span></span>|<span data-ttu-id="a13d7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a13d7-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a13d7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a13d7-115">S_OK</span></span>|<span data-ttu-id="a13d7-116">`OpenThreadToken`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a13d7-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="a13d7-117">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a13d7-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a13d7-118">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a13d7-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a13d7-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a13d7-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a13d7-120">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a13d7-120">The call timed out.</span></span>|  
|<span data-ttu-id="a13d7-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a13d7-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a13d7-122">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a13d7-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a13d7-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a13d7-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a13d7-124">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a13d7-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a13d7-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a13d7-125">E_FAIL</span></span>|<span data-ttu-id="a13d7-126">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="a13d7-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a13d7-127">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a13d7-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a13d7-128">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a13d7-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a13d7-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="a13d7-129">Remarks</span></span>  
 <span data-ttu-id="a13d7-130">`IHostSecurityManager::OpenThreadToken`ведет себя точно так же для соответствующей функции Win32 с таким же именем, за исключением того, что функция Win32 позволяет вызывающему объекту произвольном потоке, передается дескриптор, хотя `IHostSecurityManager::OpenThreadToken` открывает только маркером, связанным с вызывающего потока.</span><span class="sxs-lookup"><span data-stu-id="a13d7-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="a13d7-131">`HANDLE` Типа не удовлетворяет требованиям COM, то есть, его размер будет относится к операционной системе и требуется пользовательский маршалинг.</span><span class="sxs-lookup"><span data-stu-id="a13d7-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="a13d7-132">Таким образом этот токен предназначен для использования только в пределах процесса в среде CLR и узла.</span><span class="sxs-lookup"><span data-stu-id="a13d7-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13d7-133">Требования</span><span class="sxs-lookup"><span data-stu-id="a13d7-133">Requirements</span></span>  
 <span data-ttu-id="a13d7-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a13d7-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13d7-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a13d7-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a13d7-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a13d7-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a13d7-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13d7-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13d7-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a13d7-138">See Also</span></span>  
 [<span data-ttu-id="a13d7-139">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="a13d7-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="a13d7-140">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="a13d7-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
