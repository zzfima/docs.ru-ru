---
title: Интерфейс ICorDebugFunctionBreakpoint
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
ms.openlocfilehash: ed09b4f9be71c7f85714b9ee26d45018410fda42
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917069"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="f56f5-102">Интерфейс ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f56f5-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="f56f5-103">Расширяет интерфейс Икордебугбреакпоинт для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="f56f5-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f56f5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f56f5-104">Methods</span></span>  
  
|<span data-ttu-id="f56f5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f56f5-105">Method</span></span>|<span data-ttu-id="f56f5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f56f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f56f5-107">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="f56f5-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="f56f5-108">Возвращает указатель на интерфейс ICorDebugFunction, ссылающийся на функцию, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="f56f5-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="f56f5-109">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="f56f5-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="f56f5-110">Возвращает смещение точки останова внутри функции.</span><span class="sxs-lookup"><span data-stu-id="f56f5-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f56f5-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f56f5-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f56f5-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f56f5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f56f5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f56f5-113">Requirements</span></span>  
 <span data-ttu-id="f56f5-114">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f56f5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f56f5-115">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f56f5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f56f5-116">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f56f5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f56f5-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f56f5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f56f5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f56f5-118">See also</span></span>

- [<span data-ttu-id="f56f5-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f56f5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
