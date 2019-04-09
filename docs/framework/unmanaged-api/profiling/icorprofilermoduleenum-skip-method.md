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
ms.openlocfilehash: 397e8afcc176bcd9733e83dc6425fe49f385931e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078206"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="d5f00-102">Метод ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="d5f00-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="d5f00-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="d5f00-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5f00-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5f00-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5f00-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d5f00-106">[in] Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="d5f00-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5f00-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d5f00-107">Return Value</span></span>  
 <span data-ttu-id="d5f00-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="d5f00-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d5f00-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5f00-109">HRESULT</span></span>|<span data-ttu-id="d5f00-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d5f00-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5f00-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5f00-111">S_OK</span></span>|`celt` <span data-ttu-id="d5f00-112">элементы были пропущены.</span><span class="sxs-lookup"><span data-stu-id="d5f00-112">elements were skipped.</span></span>|  
|<span data-ttu-id="d5f00-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d5f00-113">S_FALSE</span></span>|<span data-ttu-id="d5f00-114">Менее `celt` элементы были пропущены, который указывает, что никакие элементы.</span><span class="sxs-lookup"><span data-stu-id="d5f00-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5f00-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5f00-115">Remarks</span></span>  
 <span data-ttu-id="d5f00-116">Новое положение курсора этот перечислитель является (текущей позиции) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="d5f00-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5f00-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d5f00-117">Requirements</span></span>  
 <span data-ttu-id="d5f00-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5f00-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5f00-119">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5f00-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5f00-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5f00-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d5f00-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d5f00-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5f00-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d5f00-122">See also</span></span>

- [<span data-ttu-id="d5f00-123">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="d5f00-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="d5f00-124">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="d5f00-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
