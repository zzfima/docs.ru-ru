---
title: Метод ICorDebugProcess5::EnumerateHandles
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3cc158c48e8bb9f833429bbddaa74ed459f1b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108837"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="60bc9-102">Метод ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="60bc9-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="60bc9-103">Возвращает перечислитель для дескрипторов объектов в процессе.</span><span class="sxs-lookup"><span data-stu-id="60bc9-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60bc9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60bc9-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60bc9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="60bc9-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="60bc9-106">[in] Побитовое сочетание [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значений, определяющих тип маркеры, чтобы включить в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="60bc9-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="60bc9-107">[out] Указатель на адрес [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) то есть перечислитель для объектов мусора.</span><span class="sxs-lookup"><span data-stu-id="60bc9-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60bc9-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="60bc9-108">Remarks</span></span>  
 `EnumerateHandles` <span data-ttu-id="60bc9-109">— это вспомогательная функция, которая поддерживает проверку таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="60bc9-109">is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="60bc9-110">Это похоже на [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) метода, за исключением случаев, вместо того чтобы заполнение [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) коллекции со всеми объектами, чтобы участвовать в сборе мусора, его включает только те объекты, с дескрипторами из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="60bc9-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="60bc9-111">`types` Параметр указывает типы дескрипторов для включения в коллекции.</span><span class="sxs-lookup"><span data-stu-id="60bc9-111">The `types` parameter specifies the handle types to include in the collection.</span></span> `types` <span data-ttu-id="60bc9-112">может принимать любое из следующих трех членов [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) перечисления:</span><span class="sxs-lookup"><span data-stu-id="60bc9-112">can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   `CorHandleStrongOnly` <span data-ttu-id="60bc9-113">(маркеры только строгих ссылок.)</span><span class="sxs-lookup"><span data-stu-id="60bc9-113">(handles to strong references only).</span></span>  
  
-   `CorHandleWeakOnly` <span data-ttu-id="60bc9-114">(маркеры только слабые ссылки.)</span><span class="sxs-lookup"><span data-stu-id="60bc9-114">(handles to weak references only).</span></span>  
  
-   `CorHandleAll` <span data-ttu-id="60bc9-115">(все дескрипторы).</span><span class="sxs-lookup"><span data-stu-id="60bc9-115">(all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60bc9-116">Требования</span><span class="sxs-lookup"><span data-stu-id="60bc9-116">Requirements</span></span>  
 <span data-ttu-id="60bc9-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60bc9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60bc9-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60bc9-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60bc9-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60bc9-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="60bc9-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="60bc9-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="60bc9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="60bc9-121">See also</span></span>

- [<span data-ttu-id="60bc9-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="60bc9-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="60bc9-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="60bc9-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
