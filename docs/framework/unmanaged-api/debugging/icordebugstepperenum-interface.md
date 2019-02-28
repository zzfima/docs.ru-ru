---
title: Интерфейс ICorDebugStepperEnum
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum
helpviewer_keywords:
- ICorDebugStepperEnum interface [.NET Framework debugging]
ms.assetid: 988718c1-1a4a-40f2-a04c-7d67e5cfe1e2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad6c48b08fbdc660fdaa7ce5bfda3a6c0529662a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980734"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="7e30c-102">Интерфейс ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="7e30c-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="7e30c-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugStepper.</span><span class="sxs-lookup"><span data-stu-id="7e30c-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e30c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7e30c-104">Methods</span></span>  
  
|<span data-ttu-id="7e30c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7e30c-105">Method</span></span>|<span data-ttu-id="7e30c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7e30c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e30c-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="7e30c-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="7e30c-108">Возвращает заданное число `ICorDebugStepper` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="7e30c-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e30c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e30c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e30c-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7e30c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e30c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7e30c-111">Requirements</span></span>  
 <span data-ttu-id="7e30c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e30c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e30c-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e30c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e30c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e30c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e30c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e30c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e30c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7e30c-116">See also</span></span>
- [<span data-ttu-id="7e30c-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7e30c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
