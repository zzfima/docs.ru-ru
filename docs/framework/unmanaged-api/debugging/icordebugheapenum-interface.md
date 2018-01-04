---
title: "Интерфейс ICorDebugHeapEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapEnum
helpviewer_keywords: ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e317cb24e0eeaeaa38833433791eb546ee3c0478
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="53d91-102">Интерфейс ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="53d91-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="53d91-103">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="53d91-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="53d91-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="53d91-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53d91-105">Методы</span><span class="sxs-lookup"><span data-stu-id="53d91-105">Methods</span></span>  
  
|<span data-ttu-id="53d91-106">Метод</span><span class="sxs-lookup"><span data-stu-id="53d91-106">Method</span></span>|<span data-ttu-id="53d91-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="53d91-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53d91-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="53d91-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="53d91-109">Возвращает заданное число [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляров, которые содержат сведения об объектах в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="53d91-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53d91-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="53d91-110">Remarks</span></span>  
 <span data-ttu-id="53d91-111">`ICorDebugHeapEnum` ICorDebugEnum-интерфейс реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="53d91-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="53d91-112">`ICorDebugHeapEnum` Заполненный экземпляр [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляры путем вызова [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="53d91-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="53d91-113">Каждый [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляра в коллекции представляет либо активный объект в куче, либо объект, который не связан с любым объектом, но еще не были собраны сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="53d91-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="53d91-114">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объектов в коллекции могут быть перечислены путем вызова [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="53d91-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53d91-115">Требования</span><span class="sxs-lookup"><span data-stu-id="53d91-115">Requirements</span></span>  
 <span data-ttu-id="53d91-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53d91-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53d91-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53d91-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53d91-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53d91-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53d91-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53d91-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d91-120">См. также</span><span class="sxs-lookup"><span data-stu-id="53d91-120">See Also</span></span>  
 [<span data-ttu-id="53d91-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="53d91-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
