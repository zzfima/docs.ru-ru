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
ms.openlocfilehash: 0c833416cca965f2655266152c5bdf5f11624d14
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861142"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="28f23-102">Метод ICorProfilerObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="28f23-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="28f23-103">Возвращает указанное количество смежных объектов из последовательной коллекции объектов, начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="28f23-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f23-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28f23-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28f23-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28f23-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="28f23-106">[in] Количество объектов, которые должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="28f23-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="28f23-107">заполняет Массив значений `ObjectID`, каждый из которых представляет извлеченный объект.</span><span class="sxs-lookup"><span data-stu-id="28f23-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="28f23-108">[out] Указатель на число элементов, фактически извлеченных в массив `objects`.</span><span class="sxs-lookup"><span data-stu-id="28f23-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f23-109">Требования</span><span class="sxs-lookup"><span data-stu-id="28f23-109">Requirements</span></span>  
 <span data-ttu-id="28f23-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28f23-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28f23-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28f23-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28f23-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28f23-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28f23-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28f23-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f23-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="28f23-114">See also</span></span>

- [<span data-ttu-id="28f23-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="28f23-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
