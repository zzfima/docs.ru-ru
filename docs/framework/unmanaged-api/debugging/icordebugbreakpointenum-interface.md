---
title: ICorDebugBreakpointEnum интерфейс1
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
ms.openlocfilehash: 8299be7189522c1b508e647ae227de5d5dd68c73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403322"
---
# <a name="icordebugbreakpointenum-interface1"></a><span data-ttu-id="a0d17-102">ICorDebugBreakpointEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="a0d17-102">ICorDebugBreakpointEnum Interface1</span></span>
<span data-ttu-id="a0d17-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="a0d17-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0d17-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a0d17-104">Methods</span></span>  
  
|<span data-ttu-id="a0d17-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a0d17-105">Method</span></span>|<span data-ttu-id="a0d17-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a0d17-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0d17-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="a0d17-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="a0d17-108">Возвращает заданное число `ICorDebugBreakpoint` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="a0d17-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0d17-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0d17-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0d17-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a0d17-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0d17-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a0d17-111">Requirements</span></span>  
 <span data-ttu-id="a0d17-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0d17-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0d17-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0d17-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0d17-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0d17-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0d17-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0d17-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d17-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a0d17-116">See Also</span></span>  
 [<span data-ttu-id="a0d17-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a0d17-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
