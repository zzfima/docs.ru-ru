---
title: Интерфейс ICorDebugBreakpointEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: 5fb4a8a508cde4455bbee8c08432d3549e3fac43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122758"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="24519-102">Интерфейс ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="24519-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="24519-103">Реализует методы ICorDebugEnum и перечисляет Икордебугбреакпоинт массивы.</span><span class="sxs-lookup"><span data-stu-id="24519-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24519-104">Методы</span><span class="sxs-lookup"><span data-stu-id="24519-104">Methods</span></span>  
  
|<span data-ttu-id="24519-105">Метод</span><span class="sxs-lookup"><span data-stu-id="24519-105">Method</span></span>|<span data-ttu-id="24519-106">Описание</span><span class="sxs-lookup"><span data-stu-id="24519-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24519-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="24519-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="24519-108">Возвращает указанное число экземпляров `ICorDebugBreakpoint` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="24519-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24519-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="24519-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24519-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="24519-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24519-111">Требования</span><span class="sxs-lookup"><span data-stu-id="24519-111">Requirements</span></span>  
 <span data-ttu-id="24519-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24519-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24519-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24519-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24519-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24519-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24519-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24519-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24519-116">См. также</span><span class="sxs-lookup"><span data-stu-id="24519-116">See also</span></span>

- [<span data-ttu-id="24519-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="24519-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
