---
title: Интерфейс ICorDebugManagedCallback2
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
ms.openlocfilehash: 43982ebb634843c0130c3321aa84c90b84e8c786
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793316"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="49868-102">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="49868-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="49868-103">Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="49868-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="49868-104">`ICorDebugManagedCallback2` является логическим расширением интерфейса [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="49868-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49868-105">Методы</span><span class="sxs-lookup"><span data-stu-id="49868-105">Methods</span></span>  
  
|<span data-ttu-id="49868-106">Метод</span><span class="sxs-lookup"><span data-stu-id="49868-106">Method</span></span>|<span data-ttu-id="49868-107">Описание</span><span class="sxs-lookup"><span data-stu-id="49868-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49868-108">Метод ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="49868-108">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="49868-109">Уведомляет отладчик о том, что набор задач, связанных с указанным соединением, изменился.</span><span class="sxs-lookup"><span data-stu-id="49868-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="49868-110">Метод CreateConnection</span><span class="sxs-lookup"><span data-stu-id="49868-110">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="49868-111">Уведомляет отладчик о создании нового соединения.</span><span class="sxs-lookup"><span data-stu-id="49868-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="49868-112">Метод DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="49868-112">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="49868-113">Уведомляет отладчик о завершении указанного соединения.</span><span class="sxs-lookup"><span data-stu-id="49868-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="49868-114">Метод Exception</span><span class="sxs-lookup"><span data-stu-id="49868-114">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="49868-115">Уведомляет отладчик о запуске поиска обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="49868-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="49868-116">Метод ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="49868-116">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="49868-117">Предоставляет уведомление о состоянии во время процесса очистки исключения.</span><span class="sxs-lookup"><span data-stu-id="49868-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="49868-118">Метод FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="49868-118">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="49868-119">Уведомляет отладчик о том, что выполнение кода переключено на новую версию измененной функции.</span><span class="sxs-lookup"><span data-stu-id="49868-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="49868-120">Метод FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="49868-120">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="49868-121">Уведомляет отладчик о том, что выполнение кода достигло точки последовательности в более ранней версии измененной функции.</span><span class="sxs-lookup"><span data-stu-id="49868-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="49868-122">Метод MDANotification</span><span class="sxs-lookup"><span data-stu-id="49868-122">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="49868-123">Предоставляет уведомление о том, что при выполнении кода было обнаружено сообщение MDA.</span><span class="sxs-lookup"><span data-stu-id="49868-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49868-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="49868-124">Remarks</span></span>  
 <span data-ttu-id="49868-125">Интерфейс `ICorDebugManagedCallback2` расширяет интерфейс `ICorDebugManagedCallback` для поддержки новых событий отладки, появившихся в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="49868-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="49868-126">Отладчик должен реализовывать `ICorDebugManagedCallback2`, если он Отладка .NET Framework 2,0 приложений.</span><span class="sxs-lookup"><span data-stu-id="49868-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="49868-127">Экземпляр `ICorDebugManagedCallback` или `ICorDebugManagedCallback2` передается в качестве объекта обратного вызова в метод [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="49868-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49868-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="49868-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49868-129">Требования</span><span class="sxs-lookup"><span data-stu-id="49868-129">Requirements</span></span>  
 <span data-ttu-id="49868-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49868-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49868-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49868-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49868-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49868-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49868-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49868-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49868-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="49868-134">See also</span></span>

- [<span data-ttu-id="49868-135">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="49868-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="49868-136">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="49868-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="49868-137">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="49868-137">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
