---
title: Метод ICorProfilerInfo2::GetArrayObjectInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ebf8c736cdd1362cae1b1e0b734ce14bea49b18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751884"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="6f083-102">Метод ICorProfilerInfo2::GetArrayObjectInfo</span><span class="sxs-lookup"><span data-stu-id="6f083-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="6f083-103">Получает подробные сведения об объекте массива.</span><span class="sxs-lookup"><span data-stu-id="6f083-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f083-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f083-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f083-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f083-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="6f083-106">[in] Идентификатор объекта допустимым массивом.</span><span class="sxs-lookup"><span data-stu-id="6f083-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="6f083-107">[in] Ранг (число измерений) массива.</span><span class="sxs-lookup"><span data-stu-id="6f083-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="6f083-108">[out] Массив, содержащий целые числа, каждый из которых представляет размер измерения массива.</span><span class="sxs-lookup"><span data-stu-id="6f083-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="6f083-109">[out] Массив, содержащий целые числа, каждый из которых представляет нижняя граница измерения массива.</span><span class="sxs-lookup"><span data-stu-id="6f083-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="6f083-110">[out] Указатель на адрес необработанного буфера для массива, в которой располагается согласно C++ соглашение.</span><span class="sxs-lookup"><span data-stu-id="6f083-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f083-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f083-111">Remarks</span></span>  
 <span data-ttu-id="6f083-112">`pDimensionSizes` И `pDimensionLowerBounds` являются параллельными массивами, поэтому характеристики одной сущности, элементы, расположенный в один и тот же индекс в каждом массиве.</span><span class="sxs-lookup"><span data-stu-id="6f083-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f083-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6f083-113">Requirements</span></span>  
 <span data-ttu-id="6f083-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f083-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f083-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f083-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f083-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f083-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f083-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f083-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f083-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6f083-118">See also</span></span>

- [<span data-ttu-id="6f083-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6f083-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="6f083-120">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="6f083-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
