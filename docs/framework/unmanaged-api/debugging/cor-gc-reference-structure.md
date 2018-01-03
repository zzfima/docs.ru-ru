---
title: "Структура COR_GC_REFERENCE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a86604febb7641eef147608e564a27883fdc4bec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreference-structure"></a><span data-ttu-id="d7085-102">Структура COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="d7085-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="d7085-103">Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="d7085-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7085-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7085-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="d7085-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d7085-105">Members</span></span>  
  
|<span data-ttu-id="d7085-106">Член</span><span class="sxs-lookup"><span data-stu-id="d7085-106">Member</span></span>|<span data-ttu-id="d7085-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="d7085-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="d7085-108">Указатель на домен приложения, к которому принадлежит объект или дескриптора.</span><span class="sxs-lookup"><span data-stu-id="d7085-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="d7085-109">Его значение может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="d7085-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="d7085-110">ICorDebugValue или ICorDebugReferenceValue-интерфейс, соответствующий объект, который будет собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="d7085-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="d7085-111">Объект [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значение перечисления, указывающее, откуда корня.</span><span class="sxs-lookup"><span data-stu-id="d7085-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="d7085-112">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="d7085-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="d7085-113">Дополнительные данные об объекте для сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="d7085-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="d7085-114">Эта информация зависит от источника объекта, как указано в `type` поле.</span><span class="sxs-lookup"><span data-stu-id="d7085-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="d7085-115">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="d7085-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7085-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7085-116">Remarks</span></span>  
 <span data-ttu-id="d7085-117">`type` Поле является [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значение перечисления, указывающее, откуда ссылка.</span><span class="sxs-lookup"><span data-stu-id="d7085-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="d7085-118">Определенный `COR_GC_REFERENCE` значение, может отражать следующие виды управляемых объектов:</span><span class="sxs-lookup"><span data-stu-id="d7085-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
-   <span data-ttu-id="d7085-119">Объекты из всех управляемых стеков (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="d7085-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="d7085-120">Сюда относятся активных ссылок в управляемом коде, а также объекты, созданные средой CLR.</span><span class="sxs-lookup"><span data-stu-id="d7085-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="d7085-121">Объекты из таблицы дескрипторов (`CorGCReferenceType.CorHandle*`).</span><span class="sxs-lookup"><span data-stu-id="d7085-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="d7085-122">Сюда входят строгих ссылок (`HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT`) и статические переменные в модуле.</span><span class="sxs-lookup"><span data-stu-id="d7085-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="d7085-123">Объекты из очереди метода завершения (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="d7085-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="d7085-124">Очереди метода завершения корневых объектов до выполнения метода завершения.</span><span class="sxs-lookup"><span data-stu-id="d7085-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="d7085-125">`extraData` Поле содержит дополнительные данные в зависимости от источника (или типов) ссылки.</span><span class="sxs-lookup"><span data-stu-id="d7085-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="d7085-126">Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d7085-126">Possible values are:</span></span>  
  
-   <span data-ttu-id="d7085-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="d7085-127">`DependentSource`.</span></span> <span data-ttu-id="d7085-128">Если `type` — `CorGCREferenceType.CorHandleStrongDependent`, это поле является объект, если в активном состоянии, корней объект, который будет собрана сборщиком мусора во `COR_GC_REFERENCE.Location`.</span><span class="sxs-lookup"><span data-stu-id="d7085-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
-   <span data-ttu-id="d7085-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="d7085-129">`RefCount`.</span></span> <span data-ttu-id="d7085-130">Если `type` — `CorGCREferenceType.CorHandleStrongRefCount`, это поле является дескриптор счетчика ссылок.</span><span class="sxs-lookup"><span data-stu-id="d7085-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
-   <span data-ttu-id="d7085-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="d7085-131">`Size`.</span></span> <span data-ttu-id="d7085-132">Если `type` — `CorGCREferenceType.CorHandleStrongSizedByref`, это поле является последний размер дерева объектов, для которой сборщик мусора рассчитана корни объекта.</span><span class="sxs-lookup"><span data-stu-id="d7085-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="d7085-133">Обратите внимание, что этот расчет не обязательно в актуальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="d7085-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7085-134">Требования</span><span class="sxs-lookup"><span data-stu-id="d7085-134">Requirements</span></span>  
 <span data-ttu-id="d7085-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7085-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7085-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7085-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7085-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7085-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7085-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7085-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7085-139">См. также</span><span class="sxs-lookup"><span data-stu-id="d7085-139">See Also</span></span>  
 [<span data-ttu-id="d7085-140">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="d7085-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="d7085-141">Отладка</span><span class="sxs-lookup"><span data-stu-id="d7085-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
