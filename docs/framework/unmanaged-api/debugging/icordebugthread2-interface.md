---
title: Интерфейс1 ICorDebugThread2
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
ms.openlocfilehash: 3826bfd16d3cf7534a6e920c516987908547b419
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716156"
---
# <a name="icordebugthread2-interface1"></a><span data-ttu-id="05b65-102">Интерфейс1 ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="05b65-102">ICorDebugThread2 Interface1</span></span>
<span data-ttu-id="05b65-103">Служит логическим расширением ICorDebugThread-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="05b65-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05b65-104">Методы</span><span class="sxs-lookup"><span data-stu-id="05b65-104">Methods</span></span>  
  
|<span data-ttu-id="05b65-105">Метод</span><span class="sxs-lookup"><span data-stu-id="05b65-105">Method</span></span>|<span data-ttu-id="05b65-106">Описание</span><span class="sxs-lookup"><span data-stu-id="05b65-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05b65-107">Метод GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="05b65-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="05b65-108">Возвращает массив экземпляров COR_ACTIVE_FUNCTION, содержащих данные об активных функциях в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="05b65-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="05b65-109">Метод GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="05b65-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="05b65-110">Получает идентификатор подключения для данного `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="05b65-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="05b65-111">Метод GetTaskID</span><span class="sxs-lookup"><span data-stu-id="05b65-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="05b65-112">Получает идентификатор задачи для данного `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="05b65-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="05b65-113">Метод GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="05b65-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="05b65-114">Получает идентификатор потока операционной системы для данного `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="05b65-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="05b65-115">Метод InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="05b65-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="05b65-116">Позволяет отладчику перехватить текущее исключение в потоке.</span><span class="sxs-lookup"><span data-stu-id="05b65-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05b65-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="05b65-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05b65-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="05b65-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05b65-119">Требования</span><span class="sxs-lookup"><span data-stu-id="05b65-119">Requirements</span></span>  
 <span data-ttu-id="05b65-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05b65-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05b65-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05b65-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05b65-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05b65-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05b65-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05b65-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b65-124">См. также</span><span class="sxs-lookup"><span data-stu-id="05b65-124">See also</span></span>
- [<span data-ttu-id="05b65-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="05b65-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
