---
title: ICorDebugThread2 интерфейс1
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
ms.openlocfilehash: c348cf28a6330523d1a490c136a3214e37d13f4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423053"
---
# <a name="icordebugthread2-interface1"></a><span data-ttu-id="3ac18-102">ICorDebugThread2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="3ac18-102">ICorDebugThread2 Interface1</span></span>
<span data-ttu-id="3ac18-103">Служит логическим расширением интерфейса ICorDebugThread-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="3ac18-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ac18-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3ac18-104">Methods</span></span>  
  
|<span data-ttu-id="3ac18-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3ac18-105">Method</span></span>|<span data-ttu-id="3ac18-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3ac18-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ac18-107">Метод GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="3ac18-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="3ac18-108">Возвращает массив экземпляров COR_ACTIVE_FUNCTION, содержащих данные об активных функциях в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="3ac18-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="3ac18-109">Метод GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="3ac18-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="3ac18-110">Получает идентификатор подключения для данного `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="3ac18-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="3ac18-111">Метод GetTaskID</span><span class="sxs-lookup"><span data-stu-id="3ac18-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="3ac18-112">Возвращает идентификатор задачи для этого `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="3ac18-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="3ac18-113">Метод GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="3ac18-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="3ac18-114">Получает идентификатор потока операционной системы для данного `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="3ac18-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="3ac18-115">Метод InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="3ac18-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="3ac18-116">Позволяет отладчику перехватить текущее исключение в потоке.</span><span class="sxs-lookup"><span data-stu-id="3ac18-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ac18-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ac18-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ac18-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3ac18-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ac18-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3ac18-119">Requirements</span></span>  
 <span data-ttu-id="3ac18-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ac18-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ac18-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ac18-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ac18-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ac18-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ac18-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ac18-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac18-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3ac18-124">See Also</span></span>  
 [<span data-ttu-id="3ac18-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3ac18-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
