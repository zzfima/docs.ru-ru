---
title: "Метод ICorProfilerModuleEnum::Skip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum.Skip Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7331c5221de1dc1bfdbbce77f8c40f4fbc95aea2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="2811b-102">Метод ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="2811b-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="2811b-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="2811b-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2811b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2811b-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2811b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2811b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2811b-106">[in] Число элементов.</span><span class="sxs-lookup"><span data-stu-id="2811b-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2811b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2811b-107">Return Value</span></span>  
 <span data-ttu-id="2811b-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="2811b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2811b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2811b-109">HRESULT</span></span>|<span data-ttu-id="2811b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2811b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2811b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2811b-111">S_OK</span></span>|<span data-ttu-id="2811b-112">`celt`элементы были пропущены.</span><span class="sxs-lookup"><span data-stu-id="2811b-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="2811b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2811b-113">S_FALSE</span></span>|<span data-ttu-id="2811b-114">Менее `celt` элементы были пропущены, указывающая, что отсутствуют дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="2811b-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2811b-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="2811b-115">Remarks</span></span>  
 <span data-ttu-id="2811b-116">Новое положение курсора данного перечислителя — (текущая позиция) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="2811b-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2811b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2811b-117">Requirements</span></span>  
 <span data-ttu-id="2811b-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2811b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2811b-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2811b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2811b-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2811b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2811b-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2811b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2811b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2811b-122">See Also</span></span>  
 [<span data-ttu-id="2811b-123">Icorprofilermoduleenum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2811b-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="2811b-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="2811b-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
