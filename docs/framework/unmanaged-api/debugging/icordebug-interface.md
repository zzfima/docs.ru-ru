---
title: "Интерфейс ICorDebug"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug
helpviewer_keywords: ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62a29133252277cbf614a1916af6fa4c6905a920
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebug-interface"></a><span data-ttu-id="aefae-102">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="aefae-102">ICorDebug Interface</span></span>
<span data-ttu-id="aefae-103">Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="aefae-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aefae-104">Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME или на платформах, отличных от x86 (например, IA64 и AMD64).</span><span class="sxs-lookup"><span data-stu-id="aefae-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aefae-105">Методы</span><span class="sxs-lookup"><span data-stu-id="aefae-105">Methods</span></span>  
  
|<span data-ttu-id="aefae-106">Метод</span><span class="sxs-lookup"><span data-stu-id="aefae-106">Method</span></span>|<span data-ttu-id="aefae-107">Описание</span><span class="sxs-lookup"><span data-stu-id="aefae-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aefae-108">Метод CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="aefae-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="aefae-109">Определяет, возможна ли запуск нового процесса или вложение в данный процесс в контексте текущей конфигурации компьютера и среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="aefae-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="aefae-110">Метод CreateProcess</span><span class="sxs-lookup"><span data-stu-id="aefae-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="aefae-111">Запускает процесс и основной поток под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="aefae-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="aefae-112">Метод DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="aefae-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="aefae-113">Присоединяет отладчик к существующему процессу.</span><span class="sxs-lookup"><span data-stu-id="aefae-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="aefae-114">Метод EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="aefae-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="aefae-115">Получает перечислитель для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="aefae-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="aefae-116">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="aefae-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="aefae-117">Возвращает объект «ICorDebugProcess» с идентификатор данного процесса.</span><span class="sxs-lookup"><span data-stu-id="aefae-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="aefae-118">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="aefae-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="aefae-119">Инициализирует `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="aefae-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="aefae-120">Метод SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="aefae-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="aefae-121">Указывает объект обработчика событий для управляемых событий.</span><span class="sxs-lookup"><span data-stu-id="aefae-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="aefae-122">Метод SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="aefae-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="aefae-123">Задает объект обработчика событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="aefae-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="aefae-124">Terminate-метод</span><span class="sxs-lookup"><span data-stu-id="aefae-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="aefae-125">Завершает `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="aefae-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aefae-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="aefae-126">Remarks</span></span>  
 <span data-ttu-id="aefae-127">`ICorDebug`представляет цикл обработки событий для процесса отладчика.</span><span class="sxs-lookup"><span data-stu-id="aefae-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="aefae-128">Отладчик должен ожидать [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) от всех процессов, отлаживаемых перед тем как освободить этот интерфейс обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="aefae-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="aefae-129">`ICorDebug` Объект является исходным объектом, для управления все дополнительные управляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="aefae-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="aefae-130">В .NET Framework версий 1.0 и 1.1, этот объект был `CoClass` объектом, созданным из COM.</span><span class="sxs-lookup"><span data-stu-id="aefae-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="aefae-131">В платформе .NET Framework версии 2.0 этот объект больше не `CoClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="aefae-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="aefae-132">Должны быть созданы с [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) функции, которая более следящее за версией.</span><span class="sxs-lookup"><span data-stu-id="aefae-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="aefae-133">Эта новая функция создания позволяет клиентам получать реализации `ICorDebug`, который также эмулируют определенную версию API отладки.</span><span class="sxs-lookup"><span data-stu-id="aefae-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aefae-134">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="aefae-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aefae-135">Требования</span><span class="sxs-lookup"><span data-stu-id="aefae-135">Requirements</span></span>  
 <span data-ttu-id="aefae-136">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aefae-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aefae-137">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aefae-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aefae-138">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aefae-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aefae-139">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aefae-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefae-140">См. также</span><span class="sxs-lookup"><span data-stu-id="aefae-140">See Also</span></span>  
 [<span data-ttu-id="aefae-141">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="aefae-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
