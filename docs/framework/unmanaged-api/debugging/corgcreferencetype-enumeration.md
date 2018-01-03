---
title: "Перечисление CorGCReferenceType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGCReferenceType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorGCReferenceType
helpviewer_keywords: CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="1ce16-102">Перечисление CorGCReferenceType</span><span class="sxs-lookup"><span data-stu-id="1ce16-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="1ce16-103">Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="1ce16-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ce16-104">Syntax</span></span>  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="1ce16-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1ce16-105">Members</span></span>  
  
|<span data-ttu-id="1ce16-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="1ce16-106">Member name</span></span>|<span data-ttu-id="1ce16-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="1ce16-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="1ce16-108">Дескриптор строгой ссылки из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="1ce16-109">Дескриптор закрепленная строгая ссылка из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="1ce16-110">Дескриптор слабая ссылка из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="1ce16-111">Дескриптор слабое объект с подсчетом ссылок из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="1ce16-112">Дескриптор объект с подсчетом ссылок из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="1ce16-113">Дескриптор зависимого объекта из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="1ce16-114">Асинхронный закрепленный объект из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="1ce16-115">Строгая ссылка, хранящая приблизительный размер общего закрытия всех объектов и корневых объектов во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1ce16-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="1ce16-116">Ссылка из управляемого стека.</span><span class="sxs-lookup"><span data-stu-id="1ce16-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="1ce16-117">Ссылка из очереди метода завершения.</span><span class="sxs-lookup"><span data-stu-id="1ce16-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="1ce16-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="1ce16-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="1ce16-119">Возвращать только строгих ссылок из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="1ce16-120">Это значение используется [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.</span><span class="sxs-lookup"><span data-stu-id="1ce16-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="1ce16-121">Возвращать только слабые ссылки из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="1ce16-122">Это значение используется [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.</span><span class="sxs-lookup"><span data-stu-id="1ce16-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="1ce16-123">Возврат всех ссылок из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="1ce16-123">Return all references from the handle table.</span></span> <span data-ttu-id="1ce16-124">Это значение используется [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.</span><span class="sxs-lookup"><span data-stu-id="1ce16-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ce16-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="1ce16-125">Remarks</span></span>  
 <span data-ttu-id="1ce16-126">`CorGCReferenceType` Перечисление используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1ce16-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="1ce16-127">В качестве значения `type` поле [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) структуры, он указывает на источник ссылки или дескриптора.</span><span class="sxs-lookup"><span data-stu-id="1ce16-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="1ce16-128">Как `types` аргумент [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) метода, задает типы маркеров для включения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="1ce16-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ce16-129">Требования</span><span class="sxs-lookup"><span data-stu-id="1ce16-129">Requirements</span></span>  
 <span data-ttu-id="1ce16-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ce16-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ce16-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ce16-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ce16-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ce16-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ce16-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ce16-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce16-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1ce16-134">See Also</span></span>  
 [<span data-ttu-id="1ce16-135">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="1ce16-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
