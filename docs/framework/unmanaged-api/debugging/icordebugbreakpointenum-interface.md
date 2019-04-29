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
ms.openlocfilehash: 7fd42f13f699b0b79fd69311186f2b2ca0c9998a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645310"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="085de-102">Интерфейс ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="085de-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="085de-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="085de-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="085de-104">Методы</span><span class="sxs-lookup"><span data-stu-id="085de-104">Methods</span></span>  
  
|<span data-ttu-id="085de-105">Метод</span><span class="sxs-lookup"><span data-stu-id="085de-105">Method</span></span>|<span data-ttu-id="085de-106">Описание</span><span class="sxs-lookup"><span data-stu-id="085de-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="085de-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="085de-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="085de-108">Возвращает заданное число `ICorDebugBreakpoint` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="085de-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="085de-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="085de-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="085de-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="085de-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="085de-111">Требования</span><span class="sxs-lookup"><span data-stu-id="085de-111">Requirements</span></span>  
 <span data-ttu-id="085de-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="085de-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="085de-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="085de-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="085de-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="085de-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="085de-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="085de-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="085de-116">См. также</span><span class="sxs-lookup"><span data-stu-id="085de-116">See also</span></span>

- [<span data-ttu-id="085de-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="085de-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
