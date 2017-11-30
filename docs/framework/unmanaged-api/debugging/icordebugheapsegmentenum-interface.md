---
title: "Интерфейс ICorDebugHeapSegmentEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHealRegionEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapSegmentEnum
helpviewer_keywords: ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ca82e888ba078fcb8b855f5286bc14f970d64ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="a091b-102">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="a091b-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="a091b-103">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="a091b-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="a091b-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a091b-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a091b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a091b-105">Methods</span></span>  
  
|<span data-ttu-id="a091b-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a091b-106">Method</span></span>|<span data-ttu-id="a091b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a091b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a091b-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="a091b-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="a091b-109">Возвращает заданное число [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляры, которые содержат сведения об областях управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="a091b-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a091b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a091b-110">Remarks</span></span>  
 <span data-ttu-id="a091b-111">`ICorDebugHeapSegmentEnum` ICorDebugEnum-интерфейс реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a091b-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="a091b-112">`ICorDebugHeapSegmentEnum` Заполненный экземпляр [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляры путем вызова [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a091b-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="a091b-113">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объектов в коллекции могут быть перечислены путем вызова [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a091b-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="a091b-114">`ICorDebugHeapSegmentEnum` Объект коллекции перечисляет все области памяти, может содержать управляемые объекты, но не гарантирует фактически управляемые объекты находятся в этих областях.</span><span class="sxs-lookup"><span data-stu-id="a091b-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="a091b-115">Он может включать сведения об областях пустой или зарезервированное памяти.</span><span class="sxs-lookup"><span data-stu-id="a091b-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a091b-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a091b-116">Requirements</span></span>  
 <span data-ttu-id="a091b-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a091b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a091b-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a091b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a091b-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a091b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a091b-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a091b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a091b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a091b-121">See Also</span></span>  
 [<span data-ttu-id="a091b-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a091b-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
