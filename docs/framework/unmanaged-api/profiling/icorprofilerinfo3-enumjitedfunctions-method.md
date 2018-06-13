---
title: Метод ICorProfilerInfo3::EnumJITedFunctions
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f35a712472887a928b1732f076b39ac08724c7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456075"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="f8d29-102">Метод ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="f8d29-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="f8d29-103">Возвращает перечислитель для всех функций, которые были ранее JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="f8d29-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8d29-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8d29-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8d29-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f8d29-106">[out] Указатель на [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) перечислителя.</span><span class="sxs-lookup"><span data-stu-id="f8d29-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8d29-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8d29-107">Remarks</span></span>  
 <span data-ttu-id="f8d29-108">Этот метод может перекрывать `JITCompilation` обратных вызовов, таких как [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f8d29-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="f8d29-109">Перечислитель, который возвращается этим методом не включает функции, загруженные из собственных образов, созданных с помощью Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="f8d29-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8d29-110">Включает только «0» для значение возвращенного перечисления `COR_PRF_FUNCTION::reJitId` поля.</span><span class="sxs-lookup"><span data-stu-id="f8d29-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="f8d29-111">Если требуется допустимый `COR_PRF_FUNCTION::reJitId` значения, используйте [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f8d29-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8d29-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f8d29-112">Requirements</span></span>  
 <span data-ttu-id="f8d29-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8d29-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8d29-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8d29-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8d29-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8d29-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8d29-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8d29-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d29-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f8d29-117">See Also</span></span>  
 [<span data-ttu-id="f8d29-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="f8d29-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="f8d29-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="f8d29-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="f8d29-120">Профилирование</span><span class="sxs-lookup"><span data-stu-id="f8d29-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
