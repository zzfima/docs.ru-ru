---
title: Структура COR_TYPEID
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51104516008ffee0694c72733cb5f82b5ba6d8cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609461"
---
# <a name="cortypeid-structure"></a><span data-ttu-id="db463-102">Структура COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="db463-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="db463-103">Содержит идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="db463-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db463-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db463-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="db463-105">Участники</span><span class="sxs-lookup"><span data-stu-id="db463-105">Members</span></span>  
  
|<span data-ttu-id="db463-106">Член</span><span class="sxs-lookup"><span data-stu-id="db463-106">Member</span></span>|<span data-ttu-id="db463-107">Описание</span><span class="sxs-lookup"><span data-stu-id="db463-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="db463-108">Первый токен.</span><span class="sxs-lookup"><span data-stu-id="db463-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="db463-109">Второй маркер.</span><span class="sxs-lookup"><span data-stu-id="db463-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db463-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="db463-110">Remarks</span></span>  
 <span data-ttu-id="db463-111">`COR_TYPEID` Структура возвращается несколько методов отладки, которые предоставляют сведения об объектах, чтобы участвовать в сборе мусора.</span><span class="sxs-lookup"><span data-stu-id="db463-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="db463-112">Он может затем передается как аргумент, другие методы отладки, предоставляющие дополнительные сведения об этом элементе.</span><span class="sxs-lookup"><span data-stu-id="db463-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="db463-113">Например, путем перечисления [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объекта, вы можете извлечь отдельные [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объекты, представляющие отдельные объекты в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="db463-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="db463-114">Затем можно передать `COR_TYPEID` значение из `COR_HEAPOBJECT.type` поле [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) метод для извлечения ICorDebugType объект, предоставляющий сведения о типе об объекте.</span><span class="sxs-lookup"><span data-stu-id="db463-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="db463-115">Объект `COR_TYPEID` объект должен быть непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="db463-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="db463-116">Не следует получить доступ к его отдельных полей или управления этим состоянием.</span><span class="sxs-lookup"><span data-stu-id="db463-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="db463-117">Его единственная используется как идентификатор, который предоставляется в качестве `out` параметр в вызов метода и который может в свою очередь, можно передать в другие методы для предоставления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="db463-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db463-118">Требования</span><span class="sxs-lookup"><span data-stu-id="db463-118">Requirements</span></span>  
 <span data-ttu-id="db463-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db463-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db463-120">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db463-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db463-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db463-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db463-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db463-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db463-123">См. также</span><span class="sxs-lookup"><span data-stu-id="db463-123">See also</span></span>

- [<span data-ttu-id="db463-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="db463-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="db463-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="db463-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
