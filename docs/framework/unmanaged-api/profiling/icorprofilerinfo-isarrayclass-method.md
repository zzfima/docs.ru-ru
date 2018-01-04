---
title: "Метод ICorProfilerInfo::IsArrayClass"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.IsArrayClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1063aea795d73ebaad0803abb7e555e1bb8b7e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="d1fa4-102">Метод ICorProfilerInfo::IsArrayClass</span><span class="sxs-lookup"><span data-stu-id="d1fa4-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="d1fa4-103">Определяет, является ли указанный класс классом массива.</span><span class="sxs-lookup"><span data-stu-id="d1fa4-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1fa4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1fa4-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1fa4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1fa4-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="d1fa4-106">[in] Идентификатор класса необходимо проанализировать.</span><span class="sxs-lookup"><span data-stu-id="d1fa4-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="d1fa4-107">[out] Указатель на значение CorElementType перечисление, указывающее тип элементов массива.</span><span class="sxs-lookup"><span data-stu-id="d1fa4-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="d1fa4-108">[out] Указатель на идентификатор класса элементов массива, если оно доступно.</span><span class="sxs-lookup"><span data-stu-id="d1fa4-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="d1fa4-109">[out] Указатель на целое число, указывающее ранг (то есть число измерений) массива.</span><span class="sxs-lookup"><span data-stu-id="d1fa4-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1fa4-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1fa4-110">Remarks</span></span>  
 <span data-ttu-id="d1fa4-111">Если класс является классом массивов `IsArrayClass` метод возвращает значение S_OK HRESULT и значения для всех параметров, отличных от null выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d1fa4-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="d1fa4-112">В противном случае возвращает значение S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="d1fa4-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1fa4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d1fa4-113">Requirements</span></span>  
 <span data-ttu-id="d1fa4-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1fa4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1fa4-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d1fa4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d1fa4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1fa4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1fa4-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1fa4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1fa4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d1fa4-118">See Also</span></span>  
 [<span data-ttu-id="d1fa4-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d1fa4-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
