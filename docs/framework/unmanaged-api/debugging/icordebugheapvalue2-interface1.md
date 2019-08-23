---
title: Интерфейс ICorDebugHeapValue2
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2
helpviewer_keywords:
- ICorDebugHeapValue2 interface [.NET Framework debugging]
ms.assetid: 87360a52-90b1-4ada-80c0-589a556116d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa872453ed72a3095c135aa25e81284610ad2436
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910210"
---
# <a name="icordebugheapvalue2-interface"></a><span data-ttu-id="1171d-102">Интерфейс ICorDebugHeapValue2</span><span class="sxs-lookup"><span data-stu-id="1171d-102">ICorDebugHeapValue2 Interface</span></span>

<span data-ttu-id="1171d-103">Расширение ICorDebugHeapValue, которое обеспечивает поддержку для дескрипторов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1171d-103">An extension of ICorDebugHeapValue that provides support for common language runtime (CLR) handles.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1171d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1171d-104">Methods</span></span>  
  
|<span data-ttu-id="1171d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1171d-105">Method</span></span>|<span data-ttu-id="1171d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1171d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1171d-107">Метод CreateHandle</span><span class="sxs-lookup"><span data-stu-id="1171d-107">CreateHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-createhandle-method.md)|<span data-ttu-id="1171d-108">Создает для этого `ICorDebugHeapValue2` объекта маркер указанного типа.</span><span class="sxs-lookup"><span data-stu-id="1171d-108">Creates a handle of the specified type for this `ICorDebugHeapValue2` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1171d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1171d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1171d-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="1171d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1171d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1171d-111">Requirements</span></span>  
 <span data-ttu-id="1171d-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1171d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1171d-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1171d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1171d-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="1171d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1171d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1171d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1171d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1171d-116">See also</span></span>

- [<span data-ttu-id="1171d-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1171d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
