---
title: "Интерфейс ICorDebugProcess5"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e26f50967f0fb70e0593584e3f175d20a7b213e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="2c84c-102">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="2c84c-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="2c84c-103">Чтобы определить, является ли отладчику загружать образы из приложения локального кэша машинных образов и расширяет их возможности ICorDebugProcess-интерфейс для поддержки доступа к управляемой куче, для предоставления сведений о сборке мусора управляемых объектов.</span><span class="sxs-lookup"><span data-stu-id="2c84c-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c84c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2c84c-104">Methods</span></span>  
  
|<span data-ttu-id="2c84c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2c84c-105">Method</span></span>|<span data-ttu-id="2c84c-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="2c84c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c84c-107">Метод EnableNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="2c84c-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="2c84c-108">Задает значение, определяющее, каким образом приложение загружает образы в машинном коде во время выполнения в отладчике управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2c84c-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="2c84c-109">Метод EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="2c84c-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="2c84c-110">Возвращает перечислитель для всех объектов, которые должны быть мусора в процессе.</span><span class="sxs-lookup"><span data-stu-id="2c84c-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="2c84c-111">Метод EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="2c84c-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="2c84c-112">Возвращает перечислитель для маркеров объектов в процессе.</span><span class="sxs-lookup"><span data-stu-id="2c84c-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="2c84c-113">Метод EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="2c84c-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="2c84c-114">Возвращает перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="2c84c-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="2c84c-115">Метод EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="2c84c-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="2c84c-116">Получает перечислитель для областей управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="2c84c-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="2c84c-117">Метод GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="2c84c-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="2c84c-118">Получает сведения о структуре массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="2c84c-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="2c84c-119">Метод GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="2c84c-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="2c84c-120">Возвращает указатель на [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) структуру, содержащую сведения об объектах, которые должны быть мусора в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="2c84c-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="2c84c-121">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="2c84c-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="2c84c-122">Возвращает указатель на объект в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="2c84c-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="2c84c-123">Метод GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="2c84c-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="2c84c-124">Возвращает указатель на массив, содержащий сведения о полях для типа, на основе его идентификатора типа.</span><span class="sxs-lookup"><span data-stu-id="2c84c-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="2c84c-125">Метод GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="2c84c-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="2c84c-126">Возвращает тип объекта, который предоставляет сведения об объекте на основе ее типа идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="2c84c-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="2c84c-127">Метод GetTypeID</span><span class="sxs-lookup"><span data-stu-id="2c84c-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="2c84c-128">Возвращает идентификатор типа для объекта по заданному адресу.</span><span class="sxs-lookup"><span data-stu-id="2c84c-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="2c84c-129">Метод GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="2c84c-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="2c84c-130">Возвращает сведения о расположении объекта в памяти в зависимости от его типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="2c84c-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c84c-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c84c-131">Remarks</span></span>  
 <span data-ttu-id="2c84c-132">Этот интерфейс логически расширяет интерфейс ICorDebugProcess ICorDebugProcess2, и [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="2c84c-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c84c-133">Этот интерфейс не поддерживает удаленные вызовы с другого компьютера или из другого процесса.</span><span class="sxs-lookup"><span data-stu-id="2c84c-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c84c-134">Требования</span><span class="sxs-lookup"><span data-stu-id="2c84c-134">Requirements</span></span>  
 <span data-ttu-id="2c84c-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c84c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c84c-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c84c-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c84c-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c84c-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c84c-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c84c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c84c-139">См. также</span><span class="sxs-lookup"><span data-stu-id="2c84c-139">See Also</span></span>  
 [<span data-ttu-id="2c84c-140">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2c84c-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2c84c-141">Отладка</span><span class="sxs-lookup"><span data-stu-id="2c84c-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
