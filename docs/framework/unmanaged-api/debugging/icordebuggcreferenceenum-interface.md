---
title: Интерфейс ICorDebugGCReferenceEnum
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f09a8974dc1e8cb20185975c42c1cb3ad86a5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647158"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="f5288-102">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="f5288-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="f5288-103">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="f5288-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5288-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f5288-104">Methods</span></span>  
  
|<span data-ttu-id="f5288-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f5288-105">Method</span></span>|<span data-ttu-id="f5288-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f5288-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5288-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="f5288-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="f5288-108">Возвращает заданное число [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) экземпляров, которые содержат сведения об объектах, которые будут удалены сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="f5288-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5288-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5288-109">Remarks</span></span>  
 <span data-ttu-id="f5288-110">`ICorDebugGCReferenceEnum` Интерфейс реализует интерфейс «ICorDebugEnum».</span><span class="sxs-lookup"><span data-stu-id="f5288-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="f5288-111">`ICorDebugGCReferenceEnum` Экземпляр заполняется [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) экземпляров путем вызова [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f5288-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="f5288-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) объектов можно перечислить, вызвав [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f5288-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="f5288-113">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) объекты в коллекции, заполняется с помощью данного метода представляют три вида объектов:</span><span class="sxs-lookup"><span data-stu-id="f5288-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="f5288-114">Объекты из всех управляемых стеков.</span><span class="sxs-lookup"><span data-stu-id="f5288-114">Objects from all managed stacks.</span></span> <span data-ttu-id="f5288-115">Сюда входят активных ссылок в управляемом коде, а также объекты, созданные средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f5288-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="f5288-116">Объекты из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="f5288-116">Objects from the handle table.</span></span> <span data-ttu-id="f5288-117">Сюда входят строгих ссылок (`HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT`) и статические переменные в модуле.</span><span class="sxs-lookup"><span data-stu-id="f5288-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="f5288-118">Объекты из очереди метода завершения.</span><span class="sxs-lookup"><span data-stu-id="f5288-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="f5288-119">Обслуживает очередь метода завершения корневых объектов, пока не будет запущен финализатор.</span><span class="sxs-lookup"><span data-stu-id="f5288-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5288-120">Требования</span><span class="sxs-lookup"><span data-stu-id="f5288-120">Requirements</span></span>  
 <span data-ttu-id="f5288-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5288-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5288-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5288-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5288-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5288-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5288-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5288-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5288-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f5288-125">See also</span></span>

- [<span data-ttu-id="f5288-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f5288-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
