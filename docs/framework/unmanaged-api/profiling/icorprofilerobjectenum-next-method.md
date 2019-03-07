---
title: Метод ICorProfilerObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc5d36267dcadcfafd4b715127ebbe2bcb9832b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487893"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="ce83f-102">Метод ICorProfilerObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ce83f-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="ce83f-103">Возвращает заданное число смежных объектов из упорядоченной коллекции объектов, начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="ce83f-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce83f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce83f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce83f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce83f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ce83f-106">[in] Количество объектов, которые должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="ce83f-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="ce83f-107">[out] Массив `ObjectID` значений, каждое из которых представляет полученный объект.</span><span class="sxs-lookup"><span data-stu-id="ce83f-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ce83f-108">[out] Указатель на число элементов, фактически извлеченных в массив `objects`.</span><span class="sxs-lookup"><span data-stu-id="ce83f-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce83f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ce83f-109">Requirements</span></span>  
 <span data-ttu-id="ce83f-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce83f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce83f-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce83f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce83f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce83f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce83f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce83f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce83f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ce83f-114">See also</span></span>
- [<span data-ttu-id="ce83f-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="ce83f-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
