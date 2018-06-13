---
title: Метод ICorProfilerInfo::IsArrayClass
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f34fee19c796f65d315fcbd26d55e1d5322303a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453032"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="ecbc7-102">Метод ICorProfilerInfo::IsArrayClass</span><span class="sxs-lookup"><span data-stu-id="ecbc7-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="ecbc7-103">Определяет, является ли указанный класс классом массива.</span><span class="sxs-lookup"><span data-stu-id="ecbc7-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecbc7-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecbc7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecbc7-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ecbc7-106">[in] Идентификатор класса необходимо проанализировать.</span><span class="sxs-lookup"><span data-stu-id="ecbc7-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="ecbc7-107">[out] Указатель на значение CorElementType перечисление, указывающее тип элементов массива.</span><span class="sxs-lookup"><span data-stu-id="ecbc7-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="ecbc7-108">[out] Указатель на идентификатор класса элементов массива, если оно доступно.</span><span class="sxs-lookup"><span data-stu-id="ecbc7-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="ecbc7-109">[out] Указатель на целое число, указывающее ранг (то есть число измерений) массива.</span><span class="sxs-lookup"><span data-stu-id="ecbc7-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecbc7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ecbc7-110">Remarks</span></span>  
 <span data-ttu-id="ecbc7-111">Если класс является классом массивов `IsArrayClass` метод возвращает значение S_OK HRESULT и значения для всех параметров, отличных от null выходные данные.</span><span class="sxs-lookup"><span data-stu-id="ecbc7-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="ecbc7-112">В противном случае возвращает значение S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="ecbc7-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecbc7-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ecbc7-113">Requirements</span></span>  
 <span data-ttu-id="ecbc7-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecbc7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbc7-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ecbc7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ecbc7-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecbc7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecbc7-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecbc7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbc7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ecbc7-118">See Also</span></span>  
 [<span data-ttu-id="ecbc7-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ecbc7-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
