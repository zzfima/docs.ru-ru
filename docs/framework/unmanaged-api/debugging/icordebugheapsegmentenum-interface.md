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
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138453"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="8239a-102">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="8239a-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="8239a-103">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="8239a-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="8239a-104">Этот интерфейс является подклассом интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="8239a-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8239a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8239a-105">Methods</span></span>  
  
|<span data-ttu-id="8239a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8239a-106">Method</span></span>|<span data-ttu-id="8239a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8239a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8239a-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="8239a-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="8239a-109">Возвращает указанное число экземпляров [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) , содержащих сведения о регионах управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="8239a-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8239a-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="8239a-110">Remarks</span></span>  
 <span data-ttu-id="8239a-111">Интерфейс `ICorDebugHeapSegmentEnum` реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="8239a-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="8239a-112">Экземпляр `ICorDebugHeapSegmentEnum` заполняется экземплярами [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) путем вызова метода [метод ICorDebugProcess5:: енумератехеапрегионс](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8239a-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="8239a-113">Объекты [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) в коллекции можно перечислить, вызвав метод [Икордебугхеапсегментенум:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8239a-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="8239a-114">Объект `ICorDebugHeapSegmentEnum` Collection перечисляет все области памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах.</span><span class="sxs-lookup"><span data-stu-id="8239a-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="8239a-115">Он может включать сведения о пустых или зарезервированных регионах памяти.</span><span class="sxs-lookup"><span data-stu-id="8239a-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8239a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="8239a-116">Requirements</span></span>  
 <span data-ttu-id="8239a-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8239a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8239a-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8239a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8239a-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8239a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8239a-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8239a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8239a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8239a-121">See also</span></span>

- [<span data-ttu-id="8239a-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8239a-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
