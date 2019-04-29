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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68ebfdcd0ef34edec724a044791d05dd48580b12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697489"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="eecef-102">Метод IHostSecurityManager::OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="eecef-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="eecef-103">Открывает маркер доступа на уровне пользователей, связанный с текущим выполняемым потоком.</span><span class="sxs-lookup"><span data-stu-id="eecef-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eecef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eecef-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eecef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eecef-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="eecef-106">[in] Маска доступа значения, указывающие запрошенных типов доступа к маркер потока.</span><span class="sxs-lookup"><span data-stu-id="eecef-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="eecef-107">Эти значения определены в Win32 `OpenThreadToken` функции.</span><span class="sxs-lookup"><span data-stu-id="eecef-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="eecef-108">Запрошенные типы доступа сравниваются со списком управления доступом маркера (DACL), чтобы определить, какие типы доступа, чтобы предоставить или запретить.</span><span class="sxs-lookup"><span data-stu-id="eecef-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="eecef-109">[in] `true` для указания, что проверка доступа следует выполнить, используя контекст безопасности процесса для вызывающего потока; `false` для указания, что проверка доступа должна выполняться с помощью контекста безопасности для самого вызывающего потока.</span><span class="sxs-lookup"><span data-stu-id="eecef-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="eecef-110">Если поток олицетворяет клиента, контекст безопасности может быть имя клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="eecef-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="eecef-111">[out] Указатель на маркер вновь открытого доступа.</span><span class="sxs-lookup"><span data-stu-id="eecef-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eecef-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eecef-112">Return Value</span></span>  
  
|<span data-ttu-id="eecef-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eecef-113">HRESULT</span></span>|<span data-ttu-id="eecef-114">Описание</span><span class="sxs-lookup"><span data-stu-id="eecef-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eecef-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="eecef-115">S_OK</span></span>|<span data-ttu-id="eecef-116">`OpenThreadToken` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="eecef-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="eecef-117">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eecef-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eecef-118">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="eecef-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eecef-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eecef-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eecef-120">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="eecef-120">The call timed out.</span></span>|  
|<span data-ttu-id="eecef-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eecef-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eecef-122">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="eecef-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eecef-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eecef-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eecef-124">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="eecef-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eecef-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eecef-125">E_FAIL</span></span>|<span data-ttu-id="eecef-126">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="eecef-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eecef-127">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="eecef-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eecef-128">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eecef-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eecef-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="eecef-129">Remarks</span></span>  
 <span data-ttu-id="eecef-130">`IHostSecurityManager::OpenThreadToken` ведет себя точно так же для соответствующей функции Win32 с тем же именем, за исключением того, функцию Win32 позволяет вызывающей стороне передать в дескриптор в произвольном потоке, пока `IHostSecurityManager::OpenThreadToken` открывает только маркером, связанным с вызывающего потока.</span><span class="sxs-lookup"><span data-stu-id="eecef-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="eecef-131">`HANDLE` Типа не удовлетворяет требованиям COM, то есть его размер зависит от операционной системы и требует пользовательский маршалинг.</span><span class="sxs-lookup"><span data-stu-id="eecef-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="eecef-132">Таким образом этот токен предназначен для использования только внутри процесса, в среде CLR и узла.</span><span class="sxs-lookup"><span data-stu-id="eecef-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eecef-133">Требования</span><span class="sxs-lookup"><span data-stu-id="eecef-133">Requirements</span></span>  
 <span data-ttu-id="eecef-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eecef-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eecef-135">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eecef-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eecef-136">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eecef-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eecef-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eecef-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eecef-138">См. также</span><span class="sxs-lookup"><span data-stu-id="eecef-138">See also</span></span>

- [<span data-ttu-id="eecef-139">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="eecef-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="eecef-140">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="eecef-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
