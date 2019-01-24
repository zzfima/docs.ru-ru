---
title: Интерфейс ICorDebugRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8db70faf418bc89a4543845890f65e4859d507e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592605"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="36a2e-102">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="36a2e-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="36a2e-103">Представляет набор регистров, доступных на компьютере, на данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="36a2e-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36a2e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="36a2e-104">Methods</span></span>  
  
|<span data-ttu-id="36a2e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="36a2e-105">Method</span></span>|<span data-ttu-id="36a2e-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="36a2e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36a2e-107">Метод GetRegisters</span><span class="sxs-lookup"><span data-stu-id="36a2e-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="36a2e-108">Получает значение каждого из регистров (на компьютере, на который в данный момент выполняется код), который указан битовой маской.</span><span class="sxs-lookup"><span data-stu-id="36a2e-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="36a2e-109">Метод GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="36a2e-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="36a2e-110">Получает маску немного, указывающее, который регистрирует в этом `ICorDebugRegisterSet` в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="36a2e-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="36a2e-111">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="36a2e-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="36a2e-112">Получает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="36a2e-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="36a2e-113">Метод SetRegisters</span><span class="sxs-lookup"><span data-stu-id="36a2e-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="36a2e-114">Не реализован для .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="36a2e-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="36a2e-115">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="36a2e-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="36a2e-116">Не реализован для .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="36a2e-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36a2e-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="36a2e-117">Remarks</span></span>  
 <span data-ttu-id="36a2e-118">`ICorDebugRegisterSet` Интерфейс поддерживает только 32-разрядные регистры.</span><span class="sxs-lookup"><span data-stu-id="36a2e-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="36a2e-119">Используйте [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) интерфейса на платформах, например IA-64, которые требуют дополнительные регистры.</span><span class="sxs-lookup"><span data-stu-id="36a2e-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36a2e-120">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="36a2e-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36a2e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="36a2e-121">Requirements</span></span>  
 <span data-ttu-id="36a2e-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36a2e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36a2e-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36a2e-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36a2e-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36a2e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36a2e-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36a2e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a2e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="36a2e-126">See also</span></span>
- [<span data-ttu-id="36a2e-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="36a2e-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="36a2e-128">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="36a2e-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
