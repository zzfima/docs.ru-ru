---
title: Метод ICorProfilerInfo4::GetObjectSize2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f72984da8f75eec35517da6ec1f8a73bc96c4609
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780808"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="58cc4-102">Метод ICorProfilerInfo4::GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="58cc4-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="58cc4-103">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="58cc4-103">Returns the size of a specified object.</span></span> <span data-ttu-id="58cc4-104">Заменяет [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) метод, фиксируя размеры объектов, размер которых больше нельзя выразить в `ULONG`.</span><span class="sxs-lookup"><span data-stu-id="58cc4-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58cc4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58cc4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58cc4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="58cc4-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="58cc4-107">[in] Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="58cc4-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="58cc4-108">[out] Указатель на размер объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="58cc4-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58cc4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="58cc4-109">Remarks</span></span>  
 <span data-ttu-id="58cc4-110">Разные объекты одного типа часто имеют одинаковый размер.</span><span class="sxs-lookup"><span data-stu-id="58cc4-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="58cc4-111">Тем не менее некоторые типы, например массивы или строки, возможно другого размера для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="58cc4-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58cc4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="58cc4-112">Requirements</span></span>  
 <span data-ttu-id="58cc4-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58cc4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58cc4-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58cc4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58cc4-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58cc4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58cc4-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58cc4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58cc4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="58cc4-117">See also</span></span>

- [<span data-ttu-id="58cc4-118">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="58cc4-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
