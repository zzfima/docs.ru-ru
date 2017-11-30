---
title: "Метод ICorDebugProcess5::EnumerateHandles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHandles
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5377f4ce0571cdb1de6c338f4bbb87d6a589aaf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="67b67-102">Метод ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="67b67-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="67b67-103">Возвращает перечислитель для маркеров объектов в процессе.</span><span class="sxs-lookup"><span data-stu-id="67b67-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67b67-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67b67-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67b67-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67b67-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="67b67-106">[in] Побитовое сочетание [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значения, которое указывает тип маркеров для включения в коллекции.</span><span class="sxs-lookup"><span data-stu-id="67b67-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="67b67-107">[out] Указатель на адрес [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) , перечислитель для объектов для сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="67b67-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67b67-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="67b67-108">Remarks</span></span>  
 <span data-ttu-id="67b67-109">`EnumerateHandles`является вспомогательная функция, которая поддерживает проверку таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="67b67-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="67b67-110">Это похоже на [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) метода, за исключением того, вместо того чтобы заполнение [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) коллекции со всеми объектами для сбора мусора, он включает только те объекты, которые имеют дескрипторы из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="67b67-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="67b67-111">`types` Параметр указывает типы дескрипторов для включения в коллекции.</span><span class="sxs-lookup"><span data-stu-id="67b67-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="67b67-112">`types`может иметь любое из следующих трех возможных членов [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) перечисления:</span><span class="sxs-lookup"><span data-stu-id="67b67-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="67b67-113">`CorHandleStrongOnly`(маркеры для строгих ссылок только).</span><span class="sxs-lookup"><span data-stu-id="67b67-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="67b67-114">`CorHandleWeakOnly`(маркеры для только слабые ссылки).</span><span class="sxs-lookup"><span data-stu-id="67b67-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="67b67-115">`CorHandleAll`(все дескрипторы).</span><span class="sxs-lookup"><span data-stu-id="67b67-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67b67-116">Требования</span><span class="sxs-lookup"><span data-stu-id="67b67-116">Requirements</span></span>  
 <span data-ttu-id="67b67-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67b67-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67b67-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67b67-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67b67-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67b67-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67b67-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67b67-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b67-121">См. также</span><span class="sxs-lookup"><span data-stu-id="67b67-121">See Also</span></span>  
 [<span data-ttu-id="67b67-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="67b67-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="67b67-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="67b67-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
