---
title: "Метод ICorProfilerInfo4::GetObjectSize2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetObjectSize2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0aa13a056929c9cb4f63c52f1e993f110cfca7be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="f0d46-102">Метод ICorProfilerInfo4::GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="f0d46-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="f0d46-103">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="f0d46-103">Returns the size of a specified object.</span></span> <span data-ttu-id="f0d46-104">Заменяет [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) метод фиксируя размер объектов, размер которых превышает нельзя выразить в `ULONG`.</span><span class="sxs-lookup"><span data-stu-id="f0d46-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0d46-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0d46-105">Syntax</span></span>  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0d46-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0d46-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="f0d46-107">[in] Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="f0d46-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="f0d46-108">[out] Указатель на размер объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="f0d46-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0d46-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0d46-109">Remarks</span></span>  
 <span data-ttu-id="f0d46-110">Разные объекты одного типа часто имеют одинаковый размер.</span><span class="sxs-lookup"><span data-stu-id="f0d46-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="f0d46-111">Однако некоторые типы, например массивов или строк, могут иметь другого размера для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="f0d46-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0d46-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f0d46-112">Requirements</span></span>  
 <span data-ttu-id="f0d46-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0d46-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0d46-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0d46-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0d46-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0d46-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0d46-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0d46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d46-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f0d46-117">See Also</span></span>  
 [<span data-ttu-id="f0d46-118">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="f0d46-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
