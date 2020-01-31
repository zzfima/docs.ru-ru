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
ms.openlocfilehash: a22a0de9a20f32ce1c9818bbcf29222a4b331420
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862429"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="96842-102">Метод ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="96842-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="96842-103">Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="96842-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96842-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96842-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96842-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96842-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="96842-106">заполняет Указатель на перечислитель [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="96842-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96842-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="96842-107">Remarks</span></span>  
 <span data-ttu-id="96842-108">Этот метод может перекрываться с `JITCompilation` обратными вызовами, такими как метод [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="96842-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="96842-109">Перечислитель, возвращаемый этим методом, не включает функции, загруженные из образов в машинном кодах, созданных с помощью Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="96842-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96842-110">Возвращаемое перечисление содержит только значение "0" для значения поля `COR_PRF_FUNCTION::reJitId`.</span><span class="sxs-lookup"><span data-stu-id="96842-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="96842-111">Если требуются допустимые значения `COR_PRF_FUNCTION::reJitId`, используйте метод [метод icorprofilerinfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="96842-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96842-112">Требования</span><span class="sxs-lookup"><span data-stu-id="96842-112">Requirements</span></span>  
 <span data-ttu-id="96842-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96842-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96842-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96842-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96842-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96842-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96842-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96842-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96842-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="96842-117">See also</span></span>

- [<span data-ttu-id="96842-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="96842-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="96842-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="96842-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="96842-120">Профилирование</span><span class="sxs-lookup"><span data-stu-id="96842-120">Profiling</span></span>](index.md)
