---
title: Метод ICorProfilerInfo2::GetBoxClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d00c28862036c21c44f46c23fb09e947628dcf3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783052"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="c6090-102">Метод ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="c6090-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="c6090-103">Получает сведения о расположении заданного типа значения при его упаковке.</span><span class="sxs-lookup"><span data-stu-id="c6090-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6090-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6090-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6090-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6090-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="c6090-106">[in] Идентификатор класса, который описывает тип значения, который упаковывается.</span><span class="sxs-lookup"><span data-stu-id="c6090-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="c6090-107">[out] Целое число, является смещение относительно указателя на идентификатор упакованный объект типа значения.</span><span class="sxs-lookup"><span data-stu-id="c6090-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6090-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6090-108">Remarks</span></span>  
 <span data-ttu-id="c6090-109">`pBufferOffset` Значение — это расположение в поле типа значения.</span><span class="sxs-lookup"><span data-stu-id="c6090-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="c6090-110">После `pBufferOffset` применяется макета класса типа значения в объект в рамке, могут использоваться для интерпретации значения объекта.</span><span class="sxs-lookup"><span data-stu-id="c6090-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6090-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c6090-111">Requirements</span></span>  
 <span data-ttu-id="c6090-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6090-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6090-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6090-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6090-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6090-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6090-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6090-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6090-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c6090-116">See also</span></span>

- [<span data-ttu-id="c6090-117">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c6090-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c6090-118">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="c6090-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
