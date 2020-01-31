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
ms.openlocfilehash: f01c27376191c3a2dddf56dae4b26c8b5193c73e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788638"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="50fc8-102">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="50fc8-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="50fc8-103">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="50fc8-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50fc8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="50fc8-104">Methods</span></span>  
  
|<span data-ttu-id="50fc8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="50fc8-105">Method</span></span>|<span data-ttu-id="50fc8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="50fc8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50fc8-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="50fc8-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="50fc8-108">Возвращает указанное число экземпляров [COR_GC_REFERENCE](cor-gc-reference-structure.md) , содержащих сведения об объектах, которые будут собираться сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="50fc8-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50fc8-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="50fc8-109">Remarks</span></span>  
 <span data-ttu-id="50fc8-110">Интерфейс `ICorDebugGCReferenceEnum` реализует интерфейс "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="50fc8-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="50fc8-111">Экземпляр `ICorDebugGCReferenceEnum` заполняется [COR_GC_REFERENCE](cor-gc-reference-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератегкреференцес](icordebugprocess5-enumerategcreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="50fc8-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="50fc8-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) объекты можно перечислить, вызвав метод [Икордебуггкреференце:: Next](icordebuggcreferenceenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="50fc8-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="50fc8-113">[COR_GC_REFERENCE](cor-gc-reference-structure.md) объекты в коллекции, заполненной этим методом, представляют три вида объектов:</span><span class="sxs-lookup"><span data-stu-id="50fc8-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="50fc8-114">Объекты из всех управляемых стеков.</span><span class="sxs-lookup"><span data-stu-id="50fc8-114">Objects from all managed stacks.</span></span> <span data-ttu-id="50fc8-115">Сюда входят динамические ссылки в управляемом коде, а также объекты, созданные средой CLR.</span><span class="sxs-lookup"><span data-stu-id="50fc8-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="50fc8-116">Объекты из таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="50fc8-116">Objects from the handle table.</span></span> <span data-ttu-id="50fc8-117">Сюда входят строгие ссылки (`HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT`) и статические переменные в модуле.</span><span class="sxs-lookup"><span data-stu-id="50fc8-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="50fc8-118">Объекты из очереди метода завершения.</span><span class="sxs-lookup"><span data-stu-id="50fc8-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="50fc8-119">Очередь метода завершения помещает объекты в корни до запуска метода завершения.</span><span class="sxs-lookup"><span data-stu-id="50fc8-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50fc8-120">Требования</span><span class="sxs-lookup"><span data-stu-id="50fc8-120">Requirements</span></span>  
 <span data-ttu-id="50fc8-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50fc8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50fc8-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50fc8-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50fc8-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50fc8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50fc8-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50fc8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50fc8-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="50fc8-125">See also</span></span>

- [<span data-ttu-id="50fc8-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="50fc8-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
