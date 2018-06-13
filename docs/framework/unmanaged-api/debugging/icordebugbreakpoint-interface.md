---
title: ICorDebugBreakpoint интерфейс1
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
ms.openlocfilehash: 220cd1a41ed69325b557e6498a511865b78817ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404519"
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="9bd71-102">ICorDebugBreakpoint интерфейс1</span><span class="sxs-lookup"><span data-stu-id="9bd71-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="9bd71-103">Представляет точку останова в функции или контрольную точку значение.</span><span class="sxs-lookup"><span data-stu-id="9bd71-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9bd71-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9bd71-104">Methods</span></span>  
  
|<span data-ttu-id="9bd71-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9bd71-105">Method</span></span>|<span data-ttu-id="9bd71-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9bd71-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9bd71-107">Метод Activate</span><span class="sxs-lookup"><span data-stu-id="9bd71-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="9bd71-108">Задает активное состояние `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="9bd71-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="9bd71-109">Метод IsActive</span><span class="sxs-lookup"><span data-stu-id="9bd71-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="9bd71-110">Возвращает значение, указывающее, является ли это `ICorDebugBreakpoint` активен.</span><span class="sxs-lookup"><span data-stu-id="9bd71-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bd71-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="9bd71-111">Remarks</span></span>  
 <span data-ttu-id="9bd71-112">Точки останова напрямую не поддерживают условные выражения.</span><span class="sxs-lookup"><span data-stu-id="9bd71-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="9bd71-113">При необходимости такие функциональные возможности, отладчик должен реализовать его на основе `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="9bd71-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="9bd71-114">Icordebugfunctionbreakpoint-интерфейс расширяет `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="9bd71-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bd71-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9bd71-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bd71-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9bd71-116">Requirements</span></span>  
 <span data-ttu-id="9bd71-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bd71-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bd71-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bd71-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bd71-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bd71-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bd71-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bd71-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd71-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9bd71-121">See Also</span></span>  
 [<span data-ttu-id="9bd71-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9bd71-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
