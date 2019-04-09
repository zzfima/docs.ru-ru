---
title: Метод ICorProfilerThreadEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cce96e8c6d046beba9e45c7121bf68444fd51c95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173346"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="c3bdc-102">Метод ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="c3bdc-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="c3bdc-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="c3bdc-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3bdc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3bdc-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3bdc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3bdc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c3bdc-106">[in] Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="c3bdc-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3bdc-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c3bdc-107">Return Value</span></span>  
 <span data-ttu-id="c3bdc-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="c3bdc-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c3bdc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3bdc-109">HRESULT</span></span>|<span data-ttu-id="c3bdc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c3bdc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3bdc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3bdc-111">S_OK</span></span>|`celt` <span data-ttu-id="c3bdc-112">элементы были пропущены.</span><span class="sxs-lookup"><span data-stu-id="c3bdc-112">elements were skipped.</span></span>|  
|<span data-ttu-id="c3bdc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c3bdc-113">S_FALSE</span></span>|<span data-ttu-id="c3bdc-114">Менее `celt` элементы были пропущены, который указывает, что никакие элементы.</span><span class="sxs-lookup"><span data-stu-id="c3bdc-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3bdc-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3bdc-115">Remarks</span></span>  
 <span data-ttu-id="c3bdc-116">Новое положение курсора этот перечислитель является (текущей позиции) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="c3bdc-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3bdc-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c3bdc-117">Requirements</span></span>  
 <span data-ttu-id="c3bdc-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3bdc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3bdc-119">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3bdc-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3bdc-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3bdc-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c3bdc-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c3bdc-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c3bdc-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c3bdc-122">See also</span></span>

- [<span data-ttu-id="c3bdc-123">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="c3bdc-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="c3bdc-124">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="c3bdc-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
