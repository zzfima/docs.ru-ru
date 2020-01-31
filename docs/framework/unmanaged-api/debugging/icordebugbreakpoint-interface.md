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
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784378"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="0fe6c-102">Интерфейс ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0fe6c-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="0fe6c-103">Представляет точку останова в функции или точку контрольного значения.</span><span class="sxs-lookup"><span data-stu-id="0fe6c-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0fe6c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0fe6c-104">Methods</span></span>  
  
|<span data-ttu-id="0fe6c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0fe6c-105">Method</span></span>|<span data-ttu-id="0fe6c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0fe6c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0fe6c-107">Метод Activate</span><span class="sxs-lookup"><span data-stu-id="0fe6c-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="0fe6c-108">Задает активное состояние этого `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="0fe6c-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="0fe6c-109">Метод IsActive</span><span class="sxs-lookup"><span data-stu-id="0fe6c-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="0fe6c-110">Возвращает значение, указывающее, активна ли эта `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="0fe6c-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fe6c-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="0fe6c-111">Remarks</span></span>  
 <span data-ttu-id="0fe6c-112">Точки останова не поддерживают непосредственно условные выражения.</span><span class="sxs-lookup"><span data-stu-id="0fe6c-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="0fe6c-113">Если требуется такая функциональность, отладчик должен реализовать его поверх `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="0fe6c-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="0fe6c-114">Интерфейс ICorDebugFunctionBreakpoint расширяет `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="0fe6c-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fe6c-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0fe6c-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fe6c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="0fe6c-116">Requirements</span></span>  
 <span data-ttu-id="0fe6c-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fe6c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fe6c-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fe6c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fe6c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fe6c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fe6c-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fe6c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe6c-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="0fe6c-121">See also</span></span>

- [<span data-ttu-id="0fe6c-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0fe6c-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
