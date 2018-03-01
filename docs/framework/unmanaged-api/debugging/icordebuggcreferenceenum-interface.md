---
title: "Интерфейс ICorDebugGCReferenceEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1afe52c3df8f61b234b3c68ee819ba8389593c82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="67527-102">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="67527-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="67527-103">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="67527-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67527-104">Методы</span><span class="sxs-lookup"><span data-stu-id="67527-104">Methods</span></span>  
  
|<span data-ttu-id="67527-105">Метод</span><span class="sxs-lookup"><span data-stu-id="67527-105">Method</span></span>|<span data-ttu-id="67527-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="67527-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67527-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="67527-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="67527-108">Возвращает заданное число [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) экземпляров, которые содержат сведения об объектах, которые будет собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="67527-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67527-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="67527-109">Remarks</span></span>  
 <span data-ttu-id="67527-110">`ICorDebugGCReferenceEnum` Интерфейс реализует интерфейс «ICorDebugEnum».</span><span class="sxs-lookup"><span data-stu-id="67527-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="67527-111">`ICorDebugGCReferenceEnum` Заполненный экземпляр [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) экземпляры путем вызова [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="67527-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="67527-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) объектов могут быть перечислены путем вызова [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="67527-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="67527-113">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) объектов в коллекции, который заполняется с помощью данного метода представляют собой три типа объектов:</span><span class="sxs-lookup"><span data-stu-id="67527-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
-   <span data-ttu-id="67527-114">Объекты из всех управляемых стеков.</span><span class="sxs-lookup"><span data-stu-id="67527-114">Objects from all managed stacks.</span></span> <span data-ttu-id="67527-115">В нем активных ссылок в управляемом коде, а также объекты, созданные средой CLR.</span><span class="sxs-lookup"><span data-stu-id="67527-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="67527-116">Объекты из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="67527-116">Objects from the handle table.</span></span> <span data-ttu-id="67527-117">Сюда входят строгих ссылок (`HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT`) и статические переменные в модуле.</span><span class="sxs-lookup"><span data-stu-id="67527-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="67527-118">Объекты из очереди метода завершения.</span><span class="sxs-lookup"><span data-stu-id="67527-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="67527-119">Очереди метода завершения корневых объектов до выполнения метода завершения.</span><span class="sxs-lookup"><span data-stu-id="67527-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67527-120">Требования</span><span class="sxs-lookup"><span data-stu-id="67527-120">Requirements</span></span>  
 <span data-ttu-id="67527-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67527-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67527-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67527-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67527-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67527-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67527-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67527-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67527-125">См. также</span><span class="sxs-lookup"><span data-stu-id="67527-125">See Also</span></span>  
 [<span data-ttu-id="67527-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="67527-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
