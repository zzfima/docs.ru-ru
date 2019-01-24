---
title: Интерфейс1 ICorDebugBreakpoint
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
ms.openlocfilehash: a222f578daed0ab81e2136e00d6f9b032acd95fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744938"
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="9865a-102">Интерфейс1 ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9865a-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="9865a-103">Представляет точку останова в функции или контрольную точку значение.</span><span class="sxs-lookup"><span data-stu-id="9865a-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9865a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9865a-104">Methods</span></span>  
  
|<span data-ttu-id="9865a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9865a-105">Method</span></span>|<span data-ttu-id="9865a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9865a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9865a-107">Метод Activate</span><span class="sxs-lookup"><span data-stu-id="9865a-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="9865a-108">Задает активное состояние `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="9865a-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="9865a-109">Метод IsActive</span><span class="sxs-lookup"><span data-stu-id="9865a-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="9865a-110">Получает значение, указывающее, является ли это `ICorDebugBreakpoint` активен.</span><span class="sxs-lookup"><span data-stu-id="9865a-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9865a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="9865a-111">Remarks</span></span>  
 <span data-ttu-id="9865a-112">Точки останова непосредственно не поддерживают условные выражения.</span><span class="sxs-lookup"><span data-stu-id="9865a-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="9865a-113">Если требуется такая функция, отладчик должен реализовать его поверх имени `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="9865a-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="9865a-114">Расширяет интерфейс ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="9865a-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9865a-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9865a-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9865a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9865a-116">Requirements</span></span>  
 <span data-ttu-id="9865a-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9865a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9865a-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9865a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9865a-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9865a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9865a-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9865a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9865a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9865a-121">See also</span></span>
- [<span data-ttu-id="9865a-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9865a-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
