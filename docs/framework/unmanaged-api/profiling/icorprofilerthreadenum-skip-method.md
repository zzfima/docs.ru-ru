---
title: "Метод ICorProfilerThreadEnum::Skip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c1840722a250dd627a5214700dca95c48aa2e8d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="5de18-102">Метод ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="5de18-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="5de18-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="5de18-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5de18-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5de18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5de18-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5de18-106">[in] Число элементов.</span><span class="sxs-lookup"><span data-stu-id="5de18-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5de18-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5de18-107">Return Value</span></span>  
 <span data-ttu-id="5de18-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="5de18-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5de18-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5de18-109">HRESULT</span></span>|<span data-ttu-id="5de18-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5de18-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5de18-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5de18-111">S_OK</span></span>|<span data-ttu-id="5de18-112">`celt`элементы были пропущены.</span><span class="sxs-lookup"><span data-stu-id="5de18-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="5de18-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5de18-113">S_FALSE</span></span>|<span data-ttu-id="5de18-114">Менее `celt` элементы были пропущены, указывающая, что отсутствуют дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="5de18-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5de18-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="5de18-115">Remarks</span></span>  
 <span data-ttu-id="5de18-116">Новое положение курсора данного перечислителя — (текущая позиция) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="5de18-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de18-117">Требования</span><span class="sxs-lookup"><span data-stu-id="5de18-117">Requirements</span></span>  
 <span data-ttu-id="5de18-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5de18-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de18-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5de18-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5de18-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5de18-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5de18-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de18-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de18-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5de18-122">See Also</span></span>  
 [<span data-ttu-id="5de18-123">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="5de18-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="5de18-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="5de18-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
