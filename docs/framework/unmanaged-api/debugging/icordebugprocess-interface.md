---
title: ICorDebugProcess интерфейс1
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e4e3854a850c9639e93c8db2ec8ccd567b242b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423173"
---
# <a name="icordebugprocess-interface1"></a><span data-ttu-id="3d28c-102">ICorDebugProcess интерфейс1</span><span class="sxs-lookup"><span data-stu-id="3d28c-102">ICorDebugProcess Interface1</span></span>
<span data-ttu-id="3d28c-103">Представляет процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="3d28c-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="3d28c-104">Этот интерфейс является подклассом ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="3d28c-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d28c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3d28c-105">Methods</span></span>  
  
|<span data-ttu-id="3d28c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="3d28c-106">Method</span></span>|<span data-ttu-id="3d28c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3d28c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d28c-108">Метод ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="3d28c-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="3d28c-109">Очищает текущее неуправляемое исключение в данном потоке.</span><span class="sxs-lookup"><span data-stu-id="3d28c-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="3d28c-110">Метод EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="3d28c-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="3d28c-111">Включает и отключает отправку сообщений журнала для отладчика.</span><span class="sxs-lookup"><span data-stu-id="3d28c-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="3d28c-112">Метод EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="3d28c-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="3d28c-113">Перечисляет все домены приложений в процессе.</span><span class="sxs-lookup"><span data-stu-id="3d28c-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="3d28c-114">Метод EnumerateObjects</span><span class="sxs-lookup"><span data-stu-id="3d28c-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="3d28c-115">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="3d28c-115">Not implemented.</span></span>|  
|[<span data-ttu-id="3d28c-116">Метод GetHandle</span><span class="sxs-lookup"><span data-stu-id="3d28c-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="3d28c-117">Получает дескриптор процесса.</span><span class="sxs-lookup"><span data-stu-id="3d28c-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="3d28c-118">Метод GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="3d28c-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="3d28c-119">Получает идентификатор потока операционной системы (ОС) для вспомогательный внутренний поток отладчика.</span><span class="sxs-lookup"><span data-stu-id="3d28c-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="3d28c-120">Метод GetID</span><span class="sxs-lookup"><span data-stu-id="3d28c-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="3d28c-121">Получает идентификатор процесса операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="3d28c-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="3d28c-122">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="3d28c-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="3d28c-123">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="3d28c-123">Not implemented.</span></span>|  
|[<span data-ttu-id="3d28c-124">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="3d28c-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="3d28c-125">Возвращает ICorDebugThread идентификатор экземпляра, имеющий указанный потоке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3d28c-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="3d28c-126">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="3d28c-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="3d28c-127">Возвращает контекст для данного потока.</span><span class="sxs-lookup"><span data-stu-id="3d28c-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="3d28c-128">Метод IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="3d28c-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="3d28c-129">Определяет, является ли этот поток приостановлен в результате остановки процесса отладчиком.</span><span class="sxs-lookup"><span data-stu-id="3d28c-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="3d28c-130">Метод IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="3d28c-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="3d28c-131">Определяет, является ли адрес в заглушке, что вызовет переход к управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="3d28c-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="3d28c-132">Метод ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="3d28c-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="3d28c-133">Задает уровень важности указанного переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="3d28c-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="3d28c-134">Метод ReadMemory</span><span class="sxs-lookup"><span data-stu-id="3d28c-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="3d28c-135">Считывает памяти из процесса.</span><span class="sxs-lookup"><span data-stu-id="3d28c-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="3d28c-136">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="3d28c-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="3d28c-137">Задает контекст для данного потока.</span><span class="sxs-lookup"><span data-stu-id="3d28c-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="3d28c-138">Метод ThreadForFiberCookie</span><span class="sxs-lookup"><span data-stu-id="3d28c-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="3d28c-139">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="3d28c-139">Deprecated.</span></span>|  
|[<span data-ttu-id="3d28c-140">Метод WriteMemory</span><span class="sxs-lookup"><span data-stu-id="3d28c-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="3d28c-141">Записывает данные в область памяти в процессе.</span><span class="sxs-lookup"><span data-stu-id="3d28c-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d28c-142">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d28c-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d28c-143">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3d28c-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d28c-144">Требования</span><span class="sxs-lookup"><span data-stu-id="3d28c-144">Requirements</span></span>  
 <span data-ttu-id="3d28c-145">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d28c-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d28c-146">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d28c-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d28c-147">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d28c-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d28c-148">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d28c-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d28c-149">См. также</span><span class="sxs-lookup"><span data-stu-id="3d28c-149">See Also</span></span>  
 [<span data-ttu-id="3d28c-150">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="3d28c-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="3d28c-151">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3d28c-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
