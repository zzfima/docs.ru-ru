---
title: Структура COR_HEAPOBJECT
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179340"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="48b52-102">Структура COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="48b52-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="48b52-103">Предоставляет сведения об объекте, находящемся в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="48b52-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48b52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48b52-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="48b52-105">Члены</span><span class="sxs-lookup"><span data-stu-id="48b52-105">Members</span></span>  
  
|<span data-ttu-id="48b52-106">Участник</span><span class="sxs-lookup"><span data-stu-id="48b52-106">Member</span></span>|<span data-ttu-id="48b52-107">Описание</span><span class="sxs-lookup"><span data-stu-id="48b52-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="48b52-108">Адрес объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="48b52-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="48b52-109">Общий размер объекта, в байтах.</span><span class="sxs-lookup"><span data-stu-id="48b52-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="48b52-110">[Знак COR_TYPEID,](cor-typeid-structure.md) представляющий тип объекта.</span><span class="sxs-lookup"><span data-stu-id="48b52-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48b52-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="48b52-111">Remarks</span></span>  
 <span data-ttu-id="48b52-112">`COR_HEAPOBJECT`экземпляры можно извлечь, перечислив объект интерфейса [ICorDebugHeapEnum,](icordebugheapenum-interface.md) который населен, позвонив в метод [ICorDebugProcess5::EnumerateHeap.](icordebugprocess5-enumerateheap-method.md)</span><span class="sxs-lookup"><span data-stu-id="48b52-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="48b52-113">Экземпляр `COR_HEAPOBJECT` предоставляет информацию либо о живом объекте на управляемой куче, либо об объекте, который не коренится ни одним объектом, но еще не собран сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="48b52-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="48b52-114">Для повышения производительности `COR_HEAPOBJECT.address` поле `CORDB_ADDRESS` представляет собой значение, а не значение интерфейса ICorBugValue, используемого в большей части API отладки.</span><span class="sxs-lookup"><span data-stu-id="48b52-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="48b52-115">Чтобы получить объект ICorDebugValue для данного адреса `CORDB_ADDRESS` объекта, можно передать значение методу [ICorDebugProcess5::GetObject.](icordebugprocess5-getobject-method.md)</span><span class="sxs-lookup"><span data-stu-id="48b52-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="48b52-116">Для повышения производительности `COR_HEAPOBJECT.type` поле `COR_TYPEID` является ценностью, а не значением интерфейса ICorDebugType, используемого в большей части API отладки.</span><span class="sxs-lookup"><span data-stu-id="48b52-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="48b52-117">Чтобы получить объект ICorDebugType для идентификатора заданного типа, вы можете передать `COR_TYPEID` значение методу [ICorDebugProcess5:GetTypeForTypeID.](icordebugprocess5-gettypefortypeid-method.md)</span><span class="sxs-lookup"><span data-stu-id="48b52-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="48b52-118">Структура `COR_HEAPOBJECT` включает в себя справочно-считаемый интерфейс COM.</span><span class="sxs-lookup"><span data-stu-id="48b52-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="48b52-119">Если вы извлекете `COR_HEAPOBJECT` экземпляр из регистратора, позвонив в [ICorDebugHeapEnum::Следующий](icordebugheapenum-next-method.md) метод, вы должны впоследствии освободить ссылку.</span><span class="sxs-lookup"><span data-stu-id="48b52-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48b52-120">Требования</span><span class="sxs-lookup"><span data-stu-id="48b52-120">Requirements</span></span>  
 <span data-ttu-id="48b52-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48b52-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48b52-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48b52-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48b52-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48b52-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48b52-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48b52-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b52-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48b52-125">See also</span></span>

- [<span data-ttu-id="48b52-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="48b52-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="48b52-127">Отладки</span><span class="sxs-lookup"><span data-stu-id="48b52-127">Debugging</span></span>](index.md)
