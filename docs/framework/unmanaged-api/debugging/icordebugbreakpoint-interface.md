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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 608c2cea79c20a43d65fcbf37ba13242fa465100
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969315"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="085c8-102">Интерфейс ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="085c8-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="085c8-103">Представляет точку останова в функции или точку контрольного значения.</span><span class="sxs-lookup"><span data-stu-id="085c8-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="085c8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="085c8-104">Methods</span></span>  
  
|<span data-ttu-id="085c8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="085c8-105">Method</span></span>|<span data-ttu-id="085c8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="085c8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="085c8-107">Метод Activate</span><span class="sxs-lookup"><span data-stu-id="085c8-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="085c8-108">Задает активное состояние этого `ICorDebugBreakpoint`объекта.</span><span class="sxs-lookup"><span data-stu-id="085c8-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="085c8-109">Метод IsActive</span><span class="sxs-lookup"><span data-stu-id="085c8-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="085c8-110">Возвращает значение, указывающее, является ли `ICorDebugBreakpoint` этот объект активным.</span><span class="sxs-lookup"><span data-stu-id="085c8-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="085c8-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="085c8-111">Remarks</span></span>  
 <span data-ttu-id="085c8-112">Точки останова не поддерживают непосредственно условные выражения.</span><span class="sxs-lookup"><span data-stu-id="085c8-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="085c8-113">Если требуется такая функциональность, отладчик должен реализовать его поверх `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="085c8-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="085c8-114">Интерфейс ICorDebugFunctionBreakpoint расширяется `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="085c8-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="085c8-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="085c8-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="085c8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="085c8-116">Requirements</span></span>  
 <span data-ttu-id="085c8-117">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="085c8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="085c8-118">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="085c8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="085c8-119">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="085c8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="085c8-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="085c8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="085c8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="085c8-121">See also</span></span>

- [<span data-ttu-id="085c8-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="085c8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
