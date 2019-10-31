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
ms.openlocfilehash: e0e68dba1f4d9ac5fa618aa842b823dcc046e70e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129680"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="767d3-102">Метод ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="767d3-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="767d3-103">Возвращает перечислитель для дескрипторов объектов в процессе.</span><span class="sxs-lookup"><span data-stu-id="767d3-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="767d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="767d3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="767d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="767d3-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="767d3-106">окне Побитовое сочетание значений [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) , определяющих тип дескрипторов, включаемых в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="767d3-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="767d3-107">заполняет Указатель на адрес [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) , который является перечислителем для объектов, которые должны быть собраны в мусор.</span><span class="sxs-lookup"><span data-stu-id="767d3-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="767d3-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="767d3-108">Remarks</span></span>  
 <span data-ttu-id="767d3-109">`EnumerateHandles` — это вспомогательная функция, которая поддерживает проверку таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="767d3-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="767d3-110">Он аналогичен методу [метод ICorDebugProcess5:: енумератегкреференцес](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) , за исключением того, что вместо заполнения коллекции [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) всеми объектами для сбора мусора он включает только объекты, имеющие дескрипторы из Таблица Handle.</span><span class="sxs-lookup"><span data-stu-id="767d3-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="767d3-111">Параметр `types` указывает типы обработчиков, которые необходимо включить в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="767d3-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="767d3-112">`types` может быть любым из следующих трех членов перечисления [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) :</span><span class="sxs-lookup"><span data-stu-id="767d3-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="767d3-113">`CorHandleStrongOnly` (обрабатываются только строгими ссылками).</span><span class="sxs-lookup"><span data-stu-id="767d3-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="767d3-114">`CorHandleWeakOnly` (дескрипторы только слабых ссылок).</span><span class="sxs-lookup"><span data-stu-id="767d3-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="767d3-115">`CorHandleAll` (все дескрипторы).</span><span class="sxs-lookup"><span data-stu-id="767d3-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="767d3-116">Требования</span><span class="sxs-lookup"><span data-stu-id="767d3-116">Requirements</span></span>  
 <span data-ttu-id="767d3-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="767d3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="767d3-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="767d3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="767d3-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="767d3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="767d3-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="767d3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767d3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="767d3-121">See also</span></span>

- [<span data-ttu-id="767d3-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="767d3-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="767d3-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="767d3-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
