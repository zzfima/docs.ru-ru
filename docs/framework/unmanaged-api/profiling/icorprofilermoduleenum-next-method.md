---
title: Метод ICorProfilerModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 974879b854f7a4c18aa4625ea88abb4953123f3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456154"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="5b815-102">Метод ICorProfilerModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="5b815-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="5b815-103">Возвращает заданное число смежных модулей из последовательной коллекции модулей начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="5b815-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b815-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b815-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b815-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b815-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5b815-106">[in] Количество модулей для извлечения.</span><span class="sxs-lookup"><span data-stu-id="5b815-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="5b815-107">[out] Массив значений `ModuleID`, каждое из которых представляет полученный модуль.</span><span class="sxs-lookup"><span data-stu-id="5b815-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5b815-108">[out] Указатель на число элементов, фактически извлеченных в массив `ids`.</span><span class="sxs-lookup"><span data-stu-id="5b815-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b815-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5b815-109">Return Value</span></span>  
 <span data-ttu-id="5b815-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="5b815-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5b815-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b815-111">HRESULT</span></span>|<span data-ttu-id="5b815-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5b815-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b815-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b815-113">S_OK</span></span>|<span data-ttu-id="5b815-114">Возвращенные элементы `celt`.</span><span class="sxs-lookup"><span data-stu-id="5b815-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="5b815-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5b815-115">S_FALSE</span></span>|<span data-ttu-id="5b815-116">Было возвращено элементов менее, чем `celt`, что указывает, что перечисление завершено.</span><span class="sxs-lookup"><span data-stu-id="5b815-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b815-117">Требования</span><span class="sxs-lookup"><span data-stu-id="5b815-117">Requirements</span></span>  
 <span data-ttu-id="5b815-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b815-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b815-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b815-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b815-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b815-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b815-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b815-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b815-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5b815-122">See Also</span></span>  
 [<span data-ttu-id="5b815-123">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="5b815-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="5b815-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="5b815-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
