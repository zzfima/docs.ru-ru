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
ms.openlocfilehash: 2a1653055a3834ce1bed0e7de7877b255bea0c38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792427"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="8622d-102">Метод ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="8622d-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="8622d-103">Возвращает перечислитель для дескрипторов объектов в процессе.</span><span class="sxs-lookup"><span data-stu-id="8622d-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8622d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8622d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8622d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8622d-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="8622d-106">окне Побитовое сочетание значений [CorGCReferenceType](corgcreferencetype-enumeration.md) , определяющих тип дескрипторов, включаемых в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="8622d-106">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="8622d-107">заполняет Указатель на адрес [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) , который является перечислителем для объектов, которые должны быть собраны в мусор.</span><span class="sxs-lookup"><span data-stu-id="8622d-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8622d-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="8622d-108">Remarks</span></span>  
 <span data-ttu-id="8622d-109">`EnumerateHandles` — это вспомогательная функция, которая поддерживает проверку таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="8622d-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="8622d-110">Он похож на метод [метод ICorDebugProcess5:: енумератегкреференцес](icordebugprocess5-enumerategcreferences-method.md) , за исключением того, что вместо заполнения коллекции [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) всеми объектами, которые должны быть собраны сборщиком мусора, он включает только объекты, имеющие дескрипторы из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="8622d-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="8622d-111">Параметр `types` указывает типы обработчиков, которые необходимо включить в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="8622d-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="8622d-112">`types` может быть любым из следующих трех членов перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md) :</span><span class="sxs-lookup"><span data-stu-id="8622d-112">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="8622d-113">`CorHandleStrongOnly` (обрабатываются только строгими ссылками).</span><span class="sxs-lookup"><span data-stu-id="8622d-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="8622d-114">`CorHandleWeakOnly` (дескрипторы только слабых ссылок).</span><span class="sxs-lookup"><span data-stu-id="8622d-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="8622d-115">`CorHandleAll` (все дескрипторы).</span><span class="sxs-lookup"><span data-stu-id="8622d-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8622d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="8622d-116">Requirements</span></span>  
 <span data-ttu-id="8622d-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8622d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8622d-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8622d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8622d-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8622d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8622d-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8622d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8622d-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="8622d-121">See also</span></span>

- [<span data-ttu-id="8622d-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="8622d-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="8622d-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="8622d-123">Debugging</span></span>](index.md)
