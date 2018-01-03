---
title: "Структура COR_HEAPOBJECT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPOBJECT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPOBJECT
helpviewer_keywords: COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 476d9dcb1c6700833b0a113028bdaaf0c5a375c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corheapobject-structure"></a><span data-ttu-id="6a4f0-102">Структура COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="6a4f0-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="6a4f0-103">Предоставляет сведения об объекте, находящемся в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a4f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a4f0-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="6a4f0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6a4f0-105">Members</span></span>  
  
|<span data-ttu-id="6a4f0-106">Член</span><span class="sxs-lookup"><span data-stu-id="6a4f0-106">Member</span></span>|<span data-ttu-id="6a4f0-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="6a4f0-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="6a4f0-108">Адрес объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="6a4f0-109">Общий размер объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="6a4f0-110">Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) токен, представляющий тип объекта.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a4f0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a4f0-111">Remarks</span></span>  
 <span data-ttu-id="6a4f0-112">`COR_HEAPOBJECT`экземпляры можно получить путем перечисления [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объект интерфейса, который заполняется путем вызова [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="6a4f0-113">Объект `COR_HEAPOBJECT` экземпляр предоставляет сведения о динамической объекта в управляемой куче, либо об объекте, который не связан с любым объектом, но еще не были собраны сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="6a4f0-114">Для повышения производительности `COR_HEAPOBJECT.address` поле является `CORDB_ADDRESS` значение вместо ICorDebugValue интерфейс значение, используемое в большую часть API отладки.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="6a4f0-115">Чтобы получить объект ICorDebugValue для адреса заданного объекта, можно передать `CORDB_ADDRESS` значение [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="6a4f0-116">Для повышения производительности `COR_HEAPOBJECT.type` поле является `COR_TYPEID` значение вместо ICorDebugType интерфейс значение, используемое в большую часть API отладки.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="6a4f0-117">Чтобы получить объект ICorDebugType для идентификатора указанного типа, можно передать `COR_TYPEID` значение [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="6a4f0-118">`COR_HEAPOBJECT` Структура включает в себя подсчетом ссылок COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="6a4f0-119">При извлечении `COR_HEAPOBJECT` экземпляра перечислителя путем вызова [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) метод, впоследствии необходимо освободить ссылку.</span><span class="sxs-lookup"><span data-stu-id="6a4f0-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a4f0-120">Требования</span><span class="sxs-lookup"><span data-stu-id="6a4f0-120">Requirements</span></span>  
 <span data-ttu-id="6a4f0-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a4f0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a4f0-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a4f0-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a4f0-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a4f0-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a4f0-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a4f0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a4f0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6a4f0-125">See Also</span></span>  
 [<span data-ttu-id="6a4f0-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="6a4f0-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="6a4f0-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="6a4f0-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
