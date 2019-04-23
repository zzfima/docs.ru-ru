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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173346"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="b14ae-102">Метод ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="b14ae-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="b14ae-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="b14ae-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b14ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b14ae-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b14ae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b14ae-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b14ae-106">[in] Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="b14ae-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b14ae-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b14ae-107">Return Value</span></span>  
 <span data-ttu-id="b14ae-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b14ae-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b14ae-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b14ae-109">HRESULT</span></span>|<span data-ttu-id="b14ae-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b14ae-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b14ae-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b14ae-111">S_OK</span></span>|<span data-ttu-id="b14ae-112">`celt` элементы были пропущены.</span><span class="sxs-lookup"><span data-stu-id="b14ae-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="b14ae-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b14ae-113">S_FALSE</span></span>|<span data-ttu-id="b14ae-114">Менее `celt` элементы были пропущены, который указывает, что никакие элементы.</span><span class="sxs-lookup"><span data-stu-id="b14ae-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b14ae-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="b14ae-115">Remarks</span></span>  
 <span data-ttu-id="b14ae-116">Новое положение курсора этот перечислитель является (текущей позиции) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="b14ae-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b14ae-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b14ae-117">Requirements</span></span>  
 <span data-ttu-id="b14ae-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b14ae-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b14ae-119">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b14ae-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b14ae-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b14ae-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b14ae-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b14ae-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14ae-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b14ae-122">See also</span></span>

- [<span data-ttu-id="b14ae-123">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="b14ae-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="b14ae-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="b14ae-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
