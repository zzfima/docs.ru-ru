---
title: Интерфейс ICorDebugHeapEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79ef77e52e14fede9949121e7ec4575d10b820c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135854"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="ada6c-102">Интерфейс ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="ada6c-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="ada6c-103">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="ada6c-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="ada6c-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ada6c-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ada6c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ada6c-105">Methods</span></span>  
  
|<span data-ttu-id="ada6c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ada6c-106">Method</span></span>|<span data-ttu-id="ada6c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ada6c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ada6c-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="ada6c-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="ada6c-109">Возвращает заданное число [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляров, которые содержат сведения об объектах в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="ada6c-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ada6c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ada6c-110">Remarks</span></span>  
 <span data-ttu-id="ada6c-111">`ICorDebugHeapEnum` Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="ada6c-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="ada6c-112">`ICorDebugHeapEnum` Экземпляр заполняется [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляров путем вызова [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ada6c-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="ada6c-113">Каждый [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляра в коллекции представляет либо активный объект в куче, либо объект, который не является корневым, любой объект, но еще не были собраны сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="ada6c-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="ada6c-114">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объектов в коллекции можно перечислить, вызвав [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ada6c-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ada6c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ada6c-115">Requirements</span></span>  
 <span data-ttu-id="ada6c-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ada6c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ada6c-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ada6c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ada6c-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ada6c-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ada6c-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ada6c-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ada6c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ada6c-120">See also</span></span>

- [<span data-ttu-id="ada6c-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ada6c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
