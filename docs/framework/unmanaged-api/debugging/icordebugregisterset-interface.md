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
ms.openlocfilehash: 1ea0274adc12f3a99df0422bfc0b5180f0ef5596
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131375"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="a4b08-102">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="a4b08-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="a4b08-103">Представляет набор регистров, доступных на компьютере, который выполняет код в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a4b08-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4b08-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a4b08-104">Methods</span></span>  
  
|<span data-ttu-id="a4b08-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a4b08-105">Method</span></span>|<span data-ttu-id="a4b08-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a4b08-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4b08-107">Метод GetRegisters</span><span class="sxs-lookup"><span data-stu-id="a4b08-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="a4b08-108">Возвращает значение каждого регистра (на компьютере, выполняющем в данный момент код), который задается битовой маской.</span><span class="sxs-lookup"><span data-stu-id="a4b08-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="a4b08-109">Метод GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="a4b08-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="a4b08-110">Возвращает битовую маску, указывающую, какие регистры в этом `ICorDebugRegisterSet` доступны в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a4b08-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="a4b08-111">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="a4b08-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="a4b08-112">Возвращает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="a4b08-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="a4b08-113">Метод SetRegisters</span><span class="sxs-lookup"><span data-stu-id="a4b08-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="a4b08-114">Не реализовано для .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="a4b08-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="a4b08-115">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="a4b08-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="a4b08-116">Не реализовано для .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="a4b08-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4b08-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="a4b08-117">Remarks</span></span>  
 <span data-ttu-id="a4b08-118">Интерфейс `ICorDebugRegisterSet` поддерживает только 32-разрядные регистры.</span><span class="sxs-lookup"><span data-stu-id="a4b08-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="a4b08-119">Используйте интерфейс [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) на платформах, таких как IA-64, требующих дополнительных регистров.</span><span class="sxs-lookup"><span data-stu-id="a4b08-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4b08-120">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a4b08-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b08-121">Требования</span><span class="sxs-lookup"><span data-stu-id="a4b08-121">Requirements</span></span>  
 <span data-ttu-id="a4b08-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4b08-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b08-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4b08-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4b08-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4b08-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4b08-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b08-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b08-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a4b08-126">See also</span></span>

- [<span data-ttu-id="a4b08-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a4b08-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a4b08-128">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="a4b08-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
