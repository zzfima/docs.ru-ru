---
title: Метод ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33ad221f2a05357484d0877b6306d78e3864eff6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120176"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="281ef-102">Метод ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="281ef-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="281ef-103">Возвращает заданное число [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) экземпляров, которые содержат сведения об объектах, которые будут удалены сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="281ef-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="281ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="281ef-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="281ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="281ef-105">Parameters</span></span>  
 <span data-ttu-id="281ef-106">celt</span><span class="sxs-lookup"><span data-stu-id="281ef-106">celt</span></span>  
 <span data-ttu-id="281ef-107">[in] Число корней, которые требуется извлечь.</span><span class="sxs-lookup"><span data-stu-id="281ef-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="281ef-108">корни</span><span class="sxs-lookup"><span data-stu-id="281ef-108">roots</span></span>  
 <span data-ttu-id="281ef-109">[out] Массив указателей, каждый из которых указывает [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) объект, который предоставляет собой корневой объект как сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="281ef-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="281ef-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="281ef-110">pceltFetched</span></span>  
 <span data-ttu-id="281ef-111">[out] Указатель на число [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) объектов, фактически возвращенных в `roots`.</span><span class="sxs-lookup"><span data-stu-id="281ef-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="281ef-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="281ef-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="281ef-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="281ef-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="281ef-114">Требования</span><span class="sxs-lookup"><span data-stu-id="281ef-114">Requirements</span></span>  
 <span data-ttu-id="281ef-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="281ef-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="281ef-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="281ef-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="281ef-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="281ef-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="281ef-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="281ef-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="281ef-119">См. также</span><span class="sxs-lookup"><span data-stu-id="281ef-119">See also</span></span>

- [<span data-ttu-id="281ef-120">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="281ef-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="281ef-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="281ef-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
