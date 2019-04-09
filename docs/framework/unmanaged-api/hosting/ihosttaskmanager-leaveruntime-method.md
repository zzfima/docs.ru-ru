---
title: Метод IHostTaskManager::LeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81da8052b79047933b4afc6d5686029465d83eba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191501"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="b557c-102">Метод IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="b557c-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="b557c-103">Уведомляет основное приложение, что текущая выполняющаяся задача сейчас оставьте общеязыковой среды выполнения (CLR) и введите неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b557c-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b557c-104">Соответствующего вызова [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) Уведомляет основное приложение, что текущая выполняющаяся задача является повторное введение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b557c-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b557c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b557c-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b557c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b557c-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="b557c-107">[in] Адрес в сопоставленной переносимый исполняемый файл для вызова неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="b557c-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b557c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b557c-108">Return Value</span></span>  
  
|<span data-ttu-id="b557c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b557c-109">HRESULT</span></span>|<span data-ttu-id="b557c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b557c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b557c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b557c-111">S_OK</span></span>|`LeaveRuntime` <span data-ttu-id="b557c-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b557c-112">returned successfully.</span></span>|  
|<span data-ttu-id="b557c-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b557c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b557c-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b557c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b557c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b557c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b557c-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b557c-116">The call timed out.</span></span>|  
|<span data-ttu-id="b557c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b557c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b557c-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b557c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b557c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b557c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b557c-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b557c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b557c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b557c-121">E_FAIL</span></span>|<span data-ttu-id="b557c-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="b557c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b557c-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b557c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b557c-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b557c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b557c-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b557c-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b557c-126">Недостаточно памяти для завершения запрошенного выделения.</span><span class="sxs-lookup"><span data-stu-id="b557c-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b557c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="b557c-127">Remarks</span></span>  
 <span data-ttu-id="b557c-128">Последовательность вызовов к и из неуправляемого кода могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="b557c-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="b557c-129">Например, следующий список содержит гипотетическую ситуацию, в котором последовательность вызовов к `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), и `IHostTaskManager::EnterRuntime` позволяет основному приложению определить вложенные слои.</span><span class="sxs-lookup"><span data-stu-id="b557c-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="b557c-130">Действие</span><span class="sxs-lookup"><span data-stu-id="b557c-130">Action</span></span>|<span data-ttu-id="b557c-131">Вызов соответствующего метода</span><span class="sxs-lookup"><span data-stu-id="b557c-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="b557c-132">Управляемый исполняемый файл вызывает Visual Basic вызова неуправляемой функции, написанные на языке C с помощью платформы.</span><span class="sxs-lookup"><span data-stu-id="b557c-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="b557c-133">Неуправляемая функция C вызывает метод в управляемую библиотеку DLL, написанные на C#.</span><span class="sxs-lookup"><span data-stu-id="b557c-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="b557c-134">Управляемый C# функция вызывает другую неуправляемую функцию, написанную на языке C, также использование вызов платформ.</span><span class="sxs-lookup"><span data-stu-id="b557c-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="b557c-135">Второй неуправляемая функция возвращает результат выполнения для C# функции.</span><span class="sxs-lookup"><span data-stu-id="b557c-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="b557c-136">C# Функции возвращает результат выполнения первой неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="b557c-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="b557c-137">Первая неуправляемая функция возвращает выполнение программы на Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b557c-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="b557c-138">Требования</span><span class="sxs-lookup"><span data-stu-id="b557c-138">Requirements</span></span>  
 <span data-ttu-id="b557c-139">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b557c-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b557c-140">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b557c-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b557c-141">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b557c-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b557c-142">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b557c-142">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b557c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="b557c-143">See also</span></span>

- [<span data-ttu-id="b557c-144">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b557c-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b557c-145">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b557c-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b557c-146">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b557c-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b557c-147">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b557c-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
