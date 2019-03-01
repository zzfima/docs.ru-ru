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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b5268eb4240f7c3ff254f4d3d9a13ab494530a1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968742"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="c0ccd-102">Интерфейс ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="c0ccd-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="c0ccd-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="c0ccd-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0ccd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c0ccd-104">Methods</span></span>  
  
|<span data-ttu-id="c0ccd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c0ccd-105">Method</span></span>|<span data-ttu-id="c0ccd-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="c0ccd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0ccd-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="c0ccd-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="c0ccd-108">Возвращает заданное число `ICorDebugBreakpoint` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="c0ccd-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0ccd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0ccd-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0ccd-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="c0ccd-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ccd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c0ccd-111">Requirements</span></span>  
 <span data-ttu-id="c0ccd-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ccd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ccd-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0ccd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0ccd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0ccd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0ccd-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ccd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ccd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c0ccd-116">See also</span></span>
- [<span data-ttu-id="c0ccd-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c0ccd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
