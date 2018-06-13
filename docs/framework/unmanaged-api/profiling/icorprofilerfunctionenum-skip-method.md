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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95301c4a99253261721c7f524b99f79a6207feb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453113"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="5c6a5-102">Метод ICorProfilerFunctionEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="5c6a5-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="5c6a5-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="5c6a5-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c6a5-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c6a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c6a5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5c6a5-106">[in] Число элементов.</span><span class="sxs-lookup"><span data-stu-id="5c6a5-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c6a5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5c6a5-107">Return Value</span></span>  
 <span data-ttu-id="5c6a5-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="5c6a5-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5c6a5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c6a5-109">HRESULT</span></span>|<span data-ttu-id="5c6a5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5c6a5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c6a5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c6a5-111">S_OK</span></span>|<span data-ttu-id="5c6a5-112">`celt` элементы были пропущены.</span><span class="sxs-lookup"><span data-stu-id="5c6a5-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="5c6a5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5c6a5-113">S_FALSE</span></span>|<span data-ttu-id="5c6a5-114">Менее `celt` элементы были пропущены, указывающая, что отсутствуют дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="5c6a5-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c6a5-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c6a5-115">Remarks</span></span>  
 <span data-ttu-id="5c6a5-116">Новое положение курсора данного перечислителя — (текущая позиция) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="5c6a5-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c6a5-117">Требования</span><span class="sxs-lookup"><span data-stu-id="5c6a5-117">Requirements</span></span>  
 <span data-ttu-id="5c6a5-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c6a5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6a5-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c6a5-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c6a5-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c6a5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c6a5-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c6a5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6a5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5c6a5-122">See Also</span></span>  
 [<span data-ttu-id="5c6a5-123">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="5c6a5-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="5c6a5-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="5c6a5-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
