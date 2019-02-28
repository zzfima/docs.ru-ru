---
title: Интерфейс ICorDebugThreadEnum
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b620357967d5d22148f64a3258fbb8dc52361d86
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981729"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="cbef9-102">Интерфейс ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="cbef9-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="cbef9-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="cbef9-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cbef9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cbef9-104">Methods</span></span>  
  
|<span data-ttu-id="cbef9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cbef9-105">Method</span></span>|<span data-ttu-id="cbef9-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="cbef9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cbef9-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="cbef9-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="cbef9-108">Возвращает заданное число `ICorDebugThread` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="cbef9-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbef9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="cbef9-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbef9-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="cbef9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbef9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cbef9-111">Requirements</span></span>  
 <span data-ttu-id="cbef9-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbef9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbef9-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbef9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbef9-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbef9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbef9-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbef9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbef9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cbef9-116">See also</span></span>
- [<span data-ttu-id="cbef9-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cbef9-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
