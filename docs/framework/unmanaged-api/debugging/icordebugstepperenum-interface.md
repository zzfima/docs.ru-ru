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
ms.openlocfilehash: 7336f958019c2f696a9b1a26b075c076cfc84f5d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953016"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="5d999-102">Интерфейс ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="5d999-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="5d999-103">Реализует методы ICorDebugEnum и перечисляет массивы ICorDebugStepper.</span><span class="sxs-lookup"><span data-stu-id="5d999-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d999-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5d999-104">Methods</span></span>  
  
|<span data-ttu-id="5d999-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5d999-105">Method</span></span>|<span data-ttu-id="5d999-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5d999-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d999-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="5d999-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="5d999-108">Возвращает указанное количество `ICorDebugStepper` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="5d999-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d999-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d999-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d999-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5d999-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d999-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5d999-111">Requirements</span></span>  
 <span data-ttu-id="5d999-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d999-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d999-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5d999-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d999-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="5d999-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d999-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d999-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d999-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5d999-116">See also</span></span>

- [<span data-ttu-id="5d999-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5d999-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
