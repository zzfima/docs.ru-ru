---
title: Метод ICorDebugHeapEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd993eb26f26818117a20d376c3331f88c46b26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780904"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="16e2d-102">Метод ICorDebugHeapEnum::Next</span><span class="sxs-lookup"><span data-stu-id="16e2d-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="16e2d-103">Возвращает заданное число [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляров, которые содержат сведения об объектах в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="16e2d-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16e2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16e2d-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16e2d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16e2d-105">Parameters</span></span>  
 <span data-ttu-id="16e2d-106">celt</span><span class="sxs-lookup"><span data-stu-id="16e2d-106">celt</span></span>  
 <span data-ttu-id="16e2d-107">[in] Количество объектов, которые должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="16e2d-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="16e2d-108">объекты</span><span class="sxs-lookup"><span data-stu-id="16e2d-108">objects</span></span>  
 <span data-ttu-id="16e2d-109">[out] Массив указателей, каждый из которых указывает [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объект, предоставляющий сведения об объекте в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="16e2d-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="16e2d-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="16e2d-110">pceltFetched</span></span>  
 <span data-ttu-id="16e2d-111">[out] Указатель на число [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объектов, фактически возвращенных в `objects`.</span><span class="sxs-lookup"><span data-stu-id="16e2d-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="16e2d-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="16e2d-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16e2d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="16e2d-113">Remarks</span></span>  
 <span data-ttu-id="16e2d-114">Поле `COR_HEAPOBJECT.type` является идентификатором вложенного COM-интерфейса с подсчетом ссылок.</span><span class="sxs-lookup"><span data-stu-id="16e2d-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="16e2d-115">Эта ссылка должна быть выпущена вызывающим объектом `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="16e2d-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16e2d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="16e2d-116">Requirements</span></span>  
 <span data-ttu-id="16e2d-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16e2d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16e2d-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16e2d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16e2d-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16e2d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16e2d-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16e2d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e2d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="16e2d-121">See also</span></span>

- [<span data-ttu-id="16e2d-122">Интерфейс ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="16e2d-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [<span data-ttu-id="16e2d-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="16e2d-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
