---
title: Метод ICorProfilerThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44595229eaefa0d8fc8ca7bf15a88d0fbf1ee0d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104316"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="28c4c-102">Метод ICorProfilerThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="28c4c-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="28c4c-103">Возвращает заданное число смежных потоков из упорядоченной коллекции потоков начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="28c4c-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c4c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28c4c-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28c4c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28c4c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="28c4c-106">[in] Количество потоков для извлечения.</span><span class="sxs-lookup"><span data-stu-id="28c4c-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="28c4c-107">[out] Массив значений `ThreadID`, каждое из которых представляет полученный поток.</span><span class="sxs-lookup"><span data-stu-id="28c4c-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="28c4c-108">[out] Указатель на число потоков, фактически извлеченных в массив `ids`.</span><span class="sxs-lookup"><span data-stu-id="28c4c-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28c4c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="28c4c-109">Return Value</span></span>  
 <span data-ttu-id="28c4c-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="28c4c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="28c4c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28c4c-111">HRESULT</span></span>|<span data-ttu-id="28c4c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="28c4c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28c4c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="28c4c-113">S_OK</span></span>|<span data-ttu-id="28c4c-114">Возвращенные элементы `celt`.</span><span class="sxs-lookup"><span data-stu-id="28c4c-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="28c4c-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="28c4c-115">S_FALSE</span></span>|<span data-ttu-id="28c4c-116">Было возвращено элементов менее, чем `celt`, что указывает, что перечисление завершено.</span><span class="sxs-lookup"><span data-stu-id="28c4c-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28c4c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="28c4c-117">Requirements</span></span>  
 <span data-ttu-id="28c4c-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28c4c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28c4c-119">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28c4c-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28c4c-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28c4c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28c4c-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28c4c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c4c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="28c4c-122">See also</span></span>

- [<span data-ttu-id="28c4c-123">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="28c4c-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="28c4c-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="28c4c-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
