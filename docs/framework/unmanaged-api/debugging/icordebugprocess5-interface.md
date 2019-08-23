---
title: Интерфейс ICorDebugProcess5
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31ecea4857dabc55e8acd3c22a025895a686efcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931088"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="e1a9b-102">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="e1a9b-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="e1a9b-103">Расширяет интерфейс ICorDebugProcess для поддержки доступа к управляемой куче, предоставляет сведения о сборке мусора управляемых объектов и определяет, загружает ли отладчик изображения из локального кэша образов в машинном код.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1a9b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e1a9b-104">Methods</span></span>  
  
|<span data-ttu-id="e1a9b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e1a9b-105">Method</span></span>|<span data-ttu-id="e1a9b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e1a9b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1a9b-107">Метод EnableNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="e1a9b-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="e1a9b-108">Задает значение, определяющее, как приложение загружает образы в машинном кодах при выполнении в управляемом отладчике.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="e1a9b-109">Метод EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="e1a9b-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="e1a9b-110">Возвращает перечислитель для всех объектов, которые должны быть собраны в процессе сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="e1a9b-111">Метод EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="e1a9b-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="e1a9b-112">Возвращает перечислитель для дескрипторов объектов в процессе.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="e1a9b-113">Метод EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="e1a9b-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="e1a9b-114">Возвращает перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="e1a9b-115">Метод EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="e1a9b-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="e1a9b-116">Возвращает перечислитель для регионов управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="e1a9b-117">Метод GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="e1a9b-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="e1a9b-118">Возвращает сведения о макете массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="e1a9b-119">Метод GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="e1a9b-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="e1a9b-120">Возвращает указатель на структуру [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) , содержащую сведения об объектах, которые должны быть собраны сборщиком мусора в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="e1a9b-121">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="e1a9b-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="e1a9b-122">Возвращает указатель на объект в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="e1a9b-123">Метод GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="e1a9b-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="e1a9b-124">Возвращает указатель на массив, содержащий сведения о поле для типа на основе его идентификатора типа.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="e1a9b-125">Метод GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="e1a9b-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="e1a9b-126">Возвращает объект типа, предоставляющий сведения об объекте на основе его идентификаторов типов.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="e1a9b-127">Метод GetTypeID</span><span class="sxs-lookup"><span data-stu-id="e1a9b-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="e1a9b-128">Возвращает идентификатор типа для объекта по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="e1a9b-129">Метод GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="e1a9b-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="e1a9b-130">Возвращает сведения о макете объекта в памяти на основе его идентификатора типа.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1a9b-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1a9b-131">Remarks</span></span>  
 <span data-ttu-id="e1a9b-132">Этот интерфейс логически расширяет интерфейсы ICorDebugProcess, ICorDebugProcess2 и [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e1a9b-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1a9b-133">Этот интерфейс не поддерживает удаленный вызов на другом компьютере или другом процессе.</span><span class="sxs-lookup"><span data-stu-id="e1a9b-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1a9b-134">Требования</span><span class="sxs-lookup"><span data-stu-id="e1a9b-134">Requirements</span></span>  
 <span data-ttu-id="e1a9b-135">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1a9b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a9b-136">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e1a9b-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1a9b-137">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="e1a9b-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1a9b-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a9b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a9b-139">См. также</span><span class="sxs-lookup"><span data-stu-id="e1a9b-139">See also</span></span>

- [<span data-ttu-id="e1a9b-140">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e1a9b-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e1a9b-141">Отладка</span><span class="sxs-lookup"><span data-stu-id="e1a9b-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
