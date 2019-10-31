---
title: Структура COR_GC_REFERENCE
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
ms.openlocfilehash: 635cb0c003889beb2f78e8413189cbfc4b064175
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099140"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="bc9f1-102">Структура COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="bc9f1-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="bc9f1-103">Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc9f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc9f1-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="bc9f1-105">Члены</span><span class="sxs-lookup"><span data-stu-id="bc9f1-105">Members</span></span>  
  
|<span data-ttu-id="bc9f1-106">Член</span><span class="sxs-lookup"><span data-stu-id="bc9f1-106">Member</span></span>|<span data-ttu-id="bc9f1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bc9f1-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="bc9f1-108">Указатель на домен приложения, которому принадлежит маркер или объект.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="bc9f1-109">Его значение может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="bc9f1-110">Интерфейс ICorDebugValue или ICorDebugReferenceValue, соответствующий объекту, который должен быть собран сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="bc9f1-111">Значение перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md) , указывающее, откуда поступил корень.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="bc9f1-112">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="bc9f1-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="bc9f1-113">Дополнительные данные об объекте, который должен быть собран сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="bc9f1-114">Эти сведения зависят от источника объекта, как указано в поле `type`.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="bc9f1-115">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="bc9f1-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc9f1-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="bc9f1-116">Remarks</span></span>  
 <span data-ttu-id="bc9f1-117">Поле `type` является значением перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md) , которое указывает, откуда поступила ссылка.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="bc9f1-118">Конкретное `COR_GC_REFERENCE` значение может отражать любой из следующих видов управляемых объектов:</span><span class="sxs-lookup"><span data-stu-id="bc9f1-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="bc9f1-119">Объекты из всех управляемых стеков (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="bc9f1-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="bc9f1-120">Сюда входят динамические ссылки в управляемом коде, а также объекты, созданные средой CLR.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="bc9f1-121">Объекты из таблицы Handle (`CorGCReferenceType.CorHandle*`).</span><span class="sxs-lookup"><span data-stu-id="bc9f1-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="bc9f1-122">Сюда входят строгие ссылки (`HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT`) и статические переменные в модуле.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="bc9f1-123">Объекты из очереди метода завершения (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="bc9f1-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="bc9f1-124">Очередь метода завершения помещает объекты в корни до запуска метода завершения.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="bc9f1-125">Поле `extraData` содержит дополнительные данные в зависимости от источника (или типа) ссылки.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="bc9f1-126">Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bc9f1-126">Possible values are:</span></span>  
  
- <span data-ttu-id="bc9f1-127">`DependentSource`</span><span class="sxs-lookup"><span data-stu-id="bc9f1-127">`DependentSource`.</span></span> <span data-ttu-id="bc9f1-128">Если `type` имеет `CorGCREferenceType.CorHandleStrongDependent`, это поле является объектом, который, в своюмся, является корнем объекта, который должен быть собран в `COR_GC_REFERENCE.Location`при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="bc9f1-129">`RefCount`</span><span class="sxs-lookup"><span data-stu-id="bc9f1-129">`RefCount`.</span></span> <span data-ttu-id="bc9f1-130">Если `type` `CorGCREferenceType.CorHandleStrongRefCount`, это поле является счетчиком ссылок на маркер.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="bc9f1-131">`Size`</span><span class="sxs-lookup"><span data-stu-id="bc9f1-131">`Size`.</span></span> <span data-ttu-id="bc9f1-132">Если `type` `CorGCREferenceType.CorHandleStrongSizedByref`, это поле является последним размером дерева объектов, для которого сборщик мусора вычисляет корни объекта.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="bc9f1-133">Обратите внимание, что это вычисление не обязательно в актуальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="bc9f1-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc9f1-134">Требования</span><span class="sxs-lookup"><span data-stu-id="bc9f1-134">Requirements</span></span>  
 <span data-ttu-id="bc9f1-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc9f1-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc9f1-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc9f1-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc9f1-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc9f1-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc9f1-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc9f1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9f1-139">См. также</span><span class="sxs-lookup"><span data-stu-id="bc9f1-139">See also</span></span>

- [<span data-ttu-id="bc9f1-140">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="bc9f1-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="bc9f1-141">Отладка</span><span class="sxs-lookup"><span data-stu-id="bc9f1-141">Debugging</span></span>](index.md)
