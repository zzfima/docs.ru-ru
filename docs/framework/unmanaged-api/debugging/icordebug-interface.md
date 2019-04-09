---
title: Интерфейс ICorDebug
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193232ce1006a9cf209db9330343386404948440
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168289"
---
# <a name="icordebug-interface"></a><span data-ttu-id="e62e9-102">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e62e9-102">ICorDebug Interface</span></span>
<span data-ttu-id="e62e9-103">Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="e62e9-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e62e9-104">Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME или на платформах, отличных от — x86 (например, IA64 и AMD64).</span><span class="sxs-lookup"><span data-stu-id="e62e9-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e62e9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e62e9-105">Methods</span></span>  
  
|<span data-ttu-id="e62e9-106">Метод</span><span class="sxs-lookup"><span data-stu-id="e62e9-106">Method</span></span>|<span data-ttu-id="e62e9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e62e9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e62e9-108">Метод CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="e62e9-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="e62e9-109">Определяет, возможна ли запуск нового процесса или вложение в данный процесс в контексте текущей конфигурации компьютера и среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e62e9-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="e62e9-110">Метод CreateProcess</span><span class="sxs-lookup"><span data-stu-id="e62e9-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="e62e9-111">Запускает процесс и основной поток под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="e62e9-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="e62e9-112">Метод DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="e62e9-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="e62e9-113">Присоединяет отладчик к существующему процессу.</span><span class="sxs-lookup"><span data-stu-id="e62e9-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="e62e9-114">Метод EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="e62e9-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="e62e9-115">Получает перечислитель для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="e62e9-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="e62e9-116">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="e62e9-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="e62e9-117">Возвращает объект «ICorDebugProcess» с идентификатором указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="e62e9-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="e62e9-118">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="e62e9-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="e62e9-119">Инициализирует `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="e62e9-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="e62e9-120">Метод SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="e62e9-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="e62e9-121">Указывает объект обработчика событий для управляемых событий.</span><span class="sxs-lookup"><span data-stu-id="e62e9-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="e62e9-122">Метод SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="e62e9-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="e62e9-123">Указывает объект обработчика событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="e62e9-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="e62e9-124">Метод Terminate</span><span class="sxs-lookup"><span data-stu-id="e62e9-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="e62e9-125">Завершает `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="e62e9-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e62e9-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e62e9-126">Remarks</span></span>  
 `ICorDebug` <span data-ttu-id="e62e9-127">представляет цикл обработки событий для процесса отладчика.</span><span class="sxs-lookup"><span data-stu-id="e62e9-127">represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="e62e9-128">Отладчик должен ожидать [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) обратного вызова от всех процессов, отлаживаемых перед тем как освободить этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e62e9-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="e62e9-129">`ICorDebug` Объект является исходный объект для управления все дополнительные управляемые отладки.</span><span class="sxs-lookup"><span data-stu-id="e62e9-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="e62e9-130">В .NET Framework версий 1.0 и 1.1, этот объект был `CoClass` объект, созданный из COM.</span><span class="sxs-lookup"><span data-stu-id="e62e9-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="e62e9-131">В .NET Framework версии 2.0, этот объект больше не `CoClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="e62e9-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="e62e9-132">Она должна быть создана путем [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) функцию, которая более следящее за версией.</span><span class="sxs-lookup"><span data-stu-id="e62e9-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="e62e9-133">Эта новая функция создания позволяет клиентам получать реализации `ICorDebug`, которое также позволяет эмулировать определенную версию API отладки.</span><span class="sxs-lookup"><span data-stu-id="e62e9-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e62e9-134">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e62e9-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e62e9-135">Требования</span><span class="sxs-lookup"><span data-stu-id="e62e9-135">Requirements</span></span>  
 <span data-ttu-id="e62e9-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e62e9-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e62e9-137">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e62e9-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e62e9-138">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e62e9-138">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e62e9-139">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e62e9-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e62e9-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e62e9-140">See also</span></span>

- [<span data-ttu-id="e62e9-141">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e62e9-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
