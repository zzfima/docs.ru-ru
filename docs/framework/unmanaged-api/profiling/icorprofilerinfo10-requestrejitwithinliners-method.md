---
title: 'ICorProfilerInfo10:: Рекуестрежитвисинлинерс'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 79a1c80f1c7582bd0751c43dea1d35a4d4d1c661
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973984"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="b1faf-102">Метод ICorProfilerInfo10:: Рекуестрежитвисинлинерс</span><span class="sxs-lookup"><span data-stu-id="b1faf-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>
  
<span data-ttu-id="b1faf-103">Режитс запрошенные методы, а также любые запрашиваются методы.</span><span class="sxs-lookup"><span data-stu-id="b1faf-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="b1faf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1faf-104">Syntax</span></span>  
  
```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1faf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1faf-105">Parameters</span></span>  
 
 `dwRejitFlags` \
 <span data-ttu-id="b1faf-106">окне Битовая маска [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b1faf-106">[in] A bitmask of [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span></span>
 
 `cFunctions`  
 <span data-ttu-id="b1faf-107">[in] Число функций для перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="b1faf-107">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="b1faf-108">[in] Указывает часть `moduleId` пар (`module`, `methodDef`), которые идентифицируют перекомпилируемые функции.</span><span class="sxs-lookup"><span data-stu-id="b1faf-108">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="b1faf-109">[in] Указывает часть `methodId` пар (`module`, `methodDef`), которые идентифицируют перекомпилируемые функции.</span><span class="sxs-lookup"><span data-stu-id="b1faf-109">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  

## <a name="remarks"></a><span data-ttu-id="b1faf-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1faf-110">Remarks</span></span>  
  <span data-ttu-id="b1faf-111">[Рекуестрежит](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) не выполняет отслеживание встроенных методов.</span><span class="sxs-lookup"><span data-stu-id="b1faf-111">[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="b1faf-112">Профилировщик ожидал блокировать встраивание или отслеживание встраивания, а также вызов `RequestReJIT` всех строк, чтобы гарантировать, что каждый экземпляр встроенного метода был режиттед.</span><span class="sxs-lookup"><span data-stu-id="b1faf-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="b1faf-113">Это создает проблему с ReJIT при присоединении, так как профилировщик отсутствует для мониторинга встраивания.</span><span class="sxs-lookup"><span data-stu-id="b1faf-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="b1faf-114">Этот метод может быть вызван, чтобы гарантировать, что полный набор Режиттед также будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="b1faf-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>  

## <a name="requirements"></a><span data-ttu-id="b1faf-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b1faf-115">Requirements</span></span>  
 <span data-ttu-id="b1faf-116">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="b1faf-116">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="b1faf-117">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b1faf-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1faf-118">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="b1faf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1faf-119">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1faf-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1faf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b1faf-120">See also</span></span>
- [<span data-ttu-id="b1faf-121">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="b1faf-121">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

