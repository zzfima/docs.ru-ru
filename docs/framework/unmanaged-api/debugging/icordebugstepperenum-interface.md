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
ms.openlocfilehash: 89552a099241f1bec61f9aa8a8321ef9932e886c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173229"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="08fdc-102">Интерфейс ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="08fdc-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="08fdc-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugStepper.</span><span class="sxs-lookup"><span data-stu-id="08fdc-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08fdc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="08fdc-104">Methods</span></span>  
  
|<span data-ttu-id="08fdc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="08fdc-105">Method</span></span>|<span data-ttu-id="08fdc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="08fdc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08fdc-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="08fdc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="08fdc-108">Возвращает заданное число `ICorDebugStepper` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="08fdc-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08fdc-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="08fdc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08fdc-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="08fdc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08fdc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="08fdc-111">Requirements</span></span>  
 <span data-ttu-id="08fdc-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08fdc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08fdc-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08fdc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08fdc-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08fdc-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="08fdc-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="08fdc-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08fdc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="08fdc-116">See also</span></span>

- [<span data-ttu-id="08fdc-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="08fdc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
