---
title: "ICorDebugBreakpoint интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint
helpviewer_keywords: ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b78b61b99fb8f236e787f3acbf993d0a1c57e797
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="50b87-102">ICorDebugBreakpoint интерфейс1</span><span class="sxs-lookup"><span data-stu-id="50b87-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="50b87-103">Представляет точку останова в функции или контрольную точку значение.</span><span class="sxs-lookup"><span data-stu-id="50b87-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50b87-104">Методы</span><span class="sxs-lookup"><span data-stu-id="50b87-104">Methods</span></span>  
  
|<span data-ttu-id="50b87-105">Метод</span><span class="sxs-lookup"><span data-stu-id="50b87-105">Method</span></span>|<span data-ttu-id="50b87-106">Описание</span><span class="sxs-lookup"><span data-stu-id="50b87-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50b87-107">Activate-метод</span><span class="sxs-lookup"><span data-stu-id="50b87-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="50b87-108">Задает активное состояние `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="50b87-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="50b87-109">IsActive-метод</span><span class="sxs-lookup"><span data-stu-id="50b87-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="50b87-110">Возвращает значение, указывающее, является ли это `ICorDebugBreakpoint` активен.</span><span class="sxs-lookup"><span data-stu-id="50b87-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50b87-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="50b87-111">Remarks</span></span>  
 <span data-ttu-id="50b87-112">Точки останова напрямую не поддерживают условные выражения.</span><span class="sxs-lookup"><span data-stu-id="50b87-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="50b87-113">При необходимости такие функциональные возможности, отладчик должен реализовать его на основе `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="50b87-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="50b87-114">Icordebugfunctionbreakpoint-интерфейс расширяет `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="50b87-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50b87-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="50b87-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50b87-116">Требования</span><span class="sxs-lookup"><span data-stu-id="50b87-116">Requirements</span></span>  
 <span data-ttu-id="50b87-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50b87-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50b87-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50b87-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50b87-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50b87-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50b87-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50b87-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b87-121">См. также</span><span class="sxs-lookup"><span data-stu-id="50b87-121">See Also</span></span>  
 [<span data-ttu-id="50b87-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="50b87-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
