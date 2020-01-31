---
title: Перечисление CorGCReferenceType
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
ms.openlocfilehash: 17d47b6242bb12ff5ca3cfbde3e4ec183b9c19fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793866"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="f75dc-102">Перечисление CorGCReferenceType</span><span class="sxs-lookup"><span data-stu-id="f75dc-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="f75dc-103">Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="f75dc-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f75dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f75dc-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="f75dc-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f75dc-105">Members</span></span>  
  
|<span data-ttu-id="f75dc-106">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="f75dc-106">Member name</span></span>|<span data-ttu-id="f75dc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f75dc-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="f75dc-108">Дескриптор строгой ссылки из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="f75dc-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="f75dc-109">Указатель на закрепленную строгую ссылку из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="f75dc-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="f75dc-110">Указатель на слабую ссылку из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="f75dc-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="f75dc-111">Указатель на слабый объект, подсчитанный по ссылке, из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="f75dc-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="f75dc-112">Указатель на объект, подсчитанный по ссылке, из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="f75dc-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="f75dc-113">Маркер зависимого объекта из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="f75dc-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="f75dc-114">Асинхронный закрепленный объект из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="f75dc-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="f75dc-115">Строгая ссылка, хранящая приблизительный размер общего закрытия всех объектов и корневых объектов во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f75dc-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="f75dc-116">Ссылка из управляемого стека.</span><span class="sxs-lookup"><span data-stu-id="f75dc-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="f75dc-117">Ссылка из очереди метода завершения.</span><span class="sxs-lookup"><span data-stu-id="f75dc-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="f75dc-118">корхандлестронгонли</span><span class="sxs-lookup"><span data-stu-id="f75dc-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="f75dc-119">Возвращать только строгие ссылки из таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="f75dc-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="f75dc-120">Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f75dc-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="f75dc-121">Возвращать только слабые ссылки из таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="f75dc-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="f75dc-122">Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f75dc-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="f75dc-123">Возвращает все ссылки из таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="f75dc-123">Return all references from the handle table.</span></span> <span data-ttu-id="f75dc-124">Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f75dc-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f75dc-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="f75dc-125">Remarks</span></span>  
 <span data-ttu-id="f75dc-126">Перечисление `CorGCReferenceType` используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f75dc-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="f75dc-127">В качестве значения поля `type` структуры [COR_GC_REFERENCE](cor-gc-reference-structure.md) указывает источник ссылки или маркера.</span><span class="sxs-lookup"><span data-stu-id="f75dc-127">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="f75dc-128">В качестве аргумента `types` метода [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) указывает типы дескрипторов, включаемых в перечисление.</span><span class="sxs-lookup"><span data-stu-id="f75dc-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f75dc-129">Требования</span><span class="sxs-lookup"><span data-stu-id="f75dc-129">Requirements</span></span>  
 <span data-ttu-id="f75dc-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f75dc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f75dc-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f75dc-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f75dc-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f75dc-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f75dc-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f75dc-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75dc-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="f75dc-134">See also</span></span>

- [<span data-ttu-id="f75dc-135">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="f75dc-135">Debugging Enumerations</span></span>](debugging-enumerations.md)
