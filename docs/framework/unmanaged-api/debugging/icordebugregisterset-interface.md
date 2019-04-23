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
ms.openlocfilehash: 7b0a5d80d984a3c696b178c4d8c936bd47354945
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135243"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="001d0-102">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="001d0-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="001d0-103">Представляет набор регистров, доступных на компьютере, на данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="001d0-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="001d0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="001d0-104">Methods</span></span>  
  
|<span data-ttu-id="001d0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="001d0-105">Method</span></span>|<span data-ttu-id="001d0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="001d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="001d0-107">Метод GetRegisters</span><span class="sxs-lookup"><span data-stu-id="001d0-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="001d0-108">Получает значение каждого из регистров (на компьютере, на который в данный момент выполняется код), который указан битовой маской.</span><span class="sxs-lookup"><span data-stu-id="001d0-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="001d0-109">Метод GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="001d0-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="001d0-110">Получает маску немного, указывающее, который регистрирует в этом `ICorDebugRegisterSet` в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="001d0-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="001d0-111">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="001d0-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="001d0-112">Получает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="001d0-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="001d0-113">Метод SetRegisters</span><span class="sxs-lookup"><span data-stu-id="001d0-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="001d0-114">Не реализован для .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="001d0-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="001d0-115">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="001d0-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="001d0-116">Не реализован для .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="001d0-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="001d0-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="001d0-117">Remarks</span></span>  
 <span data-ttu-id="001d0-118">`ICorDebugRegisterSet` Интерфейс поддерживает только 32-разрядные регистры.</span><span class="sxs-lookup"><span data-stu-id="001d0-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="001d0-119">Используйте [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) интерфейса на платформах, например IA-64, которые требуют дополнительные регистры.</span><span class="sxs-lookup"><span data-stu-id="001d0-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="001d0-120">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="001d0-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="001d0-121">Требования</span><span class="sxs-lookup"><span data-stu-id="001d0-121">Requirements</span></span>  
 <span data-ttu-id="001d0-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="001d0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="001d0-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="001d0-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="001d0-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="001d0-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="001d0-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="001d0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="001d0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="001d0-126">See also</span></span>

- [<span data-ttu-id="001d0-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="001d0-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="001d0-128">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="001d0-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
