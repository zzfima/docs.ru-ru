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
ms.openlocfilehash: bed2871c46712490bc4b0520fa1ab8023dbab5cf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794427"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="36326-102">Интерфейс ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="36326-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="36326-103">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="36326-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="36326-104">Этот интерфейс является подклассом интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="36326-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36326-105">Методы</span><span class="sxs-lookup"><span data-stu-id="36326-105">Methods</span></span>  
  
|<span data-ttu-id="36326-106">Метод</span><span class="sxs-lookup"><span data-stu-id="36326-106">Method</span></span>|<span data-ttu-id="36326-107">Описание</span><span class="sxs-lookup"><span data-stu-id="36326-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36326-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="36326-108">Next Method</span></span>](icordebugheapenum-next-method.md)|<span data-ttu-id="36326-109">Возвращает указанное число экземпляров [COR_HEAPOBJECT](cor-heapobject-structure.md) , содержащих сведения об объектах в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="36326-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36326-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="36326-110">Remarks</span></span>  
 <span data-ttu-id="36326-111">Интерфейс `ICorDebugHeapEnum` реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="36326-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="36326-112">Экземпляр `ICorDebugHeapEnum` заполняется [COR_HEAPOBJECT](cor-heapobject-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератехеап](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="36326-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="36326-113">Каждый экземпляр [COR_HEAPOBJECT](cor-heapobject-structure.md) в коллекции представляет собой либо динамический объект в куче, либо объект, который не является корневым для какого-либо объекта, но еще не был собран сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="36326-113">Each [COR_HEAPOBJECT](cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="36326-114">Объекты [COR_HEAPOBJECT](cor-heapobject-structure.md) в коллекции можно перечислить, вызвав метод [Икордебугхеапенум:: Next](icordebugheapenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="36326-114">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36326-115">Требования</span><span class="sxs-lookup"><span data-stu-id="36326-115">Requirements</span></span>  
 <span data-ttu-id="36326-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36326-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36326-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36326-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36326-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36326-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36326-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36326-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36326-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="36326-120">See also</span></span>

- [<span data-ttu-id="36326-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="36326-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
