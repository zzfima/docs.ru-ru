---
title: "Структура COR_TYPEID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ca6c9b3b02314843a3eaf01d8cd4a9eac5513efa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cortypeid-structure"></a><span data-ttu-id="8b140-102">Структура COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="8b140-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="8b140-103">Содержит идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="8b140-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b140-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b140-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="8b140-105">Участники</span><span class="sxs-lookup"><span data-stu-id="8b140-105">Members</span></span>  
  
|<span data-ttu-id="8b140-106">Член</span><span class="sxs-lookup"><span data-stu-id="8b140-106">Member</span></span>|<span data-ttu-id="8b140-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="8b140-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="8b140-108">Первый токен.</span><span class="sxs-lookup"><span data-stu-id="8b140-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="8b140-109">Второй маркер.</span><span class="sxs-lookup"><span data-stu-id="8b140-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b140-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b140-110">Remarks</span></span>  
 <span data-ttu-id="8b140-111">`COR_TYPEID` Структура возвращается несколько методов отладки, предоставляющие сведения об объектах для сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="8b140-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="8b140-112">Он затем могут передаваться в качестве аргумента в другие методы отладки, предоставляющие дополнительные сведения об этом элементе.</span><span class="sxs-lookup"><span data-stu-id="8b140-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="8b140-113">Например, путем перечисления [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объекта, вы можете извлечь отдельные [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объекты, представляющие отдельные объекты в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="8b140-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="8b140-114">Затем можно передать `COR_TYPEID` значение из `COR_HEAPOBJECT.type` на [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) метод для извлечения объекта ICorDebugType, определяющие тип объекта.</span><span class="sxs-lookup"><span data-stu-id="8b140-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="8b140-115">Объект `COR_TYPEID` объект должен быть непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="8b140-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="8b140-116">Не следует получить доступ к его отдельных полей или управления этим состоянием.</span><span class="sxs-lookup"><span data-stu-id="8b140-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="8b140-117">Единственным используется как идентификатор, предоставляемый как `out` параметр в вызове метода и который может передаваться в свою очередь, в другие методы для предоставления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="8b140-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b140-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8b140-118">Requirements</span></span>  
 <span data-ttu-id="8b140-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b140-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b140-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b140-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b140-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b140-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b140-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b140-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b140-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8b140-123">See Also</span></span>  
 [<span data-ttu-id="8b140-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="8b140-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="8b140-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="8b140-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
