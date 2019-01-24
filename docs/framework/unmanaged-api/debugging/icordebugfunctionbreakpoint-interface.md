---
title: Интерфейс1 ICorDebugFunctionBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8403873fb7bc15e3109821bf738d7b68e20f878
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662690"
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="a6255-102">Интерфейс1 ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a6255-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="a6255-103">Расширяет интерфейс ICorDebugBreakpoint для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="a6255-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6255-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a6255-104">Methods</span></span>  
  
|<span data-ttu-id="a6255-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a6255-105">Method</span></span>|<span data-ttu-id="a6255-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="a6255-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6255-107">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="a6255-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="a6255-108">Получает указатель на интерфейс ICorDebugFunction, который ссылается на функцию, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="a6255-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="a6255-109">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="a6255-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="a6255-110">Получает смещение точки останова в функции.</span><span class="sxs-lookup"><span data-stu-id="a6255-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6255-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6255-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6255-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a6255-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6255-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a6255-113">Requirements</span></span>  
 <span data-ttu-id="a6255-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6255-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6255-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6255-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6255-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6255-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6255-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6255-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6255-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a6255-118">See also</span></span>
- [<span data-ttu-id="a6255-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a6255-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
