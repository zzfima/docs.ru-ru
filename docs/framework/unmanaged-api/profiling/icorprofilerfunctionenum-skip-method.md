---
title: Метод ICorProfilerFunctionEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
ms.openlocfilehash: d2a0bff0d3d93ab8542699cffd3d0ecc032246ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448196"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="48921-102">Метод ICorProfilerFunctionEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="48921-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="48921-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="48921-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48921-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48921-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48921-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="48921-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="48921-106">[in] The number of elements to be skipped.</span><span class="sxs-lookup"><span data-stu-id="48921-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48921-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="48921-107">Return Value</span></span>  
 <span data-ttu-id="48921-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="48921-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="48921-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48921-109">HRESULT</span></span>|<span data-ttu-id="48921-110">Описание</span><span class="sxs-lookup"><span data-stu-id="48921-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48921-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="48921-111">S_OK</span></span>|<span data-ttu-id="48921-112">`celt` elements were skipped.</span><span class="sxs-lookup"><span data-stu-id="48921-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="48921-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="48921-113">S_FALSE</span></span>|<span data-ttu-id="48921-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span><span class="sxs-lookup"><span data-stu-id="48921-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48921-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="48921-115">Remarks</span></span>  
 <span data-ttu-id="48921-116">The new position of this enumerator's cursor is (current position) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="48921-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48921-117">Требования</span><span class="sxs-lookup"><span data-stu-id="48921-117">Requirements</span></span>  
 <span data-ttu-id="48921-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48921-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48921-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48921-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48921-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48921-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48921-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48921-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48921-122">См. также</span><span class="sxs-lookup"><span data-stu-id="48921-122">See also</span></span>

- [<span data-ttu-id="48921-123">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="48921-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="48921-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="48921-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
