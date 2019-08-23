---
title: Интерфейс ICorDebugFrameEnum
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9ea398c32762be31f93002533b15bcf3851b870
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910246"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="4634c-102">Интерфейс ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="4634c-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="4634c-103">Реализует методы ICorDebugEnum и перечисляет массивы ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="4634c-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4634c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4634c-104">Methods</span></span>  
  
|<span data-ttu-id="4634c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4634c-105">Method</span></span>|<span data-ttu-id="4634c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4634c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4634c-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="4634c-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="4634c-108">Возвращает указанное количество `ICorDebugFrame` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="4634c-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4634c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4634c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4634c-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4634c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4634c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4634c-111">Requirements</span></span>  
 <span data-ttu-id="4634c-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4634c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4634c-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="4634c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4634c-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="4634c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4634c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4634c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4634c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4634c-116">See also</span></span>

- [<span data-ttu-id="4634c-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4634c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
