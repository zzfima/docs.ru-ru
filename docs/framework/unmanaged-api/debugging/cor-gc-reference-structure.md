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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179318"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="0bee7-102">Структура COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="0bee7-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="0bee7-103">Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="0bee7-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bee7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bee7-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="0bee7-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0bee7-105">Members</span></span>  
  
|<span data-ttu-id="0bee7-106">Участник</span><span class="sxs-lookup"><span data-stu-id="0bee7-106">Member</span></span>|<span data-ttu-id="0bee7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0bee7-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="0bee7-108">Указатель на домен приложения, к которому принадлежит ручка или объект.</span><span class="sxs-lookup"><span data-stu-id="0bee7-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="0bee7-109">Его значение `null`может быть .</span><span class="sxs-lookup"><span data-stu-id="0bee7-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="0bee7-110">Либо ICorDebugValue или интерфейс ICorDebugReferenceValue, который соответствует объекту, который будет собран мусором.</span><span class="sxs-lookup"><span data-stu-id="0bee7-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="0bee7-111">Значение [перечисления CorGCReferenceType,](corgcreferencetype-enumeration.md) которое указывает, откуда взялся корень.</span><span class="sxs-lookup"><span data-stu-id="0bee7-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="0bee7-112">Дополнительные сведения см. в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="0bee7-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="0bee7-113">Дополнительные данные об объекте, который должен быть собран мусором.</span><span class="sxs-lookup"><span data-stu-id="0bee7-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="0bee7-114">Эта информация зависит от источника объекта, `type` как указано на поле.</span><span class="sxs-lookup"><span data-stu-id="0bee7-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="0bee7-115">Дополнительные сведения см. в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="0bee7-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bee7-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="0bee7-116">Remarks</span></span>  
 <span data-ttu-id="0bee7-117">Поле `type` представляет собой значение перечисления [CorGCReferenceType,](corgcreferencetype-enumeration.md) которое указывает, откуда пришла ссылка.</span><span class="sxs-lookup"><span data-stu-id="0bee7-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="0bee7-118">Определенное `COR_GC_REFERENCE` значение может отражать любой из следующих видов управляемых объектов:</span><span class="sxs-lookup"><span data-stu-id="0bee7-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="0bee7-119">Объекты из всех`CorGCReferenceType.CorReferenceStack`управляемых стеков ().</span><span class="sxs-lookup"><span data-stu-id="0bee7-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="0bee7-120">Это включает в себя живые ссылки в управляемом коде, а также объекты, созданные общим временем выполнения языка.</span><span class="sxs-lookup"><span data-stu-id="0bee7-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="0bee7-121">Объекты из таблицы рукоятки ().`CorGCReferenceType.CorHandle*`</span><span class="sxs-lookup"><span data-stu-id="0bee7-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="0bee7-122">Это включает в`HNDTYPE_STRONG` себя `HNDTYPE_REFCOUNT`сильные ссылки (и ) и статические переменные в модуле.</span><span class="sxs-lookup"><span data-stu-id="0bee7-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="0bee7-123">Объекты из очереди`CorGCReferenceType.CorReferenceFinalizer`finalizer ().</span><span class="sxs-lookup"><span data-stu-id="0bee7-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="0bee7-124">Очередь finalizer корни объектов до завершения.</span><span class="sxs-lookup"><span data-stu-id="0bee7-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="0bee7-125">Поле `extraData` содержит дополнительные данные в зависимости от источника (или типа) ссылки.</span><span class="sxs-lookup"><span data-stu-id="0bee7-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="0bee7-126">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0bee7-126">Possible values are:</span></span>  
  
- <span data-ttu-id="0bee7-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="0bee7-127">`DependentSource`.</span></span> <span data-ttu-id="0bee7-128">Если `type` это, `CorGCREferenceType.CorHandleStrongDependent`это поле является объектом, который, если жив, `COR_GC_REFERENCE.Location`корни объекта, который будет мусор собран на .</span><span class="sxs-lookup"><span data-stu-id="0bee7-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="0bee7-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="0bee7-129">`RefCount`.</span></span> <span data-ttu-id="0bee7-130">Если `type` есть, `CorGCREferenceType.CorHandleStrongRefCount`это поле является эталоном ручки.</span><span class="sxs-lookup"><span data-stu-id="0bee7-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="0bee7-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="0bee7-131">`Size`.</span></span> <span data-ttu-id="0bee7-132">Если `type` есть, `CorGCREferenceType.CorHandleStrongSizedByref`это поле является последним размером дерева объекта, для которого сборщик мусора вычислил корни объекта.</span><span class="sxs-lookup"><span data-stu-id="0bee7-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="0bee7-133">Обратите внимание, что этот расчет не обязательно актуален.</span><span class="sxs-lookup"><span data-stu-id="0bee7-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bee7-134">Требования</span><span class="sxs-lookup"><span data-stu-id="0bee7-134">Requirements</span></span>  
 <span data-ttu-id="0bee7-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bee7-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bee7-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bee7-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bee7-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bee7-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bee7-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bee7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bee7-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0bee7-139">See also</span></span>

- [<span data-ttu-id="0bee7-140">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="0bee7-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0bee7-141">Отладки</span><span class="sxs-lookup"><span data-stu-id="0bee7-141">Debugging</span></span>](index.md)
