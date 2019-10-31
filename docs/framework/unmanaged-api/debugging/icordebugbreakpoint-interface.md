---
title: Интерфейс ICorDebugBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 29bb84341c2cb4177c43f798d25a1a6d50099aa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122801"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="09971-102">Интерфейс ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="09971-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="09971-103">Представляет точку останова в функции или точку контрольного значения.</span><span class="sxs-lookup"><span data-stu-id="09971-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09971-104">Методы</span><span class="sxs-lookup"><span data-stu-id="09971-104">Methods</span></span>  
  
|<span data-ttu-id="09971-105">Метод</span><span class="sxs-lookup"><span data-stu-id="09971-105">Method</span></span>|<span data-ttu-id="09971-106">Описание</span><span class="sxs-lookup"><span data-stu-id="09971-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09971-107">Метод Activate</span><span class="sxs-lookup"><span data-stu-id="09971-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="09971-108">Задает активное состояние этого `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="09971-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="09971-109">Метод IsActive</span><span class="sxs-lookup"><span data-stu-id="09971-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="09971-110">Возвращает значение, указывающее, активна ли эта `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="09971-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09971-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="09971-111">Remarks</span></span>  
 <span data-ttu-id="09971-112">Точки останова не поддерживают непосредственно условные выражения.</span><span class="sxs-lookup"><span data-stu-id="09971-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="09971-113">Если требуется такая функциональность, отладчик должен реализовать его поверх `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="09971-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="09971-114">Интерфейс ICorDebugFunctionBreakpoint расширяет `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="09971-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09971-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="09971-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09971-116">Требования</span><span class="sxs-lookup"><span data-stu-id="09971-116">Requirements</span></span>  
 <span data-ttu-id="09971-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09971-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09971-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09971-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09971-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09971-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09971-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09971-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09971-121">См. также</span><span class="sxs-lookup"><span data-stu-id="09971-121">See also</span></span>

- [<span data-ttu-id="09971-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="09971-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
