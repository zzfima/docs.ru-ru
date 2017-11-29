---
title: "Интерфейс ICorDebugRegisterSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet
helpviewer_keywords: ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ccff205758dee2ffc6a6432ab20b3310147eb06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="c6781-102">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="c6781-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="c6781-103">Представляет набор регистров, доступных на компьютере, на данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="c6781-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6781-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c6781-104">Methods</span></span>  
  
|<span data-ttu-id="c6781-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c6781-105">Method</span></span>|<span data-ttu-id="c6781-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c6781-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6781-107">Метод GetRegisters</span><span class="sxs-lookup"><span data-stu-id="c6781-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="c6781-108">Получает значение каждого регистра (на компьютере, который в данный момент выполняется код), который указан битовой маской.</span><span class="sxs-lookup"><span data-stu-id="c6781-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="c6781-109">Метод GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="c6781-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="c6781-110">Возвращает маску немного, указывающее, регистрируется в это `ICorDebugRegisterSet` в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="c6781-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="c6781-111">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="c6781-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="c6781-112">Получает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="c6781-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="c6781-113">Метод SetRegisters</span><span class="sxs-lookup"><span data-stu-id="c6781-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="c6781-114">Не реализован для .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="c6781-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="c6781-115">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="c6781-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="c6781-116">Не реализован для .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="c6781-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6781-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6781-117">Remarks</span></span>  
 <span data-ttu-id="c6781-118">`ICorDebugRegisterSet` Интерфейс поддерживает только 32-разрядных регистров.</span><span class="sxs-lookup"><span data-stu-id="c6781-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="c6781-119">Используйте [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) интерфейса на платформах, например IA-64, требующих наличия дополнительных регистров.</span><span class="sxs-lookup"><span data-stu-id="c6781-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6781-120">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="c6781-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6781-121">Требования</span><span class="sxs-lookup"><span data-stu-id="c6781-121">Requirements</span></span>  
 <span data-ttu-id="c6781-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6781-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6781-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6781-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6781-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6781-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6781-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6781-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6781-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c6781-126">See Also</span></span>  
 [<span data-ttu-id="c6781-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c6781-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c6781-128">ICorDebugRegisterSet2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c6781-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
