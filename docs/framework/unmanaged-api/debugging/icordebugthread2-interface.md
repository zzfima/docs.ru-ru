---
title: Интерфейс ICorDebugThread2
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82648714c375998e9daa1bb59cd9ebd9802b5794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993945"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="aef1e-102">Интерфейс ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="aef1e-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="aef1e-103">Служит логическим расширением ICorDebugThread-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="aef1e-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aef1e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="aef1e-104">Methods</span></span>  
  
|<span data-ttu-id="aef1e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="aef1e-105">Method</span></span>|<span data-ttu-id="aef1e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="aef1e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aef1e-107">Метод GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="aef1e-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="aef1e-108">Возвращает массив экземпляров COR_ACTIVE_FUNCTION, содержащих данные об активных функциях в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="aef1e-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="aef1e-109">Метод GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="aef1e-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="aef1e-110">Получает идентификатор подключения для данного `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="aef1e-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="aef1e-111">Метод GetTaskID</span><span class="sxs-lookup"><span data-stu-id="aef1e-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="aef1e-112">Получает идентификатор задачи для данного `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="aef1e-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="aef1e-113">Метод GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="aef1e-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="aef1e-114">Получает идентификатор потока операционной системы для данного `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="aef1e-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="aef1e-115">Метод InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="aef1e-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="aef1e-116">Позволяет отладчику перехватить текущее исключение в потоке.</span><span class="sxs-lookup"><span data-stu-id="aef1e-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aef1e-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="aef1e-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aef1e-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="aef1e-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aef1e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="aef1e-119">Requirements</span></span>  
 <span data-ttu-id="aef1e-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aef1e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aef1e-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aef1e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aef1e-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aef1e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aef1e-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aef1e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef1e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="aef1e-124">See also</span></span>

- [<span data-ttu-id="aef1e-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="aef1e-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
