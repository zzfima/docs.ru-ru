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
ms.openlocfilehash: a236103b8ca1501ae4c9109c1fd9e78865ab9c9c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740599"
---
# <a name="corheapobject-structure"></a><span data-ttu-id="4a65e-102">Структура COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="4a65e-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="4a65e-103">Предоставляет сведения об объекте, находящемся в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="4a65e-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a65e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a65e-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="4a65e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4a65e-105">Members</span></span>  
  
|<span data-ttu-id="4a65e-106">Член</span><span class="sxs-lookup"><span data-stu-id="4a65e-106">Member</span></span>|<span data-ttu-id="4a65e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4a65e-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="4a65e-108">Адрес объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="4a65e-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="4a65e-109">Общий размер объекта, в байтах.</span><span class="sxs-lookup"><span data-stu-id="4a65e-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="4a65e-110">Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) токен, представляющий тип объекта.</span><span class="sxs-lookup"><span data-stu-id="4a65e-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a65e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a65e-111">Remarks</span></span>  
 <span data-ttu-id="4a65e-112">`COR_HEAPOBJECT` экземпляры можно получить посредством перечисления [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объект интерфейса, который заполняется путем вызова [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4a65e-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="4a65e-113">Объект `COR_HEAPOBJECT` экземпляр предоставляет сведения о активный объект в управляемой куче, либо об объекте, который не является корневым, любой объект, но еще не были собраны сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="4a65e-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="4a65e-114">Для повышения производительности `COR_HEAPOBJECT.address` поле является `CORDB_ADDRESS` значение вместо ICorDebugValue интерфейс значение, используемое во многом API отладки.</span><span class="sxs-lookup"><span data-stu-id="4a65e-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="4a65e-115">Чтобы получить объект ICorDebugValue для адреса заданного объекта, можно передать `CORDB_ADDRESS` значение [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4a65e-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="4a65e-116">Для повышения производительности `COR_HEAPOBJECT.type` поле является `COR_TYPEID` значение вместо ICorDebugType интерфейс значение, используемое во многом API отладки.</span><span class="sxs-lookup"><span data-stu-id="4a65e-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="4a65e-117">Чтобы получить объект ICorDebugType идентификатора заданного типа, можно передать `COR_TYPEID` значение [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4a65e-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="4a65e-118">`COR_HEAPOBJECT` Структура включает в себя COM-интерфейса с подсчетом ссылок.</span><span class="sxs-lookup"><span data-stu-id="4a65e-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="4a65e-119">Если вы получите `COR_HEAPOBJECT` экземпляр из перечислителя, вызвав [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) метод, впоследствии необходимо освободить ссылку.</span><span class="sxs-lookup"><span data-stu-id="4a65e-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a65e-120">Требования</span><span class="sxs-lookup"><span data-stu-id="4a65e-120">Requirements</span></span>  
 <span data-ttu-id="4a65e-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a65e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a65e-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a65e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a65e-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a65e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a65e-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a65e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a65e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4a65e-125">See also</span></span>

- [<span data-ttu-id="4a65e-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="4a65e-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="4a65e-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="4a65e-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
