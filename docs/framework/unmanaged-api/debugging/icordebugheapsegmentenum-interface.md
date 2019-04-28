---
title: Интерфейс ICorDebugHeapSegmentEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73036d1c12c46cbfda8031073a005bc9b376040e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756216"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="7ce2c-102">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="7ce2c-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="7ce2c-103">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="7ce2c-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="7ce2c-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7ce2c-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ce2c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7ce2c-105">Methods</span></span>  
  
|<span data-ttu-id="7ce2c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="7ce2c-106">Method</span></span>|<span data-ttu-id="7ce2c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7ce2c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ce2c-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="7ce2c-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="7ce2c-109">Возвращает заданное число [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляров, которые содержат сведения о регионах управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="7ce2c-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ce2c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ce2c-110">Remarks</span></span>  
 <span data-ttu-id="7ce2c-111">`ICorDebugHeapSegmentEnum` Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="7ce2c-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="7ce2c-112">`ICorDebugHeapSegmentEnum` Экземпляр заполняется [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляров путем вызова [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7ce2c-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="7ce2c-113">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объектов в коллекции можно перечислить, вызвав [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7ce2c-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="7ce2c-114">`ICorDebugHeapSegmentEnum` Объект коллекции, перечисляет все области памяти, которые могут содержать управляемые объекты, но это не гарантирует, что управляемые объекты располагаются в этих регионах.</span><span class="sxs-lookup"><span data-stu-id="7ce2c-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="7ce2c-115">Он может содержать сведения об областях памяти пустой или зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="7ce2c-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ce2c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="7ce2c-116">Requirements</span></span>  
 <span data-ttu-id="7ce2c-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ce2c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ce2c-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ce2c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ce2c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ce2c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ce2c-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ce2c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce2c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7ce2c-121">See also</span></span>

- [<span data-ttu-id="7ce2c-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7ce2c-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
