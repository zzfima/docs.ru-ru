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
ms.openlocfilehash: f046fb51753bfa79d333d465e8850794ecc73973
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453542"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="2a595-102">Метод ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="2a595-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="2a595-103">Получает сведения о расположении заданного типа значения при его упаковке.</span><span class="sxs-lookup"><span data-stu-id="2a595-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a595-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a595-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a595-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a595-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="2a595-106">[in] Идентификатор класса, который описывает тип значения, который упаковывается.</span><span class="sxs-lookup"><span data-stu-id="2a595-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="2a595-107">[out] Целое число, — это смещение относительно указатель идентификатор упакованный объект типа значения.</span><span class="sxs-lookup"><span data-stu-id="2a595-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a595-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a595-108">Remarks</span></span>  
 <span data-ttu-id="2a595-109">`pBufferOffset` Значение представляет собой местоположение типа значения в поле.</span><span class="sxs-lookup"><span data-stu-id="2a595-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="2a595-110">После `pBufferOffset` применяется для упакованного объекта макет класса тип значения можно использовать для интерпретации значения объекта.</span><span class="sxs-lookup"><span data-stu-id="2a595-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a595-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2a595-111">Requirements</span></span>  
 <span data-ttu-id="2a595-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a595-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a595-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a595-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a595-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a595-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a595-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a595-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a595-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2a595-116">See Also</span></span>  
 [<span data-ttu-id="2a595-117">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2a595-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="2a595-118">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="2a595-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
