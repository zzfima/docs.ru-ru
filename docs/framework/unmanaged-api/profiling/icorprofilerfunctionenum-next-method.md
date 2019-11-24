---
title: Метод ICorProfilerFunctionEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
ms.openlocfilehash: 2ad4494cf3a429020099b4bd9d961341437fcd1e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447786"
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="e1637-102">Метод ICorProfilerFunctionEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e1637-102">ICorProfilerFunctionEnum::Next Method</span></span>
<span data-ttu-id="e1637-103">Возвращает заданное число смежных функций из последовательной коллекции функций начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="e1637-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1637-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1637-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1637-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1637-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e1637-106">[in] Число извлекаемых функций.</span><span class="sxs-lookup"><span data-stu-id="e1637-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="e1637-107">[out] Массив значений `COR_PRF_FUNCTION`, каждое из которых представляет извлеченную функцию.</span><span class="sxs-lookup"><span data-stu-id="e1637-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e1637-108">[out] Указатель на число функций, фактически извлеченных в массив `ids`.</span><span class="sxs-lookup"><span data-stu-id="e1637-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1637-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e1637-109">Return Value</span></span>  
 <span data-ttu-id="e1637-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="e1637-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e1637-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1637-111">HRESULT</span></span>|<span data-ttu-id="e1637-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e1637-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1637-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1637-113">S_OK</span></span>|<span data-ttu-id="e1637-114">Возвращенные элементы `celt`.</span><span class="sxs-lookup"><span data-stu-id="e1637-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="e1637-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e1637-115">S_FALSE</span></span>|<span data-ttu-id="e1637-116">Было возвращено элементов менее, чем `celt`, что указывает, что перечисление завершено.</span><span class="sxs-lookup"><span data-stu-id="e1637-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1637-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e1637-117">Requirements</span></span>  
 <span data-ttu-id="e1637-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1637-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1637-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e1637-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e1637-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1637-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1637-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1637-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1637-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e1637-122">See also</span></span>

- [<span data-ttu-id="e1637-123">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="e1637-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="e1637-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="e1637-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
