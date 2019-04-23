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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f179b58ff8eb51e2843780d3212cf38ed7d13216
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168835"
---
# <a name="corheapobject-structure"></a><span data-ttu-id="2a52b-102">Структура COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="2a52b-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="2a52b-103">Предоставляет сведения об объекте, находящемся в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="2a52b-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a52b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a52b-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="2a52b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2a52b-105">Members</span></span>  
  
|<span data-ttu-id="2a52b-106">Член</span><span class="sxs-lookup"><span data-stu-id="2a52b-106">Member</span></span>|<span data-ttu-id="2a52b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2a52b-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="2a52b-108">Адрес объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="2a52b-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="2a52b-109">Общий размер объекта, в байтах.</span><span class="sxs-lookup"><span data-stu-id="2a52b-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="2a52b-110">Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) токен, представляющий тип объекта.</span><span class="sxs-lookup"><span data-stu-id="2a52b-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a52b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a52b-111">Remarks</span></span>  
 <span data-ttu-id="2a52b-112">`COR_HEAPOBJECT` экземпляры можно получить посредством перечисления [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объект интерфейса, который заполняется путем вызова [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2a52b-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="2a52b-113">Объект `COR_HEAPOBJECT` экземпляр предоставляет сведения о активный объект в управляемой куче, либо об объекте, который не является корневым, любой объект, но еще не были собраны сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="2a52b-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="2a52b-114">Для повышения производительности `COR_HEAPOBJECT.address` поле является `CORDB_ADDRESS` значение вместо ICorDebugValue интерфейс значение, используемое во многом API отладки.</span><span class="sxs-lookup"><span data-stu-id="2a52b-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="2a52b-115">Чтобы получить объект ICorDebugValue для адреса заданного объекта, можно передать `CORDB_ADDRESS` значение [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2a52b-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="2a52b-116">Для повышения производительности `COR_HEAPOBJECT.type` поле является `COR_TYPEID` значение вместо ICorDebugType интерфейс значение, используемое во многом API отладки.</span><span class="sxs-lookup"><span data-stu-id="2a52b-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="2a52b-117">Чтобы получить объект ICorDebugType идентификатора заданного типа, можно передать `COR_TYPEID` значение [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2a52b-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="2a52b-118">`COR_HEAPOBJECT` Структура включает в себя COM-интерфейса с подсчетом ссылок.</span><span class="sxs-lookup"><span data-stu-id="2a52b-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="2a52b-119">Если вы получите `COR_HEAPOBJECT` экземпляр из перечислителя, вызвав [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) метод, впоследствии необходимо освободить ссылку.</span><span class="sxs-lookup"><span data-stu-id="2a52b-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a52b-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2a52b-120">Requirements</span></span>  
 <span data-ttu-id="2a52b-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a52b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a52b-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a52b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a52b-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a52b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a52b-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a52b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a52b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2a52b-125">See also</span></span>

- [<span data-ttu-id="2a52b-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="2a52b-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="2a52b-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="2a52b-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
