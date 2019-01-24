---
title: Метод ICorProfilerModuleEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d34c88b52dcc8d07736b6866d467439654faa9a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681850"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="73f83-102">Метод ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="73f83-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="73f83-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="73f83-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f83-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73f83-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73f83-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73f83-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="73f83-106">[in] Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="73f83-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73f83-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="73f83-107">Return Value</span></span>  
 <span data-ttu-id="73f83-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="73f83-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="73f83-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73f83-109">HRESULT</span></span>|<span data-ttu-id="73f83-110">Описание</span><span class="sxs-lookup"><span data-stu-id="73f83-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73f83-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="73f83-111">S_OK</span></span>|<span data-ttu-id="73f83-112">`celt` элементы были пропущены.</span><span class="sxs-lookup"><span data-stu-id="73f83-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="73f83-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="73f83-113">S_FALSE</span></span>|<span data-ttu-id="73f83-114">Менее `celt` элементы были пропущены, который указывает, что никакие элементы.</span><span class="sxs-lookup"><span data-stu-id="73f83-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73f83-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="73f83-115">Remarks</span></span>  
 <span data-ttu-id="73f83-116">Новое положение курсора этот перечислитель является (текущей позиции) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="73f83-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73f83-117">Требования</span><span class="sxs-lookup"><span data-stu-id="73f83-117">Requirements</span></span>  
 <span data-ttu-id="73f83-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73f83-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f83-119">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="73f83-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="73f83-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73f83-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73f83-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f83-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f83-122">См. также</span><span class="sxs-lookup"><span data-stu-id="73f83-122">See also</span></span>
- [<span data-ttu-id="73f83-123">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="73f83-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="73f83-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="73f83-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
