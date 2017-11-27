---
title: "Метод ICorProfilerFunctionEnum::Skip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Skip Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c5142b091ec32c162daaca9c53cb65763bb5ed7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="a29c3-102">Метод ICorProfilerFunctionEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="a29c3-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="a29c3-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="a29c3-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a29c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a29c3-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a29c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a29c3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a29c3-106">[in] Число элементов.</span><span class="sxs-lookup"><span data-stu-id="a29c3-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a29c3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a29c3-107">Return Value</span></span>  
 <span data-ttu-id="a29c3-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="a29c3-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a29c3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a29c3-109">HRESULT</span></span>|<span data-ttu-id="a29c3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a29c3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a29c3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a29c3-111">S_OK</span></span>|<span data-ttu-id="a29c3-112">`celt`элементы были пропущены.</span><span class="sxs-lookup"><span data-stu-id="a29c3-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="a29c3-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a29c3-113">S_FALSE</span></span>|<span data-ttu-id="a29c3-114">Менее `celt` элементы были пропущены, указывающая, что отсутствуют дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="a29c3-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a29c3-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="a29c3-115">Remarks</span></span>  
 <span data-ttu-id="a29c3-116">Новое положение курсора данного перечислителя — (текущая позиция) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="a29c3-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a29c3-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a29c3-117">Requirements</span></span>  
 <span data-ttu-id="a29c3-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a29c3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a29c3-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a29c3-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a29c3-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a29c3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a29c3-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a29c3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a29c3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a29c3-122">See Also</span></span>  
 [<span data-ttu-id="a29c3-123">ICorProfilerFunctionEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a29c3-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="a29c3-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="a29c3-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
